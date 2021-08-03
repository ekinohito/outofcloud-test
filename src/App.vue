<template>
  <div class="container">
    <Slider :slides="slides"/>

  </div>
</template>

<script>
import Slider from "@/components/Slider";
import slides from "./data/slides.json"

export default {
  name: 'App',
  components: {
    Slider
  },
  data() {
    return {
      slides
    }
  }
}
</script>

<style>
@font-face {
  font-family: 'RotondaC';
  font-style: normal;
  font-weight: normal;
  src: local('RotondaC'), url('assets/fonts/RotondaC.woff') format('woff');
}


@font-face {
  font-family: 'RotondaC Bold';
  font-style: normal;
  font-weight: normal;
  src: local('RotondaC Bold'), url('assets/fonts/RotondaC-Bold.woff') format('woff');
}

.container {
  display: flex;
  justify-content: center;
  align-content: center;
}

#app {
  font-family: RotondaC, Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  background-color: #F6F6F6;
  margin-top: 60px;
}
</style>
