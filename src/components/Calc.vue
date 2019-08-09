<template>
  <div class="calculator">
    <div class="display">{{current || '0'}}</div>
    <div @click="clear" class="btn">C</div>
    <div @click="sign" class="btn">+/-</div>
    <div @click="percent" class="btn">%</div>
    <div id="div" @click="divide" class="btn operator">/</div>
    <div @click="append('7')" class="btn">7</div>
    <div @click="append('8')" class="btn">8</div>
    <div @click="append('9')" class="btn">9</div>
    <div id="t" @click="times" class="btn operator">x</div>
    <div @click="append('4')" class="btn">4</div>
    <div @click="append('5')" class="btn">5</div>
    <div @click="append('6')" class="btn">6</div>
    <div id="min" @click="minus" class="btn operator">-</div>
    <div @click="append('1')" class="btn">1</div>
    <div @click="append('2')" class="btn">2</div>
    <div @click="append('3')" class="btn">3</div>
    <div id="add" @click="add" class="btn operator">+</div>
    <div @click="append('0')" class="btn zero">0</div>
    <div @click="dot" class="btn">.</div>
    <div @click="equal" class="btn operator">=</div>
  </div>
</template>

<script>
export default {
    name:"calc",
  data() {
    return {
      previous: null,
      current: "",
      operator: null,
      operatorClicked: false
    };
  },
  methods: {
    clear() {
      this.current = "";
    },
    sign() {
      this.current =
        this.current.charAt(0) === "-"
          ? this.current.slice(1)
          : `-${this.current}`;
    },
    percent() {
      this.current = `${parseFloat(this.current) / 100}`;
      if (this.current==false){this.current=0};

    },
    append(number) {
      if (this.operatorClicked) {
        this.current = "";
        this.operatorClicked = false;
      }

if (this.current.length<8){
      this.current = `${this.current}${number}`;}
    },
    dot() {
      if (this.current.indexOf(".") === -1) {
        this.append(".");
      }
    },
    setPrevious() {
      this.previous = this.current;
      this.operatorClicked = true;
    },

    divide() {
      this.operator = (a, b) => a / b;
      this.setPrevious();
      document.getElementById("div").style.backgroundColor = "#f57a33";
    },
    times() {
      this.operator = (a, b) => a * b;
      this.setPrevious();
      document.getElementById("t").style.backgroundColor = "#f57a33";
    },
    minus() {
      this.operator = (a, b) => a - b;
      this.setPrevious();
      document.getElementById("min").style.backgroundColor = "#f57a33";
    },
    add() {
      this.operator = (a, b) => a + b;
      this.setPrevious();
      document.getElementById("add").style.backgroundColor = "#f57a33";
    },
    equal() {
      this.current = `${this.operator(
        parseFloat(this.previous),
        parseFloat(this.current)
      )}`;
      this.previous = null;
      var a = document.getElementsByClassName("operator");
      var i;
      for (i = 0; i < a.length; i++) {
        a[i].style.backgroundColor = "orange";
      }
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.calculator {
  width: 70%;
  margin-top: 30%;
  margin: 0 auto;
  font-size: 40px;
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  grid-auto-rows: minmax(50px, auto);
}

.display {
  grid-column: 1/5;
  background-color: black;
  color: white;
}

.zero {
  grid-column: 1/3;
}

.btn {
  background-color: #f2f2f2;
  border: 1px solid #999;
  cursor: pointer;
}

.operator {
  background-color: orange;
  color: white;
}
</style>