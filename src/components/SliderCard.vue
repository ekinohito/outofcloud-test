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
    padding: 40px 40px 0;
    display: flex;
    flex-direction: column;
    justify-content: flex-start;
    align-items: center;
    max-width: 640px;
    height: 410px;
    background-color: #FFFFFF;
    border-radius: 10px;
    box-shadow: 0 0 40px rgba(0, 0, 0, 0.1)
  }

  .slider-card__image {
    object-fit: cover;
    max-width: 560px;
    max-height: 284px;
    width: 100%;
    min-height:160px;
    margin: 0 0 28px 0;
  }

  .slider-card__label {
    margin: 0;
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