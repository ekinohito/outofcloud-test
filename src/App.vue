<template>
  <Popup :is-open="isOpen" :close="closePopup"/>
  <div class="container">
    <Slider :slides="slides"/>
    <Button text="К покупкам" :action="openPopup" large/>
  </div>
</template>

<script>
import Slider from "@/components/Slider";
import slides from "./data/slides.json"
import Button from "@/components/Button";
import Popup from "@/components/Popup";

export default {
  name: 'App',
  components: {
    Popup,
    Button,
    Slider
  },
  data() {
    return {
      slides,
      isOpen: false
    }
  },
  methods: {
    openPopup() {
      this.isOpen = true
    },
    closePopup() {
      this.isOpen = false
    }
  }
}
</script>

<style>
body {
  margin: 0;
  color: #2c3e50;
  background-color: #F6F6F6;
}

@font-face {
  font-family: 'RotondaC';
  font-style: normal;
  font-weight: normal;
  src: local('RotondaC'), url('assets/fonts/RotondaC.woff') format('woff');
}


@font-face {
  font-family: 'RotondaC';
  font-style: normal;
  font-weight: bold;
  src: local('RotondaC Bold'), url('assets/fonts/RotondaC-Bold.woff') format('woff');
}

.container {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

#app {
  font-family: RotondaC, Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;}
</style>
