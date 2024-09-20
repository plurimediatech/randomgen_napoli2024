<template>
  <div id="app">
    <div class="header">
      <h1>Tecnologie avanzate e nuove competenze:</h1>
      <h2>Gli studenti degli Atenei Italiani e il Futuro nell’IT</h2>
    </div>
    <h3>Estrazione Premi</h3>
    <div>
      <label for="min">Min:</label>
      <input type="number" v-model.number="min" id="min" />
    </div>
    <div>
      <label for="max">Max:</label>
      <input type="number" v-model.number="max" id="max" />
    </div>
    <button @click="generateRandomNumber">Generate Random Number</button>
    <div class="result-wrapper" v-if="randomNumber !== null">
      <div class="result">Random Number: <br> 
      <span class="result-number"> ✨ {{ randomNumber }} ✨</span> </div>
    </div>
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
  html, body { 
    margin: 0; 
    padding: 0;
    font-family: "Noto Sans", Helvetica, Arial, sans-serif;
  }
  #app {
    text-align: center;
  }
  .header { 
    background: url(./assets/img/bg.jpg); 
    background-position: center;
    height: 200px; 
    color: #fff;
  }
  .header h1 {
    margin: 0;
    padding-top: 1em;
    font-size: 2.75em;
  }
  .header h2 {
    margin: 0;
    font-weight: 500;
    font-size: 1.75em;
  }
  h3 {
    font-size: 1.75em;
  }
  label {
    margin-right: 10px;
    color: #666;
  }
  input[type=number] {
    width: 200px;
    padding: 12px 20px;
    margin: 8px 0 10px;
    display: inline-block;
    border: 1px solid #ccc;
    border-radius: 4px;
    box-sizing: border-box;
  }
  button {
    margin-top: 1em;
    padding: 15px 26px;
    font-size: 16px;
    cursor: pointer;
    background: #0093BD;
    color: #fff;
    border: none;
    border-radius: 4px;
  }
  .result-wrapper {
    font-size: 1.25em;
    margin-top: 2em;
  }
  .result-number {
    font-size: 2em;
  }
</style>