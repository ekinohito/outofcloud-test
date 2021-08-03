<template>
  <button class="button" :class="{ 'button_outlined': outlined }" @click="action">{{text}}</button>
</template>

<script>
export default {
  name: "Button",
  props: {
    text: String,
    action: Function,
    outlined: Boolean
  }
}
</script>

<style scoped>
  .button {
    font-family: RotondaC, Avenir, Helvetica, Arial, sans-serif;
    font-size: 22px;
    font-weight: bold;
    border-radius: 10px;
    width: 340px;
    height: 70px;
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
</style>