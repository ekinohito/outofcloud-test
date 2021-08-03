<template>
  <div class="popup" v-if="isOpen" @click="close">
    <div class="popup__paper" @click.stop>
      <div class="popup__input-wrapper">
        <input class="popup__input"/>
      </div>
      <input class="popup__input"/>
      <div>
        <Button text="Закрыть" outlined :action="close"/>
        <Button text="Отправить"/>
      </div>
    </div>
  </div>
</template>

<script>
import Button from "@/components/Button";
export default {
  name: "Popup",
  components: {Button},
  props: {
    isOpen: Boolean,
    close: Function
  }
}
</script>

<style scoped>
  .popup {
    width: 100vmax;
    height: 100vmax;
    background-color: #2c3e5030;
    position: fixed;
    display: flex;
    justify-content: center;
    left: auto;
    right: auto;
    z-index: 1;
  }

  .popup__paper {
    margin: 30px;
    width: 640px;
    height: 450px;
    box-sizing: border-box;
    background-color: #FFFFFF;
    border-radius: 10px;
    box-shadow: 0 0 40px rgba(0, 0, 0, 0.1);
  }

  .popup__input {
    margin-bottom: 20px;
    outline: none;
    border: none;
    padding: 20px;
    background-color: #F1F1F1;
  }

  .popup__input:focus {
    background-color: #D0D0D0;
  }
</style>