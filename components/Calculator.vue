<template>
    <div class="calculator">
      <div class="calculator-display">
        <div>
          <span class="calculator-display-value">0</span>
        </div>
      </div>
      <div class="calculator-number">
        <v-row>
          <v-col cols="3"><v-btn elevation="2">1</v-btn></v-col>
          <v-col cols="3"><v-btn elevation="2">2</v-btn></v-col>
          <v-col cols="3"><v-btn elevation="2">3</v-btn></v-col>
          <v-col cols="3"><v-btn elevation="2">+</v-btn></v-col>
        </v-row>
        <v-row>
          <v-col cols="3"><v-btn elevation="2">4</v-btn></v-col>
          <v-col cols="3"><v-btn elevation="2">5</v-btn></v-col>
          <v-col cols="3"><v-btn elevation="2">6</v-btn></v-col>
          <v-col cols="3"><v-btn elevation="2">-</v-btn></v-col>
        </v-row>
        <v-row>
          <v-col cols="3"><v-btn elevation="2">7</v-btn></v-col>
          <v-col cols="3"><v-btn elevation="2">8</v-btn></v-col>
          <v-col cols="3"><v-btn elevation="2">9</v-btn></v-col>
          <v-col cols="3"><v-btn elevation="2">x</v-btn></v-col>
        </v-row>
        <v-row>
          <v-col cols="3"><v-btn elevation="2">CE</v-btn></v-col>
          <v-col cols="3"><v-btn elevation="2">0</v-btn></v-col>
          <v-col cols="3"><v-btn elevation="2">=</v-btn></v-col>
          <v-col cols="3"><v-btn elevation="2">/</v-btn></v-col>
        </v-row>
      </div>
    </div>
</template>
<style scoped>
.calculator {
    background-color: #006d77;
    width: 400px;
    height: 300px;
    border-radius: 10px;
    padding:10px;
  }

  .calculator-display {
    width: 100%;
    height: 45px;
    display: flex;
    justify-content: right;
    align-items: center;
    background-color: #edf6f9;
    border-radius: 10px;
    padding: 5px;
  }

  .calculator-number {
    margin-top: 10px;
  }

  .color  {
    background-color: #83c5be;
  }
</style>

<script>
export default ({
    name:'CalculatorPage'
})
</script>