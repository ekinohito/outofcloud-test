<template>
  <button class="button" :class="{ 'button_outlined': outlined, 'button_large': large }" @click="action">{{text}}</button>
</template>

<script>
export default {
  name: "Button",
  props: {
    text: String,
    action: Function,
    outlined: Boolean,
    large: Boolean
  }
}
</script>

<style scoped>
  .button {
    font-family: RotondaC, Avenir, Helvetica, Arial, sans-serif;
    font-size: 22px;
    font-weight: bold;
    border-radius: 10px;
    padding: 10px;
    color: #FFFFFF;
    background-color: #7DB945;
    border: none;
    cursor: pointer;
  }

  .button_outlined {
    background-color: #FFFFFF;
    color: #7DB945;
    border: 2px solid #7DB945;
  }

  .button_large {
    width: 340px;
    height: 70px;
  }
</style>