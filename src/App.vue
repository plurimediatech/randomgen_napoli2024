<template>
  <div id="app">
  <h1>Random Number Generator</h1>
  <div>
  <label for="min">Min:</label>
  <input type="number" v-model.number="min" id="min" />
  </div>
  <div>
  <label for="max">Max:</label>
  <input type="number" v-model.number="max" id="max" />
  </div>
  <button @click="generateRandomNumber">Generate Random Number</button>
  <p v-if="randomNumber !== null">Random Number: {{ randomNumber }}</p>
  </div>
  </template>
  
  <script>
  export default {
  data() {
  return {
  min: 1,
  max: 100,
  randomNumber: null,
  };
  },
  methods: {
  generateRandomNumber() {
  if (this.min < this.max) {
  this.randomNumber = Math.floor(Math.random() * (this.max - this.min + 1)) + this.min;
  } else {
  alert("Min should be less than Max");
  }
  },
  },
  };
  </script>
  
  <style>
  #app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: center;
  margin-top: 60px;
  }
  label {
  margin-right: 10px;
  }
  input {
  margin-bottom: 10px;
  }
  button {
  padding: 10px 20px;
  font-size: 16px;
  cursor: pointer;
  }
  </style>