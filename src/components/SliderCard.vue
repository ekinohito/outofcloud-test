<template>
  <div class="slider-card">
    <div class="slider-card__image-wrapper">
      <span class="slider-card__badge">{{id}}</span>
      <img class="slider-card__image" :src="image" :alt="title"/>
    </div>
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
    id: Number,
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
    height: 450px;
    box-sizing: border-box;
    background-color: #FFFFFF;
    border-radius: 10px;
    box-shadow: 0 0 40px rgba(0, 0, 0, 0.1);
  }

  .slider-card__image {
    object-fit: cover;
    max-width: 560px;
    max-height: 284px;
    width: 100%;
    min-height:160px;
    margin: 0 0 28px 0;
  }

  .slider-card__image-wrapper {
    position: relative;
  }

  .slider-card__badge {
    position: absolute;
    top: -12px;
    left: -4px;
    width: 50px;
    height: 50px;
    background-color: #FFFFFF;
    color: #7DB945;
    font-size: 22px;
    line-height: 50px;
    font-weight: bold;
    border-radius: 25px;
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