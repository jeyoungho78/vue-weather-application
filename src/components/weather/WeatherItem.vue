<template>
  <li class="weather-item">
    <h3>{{ weather.label }}</h3>
    <p class="temperature">{{ weather.temperature }}&deg;c</p>
    <p class="info">
      <!-- <img src="https://placeimg.com/20/20/any" alt="any" /> -->
      <!-- <img src="http://Placehold.it/20x20" alt="any" /> -->
      <img :src="weather.icon" alt="" />
      <span>습도 {{ weather.humidity }}</span>
      <span>바람 {{ weather.wind }}</span>
    </p>
  </li>
</template>

<script>
export default {
  name: "weatherItem",
  props: {
    weather: {
      type: Object,
      default() {
        return {
          label: "서울",
          code: "Seoul",
          temperature: 20,
          humidity: 15,
          wind: 1.5,
        };
      },
    },
  },
};
</script>

<style scoped>
.weather-item {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  border: 1px solid #efefef;
  padding: 0.5em;
}
.weather-item h3 {
  font-size: 14px;
  color: #333;
}
.temperature {
  font-size: 36px;
}
.info {
  display: flex;
  justify-content: center;
  align-items: center;
  font-size: 12px;
}
</style>
