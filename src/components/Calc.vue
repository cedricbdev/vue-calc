<template>
  <div id="main">
    <div id="calc">
      <calc-screen :value="screenText"></calc-screen>
      <calc-key
        v-for="calcKey in calcKeys"
        :key="calcKey.id"
        :id="`key-${calcKey.id}`"
        :class="`key key-${calcKey.className}`"
        :keyData="calcKey"
        @clicked="keyPressed"
      >
      </calc-key>
    </div>
    <calc-buffer :buffer="buffer"></calc-buffer>
  </div>
</template>

<script>
import CalcScreen from "./CalcScreen";
import CalcKey from "./CalcKey";
import CalcBuffer from "./CalcBuffer";

const calcKeys = [
  { id: "modulo", className: "operation", value: "%" },
  { id: "divide", className: "operation", value: "÷" },
  { id: "multiply", className: "operation", value: "×" },
  { id: "minus", className: "operation", value: "−" },
  { id: "plus", className: "operation", value: "+" },
  { id: "equals", className: "operation", value: "=" },
  { id: "ce", className: "operation", value: "CE" },
  { id: "dot", className: "number", value: "," },
  { id: "0", className: "number", value: "0" },
  { id: "1", className: "number", value: "1" },
  { id: "2", className: "number", value: "2" },
  { id: "3", className: "number", value: "3" },
  { id: "4", className: "number", value: "4" },
  { id: "5", className: "number", value: "5" },
  { id: "6", className: "number", value: "6" },
  { id: "7", className: "number", value: "7" },
  { id: "8", className: "number", value: "8" },
  { id: "9", className: "number", value: "9" }
];

export default {
  name: "Calc",
  components: {
    CalcKey,
    CalcScreen,
    CalcBuffer
  },
  data() {
    return {
      msg: "Welcome to Your Vue.js App",
      buffer: [],
      calcKeys
    };
  },
  computed: {
    screenText() {
      return this.buffer.reduce((accumulator, currentValue) => {
        return (accumulator += currentValue);
      }, "");
    }
  },
  methods: {
    keyPressed(keyData) {
      switch (keyData.id) {
        case "ce":
          console.clear();
          this.buffer = [];
          break;
        default:
          this.buffer.push(keyData.value);
      }
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
* {
  box-sizing: border-box;
}

#calc {
  width: 200px;
  height: 300px;
  position: relative;
  border: 2px solid #ebebeb;
  box-shadow: 0 0 25px rgba(0, 0, 0, 0.1);
  box-sizing: content-box;
  background-color: #e9e9e9;
}
.key {
  width: 50px;
  height: 50px;
  text-align: center;
  line-height: 50px;
  display: block;
  position: absolute;
  cursor: pointer;
  border: 2px solid #ebebeb;
}
.key-number {
  background: #fafafa;
  color: rgba(0, 0, 0, 0.7);
  font-weight: bold;
}
.key-number:hover {
  background: rgba(0, 0, 0, 0.1);
  color: rgba(0, 0, 0, 0.9);
}
.key-operation {
  background: #f1f1f1;
  color: rgba(0, 0, 0, 0.7);
}
.key-operation:hover {
  background: rgba(0, 0, 0, 0.25);
  color: rgba(0, 0, 0, 0.9);
}

#key-modulo {
  bottom: 200px;
  left: 0;
}
#key-divide {
  bottom: 200px;
  left: 50px;
}
#key-multiply {
  bottom: 200px;
  left: 100px;
}
#key-minus {
  bottom: 200px;
  left: 150px;
}
#key-plus {
  bottom: 100px;
  left: 150px;
  height: 100px;
  line-height: 100px;
}
#key-equals {
  height: 100px;
  bottom: 0;
  left: 150px;
  line-height: 100px;
}
#key-dot {
  bottom: 0;
  left: 100px;
}
#key-ce {
  bottom: 0;
  left: 0;
}
#key-0 {
  bottom: 0;
  left: 50px;
}
#key-1 {
  bottom: 50px;
  left: 0;
}
#key-2 {
  bottom: 50px;
  left: 50px;
}
#key-3 {
  bottom: 50px;
  left: 100px;
}
#key-4 {
  bottom: 100px;
  left: 0;
}
#key-5 {
  bottom: 100px;
  left: 50px;
}
#key-6 {
  bottom: 100px;
  left: 100px;
}
#key-7 {
  bottom: 150px;
  left: 0;
}
#key-8 {
  bottom: 150px;
  left: 50px;
}
#key-9 {
  bottom: 150px;
  left: 100px;
}
</style>
