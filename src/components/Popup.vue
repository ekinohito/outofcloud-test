<template>
  <div class="popup" v-if="isOpen" @click="closeClean">
    <div class="popup__paper" @click.stop>
      <div v-if="success">
        <h4>Спасибо!</h4>
      </div>
      <div v-else>
        <h4>Введите Ваш E-mail</h4>
        <div> <span v-show="err">{{err}}</span></div>
        <div>
          <input v-model="email" class="popup__input" :class="{ 'popup__input_red-highlight': err }" @focus="err = null"/>
          <div class="popup__button-row">
            <Button text="Закрыть" outlined :action="closeClean"/>
            <Button text="Отправить" :action="sendEmail"/>
          </div>
        </div>
      </div>

    </div>
  </div>
</template>

<script>
import Button from "@/components/Button";
import {postEmail} from "@/utils/jsonAPI";
export default {
  name: "Popup",
  components: {Button},
  props: {
    isOpen: Boolean,
    close: Function
  },
  methods: {
    validateEmail() {
      if (!this.email) return "Необходимо ввести E-mail"
      // simple email verification
      const re = /^([a-z0-9_-]+\.)*[a-z0-9_-]+@[a-z0-9_-]+(\.[a-z0-9_-]+)*\.[a-z]{2,6}$/
      if (!re.test(this.email)) return "Введите корректный E-mail"
      return null
    },
    async sendEmail() {
      this.err = this.validateEmail()
      if (this.err) return
      this.err = await postEmail(this.email)
      if (this.err) return
      this.success = true
    },
    closeClean() {
      this.success = false
      this.close()
    }
  },
  data() {
    return {
      email: null,
      err: null,
      success: false,
    }
  }
}
</script>

<style scoped>
  .popup {
    width: 100vw;
    height: 100vh;
    background-color: #2c3e5030;
    position: fixed;
    display: flex;
    justify-content: center;
    align-items: center;
    left: auto;
    right: auto;
    z-index: 1;
  }

  .popup__button-row {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
  }

  .popup__paper {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    margin: 30px;
    width: 640px;
    padding: 40px 100px;
    box-sizing: border-box;
    background-color: #FFFFFF;
    border-radius: 10px;
    box-shadow: 0 0 40px rgba(0, 0, 0, 0.1);
  }

  .popup__input {
    margin-bottom: 20px;
    width: 100%;
    outline: none;
    border: none;
    padding: 10px;
    background-color: #F1F1F1;
  }

  .popup__input:focus {
    background-color: #E0E0E0;
  }

  .popup__input_red-highlight {
    background-color: #e57e7e;
  }
</style>