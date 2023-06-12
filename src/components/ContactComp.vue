<template>
  <form
    ref="refContact"
    class="ContactContainer"
    :class="{ invisible: !visibilityContact }"
    @submit.prevent="sendEmail"
  >
    <span class="ContactTitle">Write me a message!</span>
    <div class="Tile">
      <label for="name">Your name</label>
      <input
        id="name"
        placeholder="John Doe"
        v-model="name"
        autocomplete="off"
        type="text"
        class="ContactInput"
        :class="{ light: !darkMode }"
      />
    </div>
    <div class="Tile">
      <label for="email">Your E-mail</label>
      <input
        id="email"
        placeholder="email@example.com"
        v-model="email"
        autocomplete="off"
        type="email"
        class="ContactInput"
        :class="{ light: !darkMode }"
      />
    </div>
    <div class="Tile">
      <label for="message">Your message</label>
      <textarea
        id="message"
        placeholder="Your message"
        v-model="message"
        class="ContactBox"
        :class="{ light: !darkMode }"
      />
    </div>
    <button type="submit" class="SendButton" :class="{ light: !darkMode }">
      Send
    </button>
  </form>
</template>

<script>
import { onMounted, reactive, ref, toRefs } from "vue";
import emailjs from "@emailjs/browser";
import { useNotification } from "@kyvg/vue3-notification";

export default {
  name: "ContactComp",
  props: ["darkMode"],
  setup() {
    const notification = useNotification()
    const state = reactive({
      message: "",
      name: "",
      email: "",
      visibilityContact: false,
    });
    const refContact = ref(null);
    //reactive watch
    // watch(()=>state.messageContent, () => {
    //   console.log(state);
    // });

    //ref watch
    // watch(areaText, (newValue) => {
    //   console.log('Aktualna wartość pola textarea:', newValue);
    // });

    onMounted(() => {
      const contactObserver = new IntersectionObserver(
        (entries) => {
          entries.forEach((entry) => {
            if (entry.intersectionRatio >= 0.1) {
              state.visibilityContact = true;
            } else {
              state.visibilityContact = false;
            }
          });
        },
        { threshold: 0.1 }
      );
      contactObserver.observe(refContact.value);
    });

    function sendEmail() {
      const requestTemplate = {
        name: state.name,
        email: state.email,
        message: state.message,
      };
      emailjs
        .send(
          process.env.VUE_APP_MAIL_SERVICE,
          process.env.VUE_APP_MAIL_TEMPLATE,
          requestTemplate,
          process.env.VUE_APP_MAIL_PUBLIC_KEY
        )
        .then(
          (result) => {
            window.scrollTo({
              top: 0,
              behavior: "smooth",
            })
            console.log("SUCCESS!", result.text);
            state.email = "";
            state.name = "";
            state.message = "";
            notification.notify({
              title: "Message has been sent 😎",
              type:'success'
            });
          },
          (error) => {
            console.log("FAILED...", error.text);
            state.email = "";
            state.name = "";
            state.message = "";
            notification.notify({
              title: "Something went wrong, try again later 😞",
              type:'error'
            });
          }
        );
    }

    return { refContact, ...toRefs(state), sendEmail };
  },
};
</script>

<style scoped>
.ContactContainer {
  box-sizing: border-box;
  opacity: 1;
  margin: 5rem auto 0;
  padding-bottom: 5rem;
  display: flex;
  justify-content: center;
  gap: 3rem;
  align-items: center;
  flex-direction: column;
  width: 40%;
  height: max-content;
  transition: 0.5s ease;
}

.Tile {
  display: flex;
  gap: 1rem;
  flex-direction: column;
  width: 100%;
}

.ContactInput {
  border-radius: 10px;
  width: 100%;
  background: rgba(255, 255, 255, 0.11);
  border: 2px solid rgba(197, 180, 180, 0.45);
  font-size: 1rem;
  outline: none;
  color: white;
  padding: 10px;
  transition: 0.3s ease;
}

.ContactInput:focus {
  background: rgba(255, 255, 255, 0.32);
}

.ContactInput:focus::placeholder {
  color: #2c2c2c;
}

.ContactInput.light:focus {
  background: rgba(75, 74, 74, 0.11);
}

.ContactInput.light {
  background: rgba(255, 255, 255, 0.11);
  border: 2px solid rgba(0, 0, 0, 0.45);
  color: black;
}

.Tile label {
  font-size: 1.2rem;
}

.ContactContainer.invisible {
  opacity: 0;
}

.ContactTitle {
  z-index: 10;
  margin-top: 2rem;
  font-size: 1.5rem;
}

.ContactBox {
  border-radius: 10px;
  resize: none;
  width: 100%;
  height: 14rem;
  background: rgba(255, 255, 255, 0.11);
  border: 2px solid rgba(197, 180, 180, 0.45);
  font-size: 1rem;
  outline: none;
  color: white;
  padding: 10px;
  transition: 0.3s ease;
}

.ContactBox:focus {
  background: rgba(255, 255, 255, 0.32);
}

.ContactBox:focus::placeholder {
  color: #2c2c2c;
}

.ContactBox.light {
  background: rgba(255, 255, 255, 0.11);
  border: 2px solid rgba(0, 0, 0, 0.45);
  color: black;
}

.ContactBox.light:focus {
  background: rgba(75, 74, 74, 0.11);
}

.SendButton {
  width: 30%;
  height: 3rem;
  font-size: 1rem;
  background: rgba(255, 255, 255, 0.47);
  border-radius: 20px;
  color: white;
  border: 1px solid rgba(197, 180, 180, 0.45);
  cursor: pointer;
  transition: 0.3s ease;
  backface-visibility: hidden;
  will-change: transform;
}

.SendButton:hover {
  background: rgba(70, 70, 70, 1);
  transform-origin: center;
  transform: scale(1.05);
}

.SendButton.light {
  width: 30%;
  height: 3rem;
  background: rgba(255, 255, 255, 0.62);
  border: 1px solid rgba(103, 102, 102, 0.73);
  color: black;
}

.SendButton.light:hover {
  background: rgb(248, 246, 246);
  transform-origin: center;
  transform: scale(1.05);
}

@media screen and (max-width: 860px) {
  .ContactBox {
    font-size: 1rem;
  }

  .ContactTitle {
    width: 110%;
  }

  .ContactInput {
    font-size: 1rem;
  }

  .SendButton,
  .SendButton.light {
    width: 55%;
    font-size: 0.9rem;
  }
}
</style>
