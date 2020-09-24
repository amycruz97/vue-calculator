<template>
  <div class="calculator">
    <!-- <input type="text" class="calculator-screen" value="" v-model="currentValue" disabled /> -->
    <div class="display">{{ display }}</div>

    <div class="calculatorKeys">
      <button type="button" class="clear" value="clear" @click="clear">
        C
      </button>
      <button type="button" class="" value="(" @click="append">(</button>
      <button type="button" class="" value=")" @click="append">)</button>
      <button type="button" class="operator" value="/" @click="divide">
        &divide;
      </button>

      <button type="button" value="7" @click="append(7)">7</button>
      <button type="button" value="8" @click="append(8)">8</button>
      <button type="button" value="9" @click="append(9)">9</button>
      <button type="button" class="operator" value="x" @click="multiply">
        &times;
      </button>

      <button type="button" value="4" @click="append(4)">4</button>
      <button type="button" value="5" @click="append(5)">5</button>
      <button type="button" value="6" @click="append(6)">6</button>
      <button type="button" class="operator" value="-" @click="subtract">
        -
      </button>

      <button type="button" value="1" @click="append(1)">1</button>
      <button type="button" value="2" @click="append(2)">2</button>
      <button type="button" value="3" @click="append(3)">3</button>
      <button type="button" class="operator" value="+" @click="add">+</button>

      <button type="button" value="0" @click="append(0)">0</button>
      <button type="button" value="%" @click="percent">%</button>
      <button type="button" class="decimal" value="." @click="decimal">
        .
      </button>
      <button type="button" class="equal-sign" value="=" @click="equal">
        =
      </button>
    </div>
  </div>
</template>

<script>
export default {
  name: "calculator",
  data() {
    return {
      display: 0,
      operator: null,
      operatorClicked: false,
      previous: null,
    };
  },

  methods: {
    clear() {
      this.display = 0;
    },
    percent() {
      this.display = this.display / 100;
    },
    append(number) {
      if (this.operatorClicked === true) {
        this.display = "";
        this.operatorClicked = false;
      }
      this.display =
        this.display === 0
          ? (this.display = number)
          : "" + this.display + number;
    },

    divide() {
      this.operator = (a, b) => a / b;
      this.previous = this.display;
      this.operatorClicked = true;
    },
    add() {
      this.operator = (a, b) => a + b;
      this.previous = this.display;
      this.operatorClicked = true;
    },
    multiply() {
      this.operator = (a, b) => a * b;
      this.previous = this.display;
      this.operatorClicked = true;
    },
    subtract() {
      this.operator = (a, b) => a - b;
      this.previous = this.display;
      this.operatorClicked = true;
    },

    decimal() {
       if (this.display.indexOf('.') === -1) {
        this.append('.');
      }
    },

     equal() {
       this.display = this.operator(Number(this.previous), Number(this.display));
      this.previous = null;
      this.operatorClicked = true;
     },
  },
};
</script>

<style scoped>
.calculator {
  /* background-color: #0f0f0f; */
  background-color: white;
  width: 350px;
  height: 700px;
  margin: 0 auto;
  border-radius: 4rem;
  padding: 3rem;
  box-shadow: 0 10px 20px rgba(0, 0, 0, 0.2), 0 2px 20px rgba(0, 0, 0, 0.2),
    0 4px 40px rgba(0, 0, 0, 0.2), 0 8px 8px rgba(0, 0, 0, 0.2),
    0 16px 20px rgba(0, 0, 0, 0.2);
}

.display {
  background-color: #000;
  border: 1px solid #000;
  width: 300px;
  height: 15%;
  margin-top: 5rem;
  color: #fff;
  font-size: 4rem;
  text-align: right;
  padding: 2rem;
}
.calculatorKeys {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  grid-row-gap: 20px;
  grid-column-gap: 20px;
  margin-top: 8rem;
}

button {
  height: 60px;
  background-color: #000;
  border: 1px solid #000;
  border-radius: 50%;
  font-size: 2rem;
  color: #fff;
  box-shadow: 0px 15px 10px -10px rgba(0, 0, 0, 1);
  cursor: pointer;
  transition: all ease-in-out 300ms;
  outline: none;
}

button:hover {
  box-shadow: 0px 37px 20px -20px rgba(0, 0, 0, 0.2);
  transform: translate(0px, -10px) scale(1.2);
  padding: 2px;
}

.operator {
  color: #f0595f;
}

.clear {
  color: #f0595f;
}

.equal-sign {
  color: #f0595f;
}


</style>
