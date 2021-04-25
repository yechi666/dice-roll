<template>
  <div id="app">
    <img id="img" :src="url" />
    <button class="btn" type="button" @click="rollDice">Roll the dice!</button>
  </div>
</template>

<script>
export default {
  name: "app",
  data: () => ({
    gifUrl: require("../public/assets/rolling.gif"),
    url: "",
  }),
  mounted() {
    this.url = this.gifUrl;
  },
  methods: {
    rollDice() {
      this.url = this.gifUrl;

      setTimeout(() => {
        const number = Math.floor(Math.random() * 6) + 1;
        this.url = require(`../public/assets/dice${number}.png`);
      }, 1000);
    },
  },
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.btn {
  position: relative;
  display: block;
  margin: 30px auto;
  padding: 0;
  overflow: hidden;
  border-width: 0;
  outline: none;
  border-radius: 2px;
  box-shadow: 0 1px 4px rgba(0, 0, 0, 0.6);
  background-color: #2ecc71;
  color: #ecf0f1;
  transition: background-color 0.3s;
  padding: 15px;
}
</style>
