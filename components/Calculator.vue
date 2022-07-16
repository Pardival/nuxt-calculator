<template>
    <div class="calculator">
      <div class="calculator-display">
        <div>
          <span class="calculator-display-value">{{leftValue}} {{operator}} {{rightValue}} = {{result}}</span>
        </div>
      </div>
      <div class="calculator-number">
        <v-row>
          <v-col cols="3"><v-btn elevation="2" @click='parseNumber("1")'>1</v-btn></v-col>
          <v-col cols="3"><v-btn elevation="2" @click='parseNumber("2")'>2</v-btn></v-col>
          <v-col cols="3"><v-btn elevation="2" @click='parseNumber("3")'>3</v-btn></v-col>
          <v-col cols="3"><v-btn elevation="2" @click='parseOperator("+")'>+</v-btn></v-col>
        </v-row>
        <v-row>
          <v-col cols="3"><v-btn elevation="2" @click='parseNumber("4")'>4</v-btn></v-col>
          <v-col cols="3"><v-btn elevation="2" @click='parseNumber("5")'>5</v-btn></v-col>
          <v-col cols="3"><v-btn elevation="2" @click='parseNumber("6")'>6</v-btn></v-col>
          <v-col cols="3"><v-btn elevation="2" @click='parseOperator("-")'>-</v-btn></v-col>
        </v-row>
        <v-row>
          <v-col cols="3"><v-btn elevation="2" @click='parseNumber("7")'>7</v-btn></v-col>
          <v-col cols="3"><v-btn elevation="2" @click='parseNumber("8")'>8</v-btn></v-col>
          <v-col cols="3"><v-btn elevation="2" @click='parseNumber("9")'>9</v-btn></v-col>
          <v-col cols="3"><v-btn elevation="2" @click='parseOperator("x")'>x</v-btn></v-col>
        </v-row>
        <v-row>
          <v-col cols="3"><v-btn elevation="2" @click="clear()">CE</v-btn></v-col>
          <v-col cols="3"><v-btn elevation="2" @click='parseNumber("0")'>0</v-btn></v-col>
          <v-col cols="3"><v-btn elevation="2" @click="determine()">=</v-btn></v-col>
          <v-col cols="3"><v-btn elevation="2" @click='parseNumber("/")'>/</v-btn></v-col>
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
    name:'CalculatorPage',
    data() {
        return {
        leftValue: "",
        rightValue: "",
        operator: "",
        result: "", 
        }
    },
    methods: {
        determine() {
            if (this.operator === '+') {
                this.result = parseInt(this.leftValue) + parseInt(this.rightValue);
            } else if (this.operator === '-') {
                this.result = parseInt(this.leftValue) - parseInt(this.rightValue);
            } else if (this.operator === 'x') {
                this.result = parseInt(this.leftValue) * parseInt(this.rightValue);
            } else if (this.operator === '/') {
                this.result = parseInt(this.leftValue) / parseInt(this.rightValue);
            }
        },
        clear() {
            this.leftValue = "";
            this.rightValue = "";
            this.operator = null;
            this.result = null;
        },
        parseNumber(value) {
            if (this.operator === "") {
                this.leftValue += value;
            } else {
                this.rightValue += value;
            }
        },
        parseOperator(value) {
            if (this.leftValue !== null) {
                this.operator = value;
            }
        }
    }
})
</script>