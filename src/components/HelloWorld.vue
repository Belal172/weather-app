<template>
  <div class="weather-app">
    <h1>Weather App 🌤</h1>

    <input v-model="city" placeholder="Enter city name" />
    <button @click="fetchWeather">Get Weather</button>

    <div v-if="weather">
      <h2>{{ weather.name }}, {{ weather.sys.country }}</h2>
      <p>🌡 Temperature: {{ temperature }}°C</p>
      <p>☁ Condition: {{ weather.weather[0].description }}</p>
      <p>💨 Wind Speed: {{ weather.wind.speed }} m/s</p>
    </div>

    <p v-if="error" style="color: red;">{{ error }}</p>
  </div>
</template>

<script>
import axios from "axios";

export default {
  data() {
    return {
      city: "Kathmandu",
      weather: null,
      error: null,
      apiKey: "9094512bd89c5bd93fb7e9c170906def"
    };
  },
  computed: {
    temperature() {
      return this.weather ? (this.weather.main.temp - 273.15).toFixed(2) : "";
    }
  },
  methods: {
  async fetchWeather() {
    this.error = null;
    if (!this.city) {
      this.error = "Please enter a city name.";
      return;
    }
    try {
      const response = await axios.get(
        `https://api.openweathermap.org/data/2.5/weather?q=${this.city}&appid=${this.apiKey}`
      );
      this.weather = response.data;
    } catch (err) {
      this.error = "City not found! Please try again.";
      this.weather = null;
    }
  }
},
  mounted() {
    this.fetchWeather(); // Fetch default city's weather on load
  }
};
</script>

<style>
.weather-app {
  text-align: center;
  font-family: Arial, sans-serif;
  margin-top: 50px;
}
input {
  padding: 10px;
  margin: 10px;
}
button {
  padding: 10px;
  background: blue;
  color: white;
  border: none;
  cursor: pointer;
}
</style>
