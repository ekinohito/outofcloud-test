<template>
  <div class="slider">
    <img src="../assets/icons/Arrow-left.svg"
         class="slider__button" :class="{ 'slider__button_disabled': currentIsFirst() }" alt="<" @click="prevSlide"/>
    <div class="slider__show">
      <template v-for="slide in slides" :key="slide.id">
        <div class="slider__slide" :class="{
          'slider__slide_displaced-left':  slide.id < currentSlide,
          'slider__slide_displaced-right': slide.id > currentSlide
        }">
          <SliderCard
              :image="require(`@/assets/slider/${slide.image}`)" :id="slide.id"
              :title="slide.title" :description="slide.description"/>
        </div>
      </template>
    </div>
    <img src="../assets/icons/Arrow-right.svg"
         class="slider__button" :class="{ 'slider__button_disabled': currentIsLast() }" alt=">" @click="nextSlide"/>
  </div>
</template>

<script>
import SliderCard from "@/components/SliderCard";
export default {
  name: "Slider",
  components: {SliderCard},
  props: {
    slides: Array
  },
  data() {
    return {
      currentSlide: 1
    }
  },
  methods: {
    currentIsFirst() {
      return this.currentSlide <= 1
    },
    currentIsLast() {
      return this.currentSlide >= this.slides.length
    },
    nextSlide() {
      if (this.currentIsLast()) return
      this.currentSlide += 1
    },
    prevSlide() {
      if (this.currentIsFirst()) return
      this.currentSlide -= 1
    }
  }
}
</script>

<style scoped>
  .slider {
    max-width: 800px;
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-content: center;
  }

  .slider__show {
    width: 640px;
    height: 450px;
    margin: 30px;
    padding-bottom: 30px;
    overflow: hidden;
  }

  .slider__slide {
    height: 0;
    transform: translate(0);
    transition-property: all;
    transition-duration: .5s;
    transition-timing-function: ease-out;
  }

  .slider__slide_displaced-left {
    transform: translate(-110%);
  }
  .slider__slide_displaced-right {
    transform: translate(110%);
  }

  .slider__button {
    height: 40px;
    align-self: center;
    cursor: pointer;
  }

  .slider__button_disabled {
    cursor: default;
    opacity: 20%;
  }
</style>