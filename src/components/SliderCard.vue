<template>
  <div class="slider-card">
    <img class="slider-card__image" :src="image" :alt="title"/>
    <p class="slider-card__label">
      <span class="slider-card__description slider-card__description_bold">{{title}}</span><br/>
      <span class="slider-card__description">{{description}}</span>
    </p>
  </div>
</template>

<script>
export default {
  name: "SliderCard",
  props: {
    image: String,
    title: String,
    description: String
  }
}
</script>

<style scoped>
  .slider-card {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    width: 640px;
    height: 450px;
    background-color: #FFFFFF;
    border-radius: 5px;
  }

  .slider-card__image {
    object-fit: cover;
    max-width: 560px;
    max-height: 284px;
    width: 100%;
    min-height:160px;
  }

  .slider-card__label {
    margin-top: 28px
  }

  .slider-card__description {
    font-weight: 400;
    font-size: 16px;
    line-height: 24px;
    text-align: center;
  }

  .slider-card__description_bold {
    font-weight: 700;
  }
</style>