<template>
  <img alt="Calculator logo" src="./assets/calculator.png">
 
  <h1>Compute Product</h1>
  <div>
    <label for num1>Number 1: </label>
    <input type="number" v-model="num1"/>
  </div>
  <br>
  <div>
    <label for num2>Number 2: </label>
    <input type="number" v-model="num2"/>
  </div>
  <br>
  <button v-if="showButton" @click="multiplyNumbers">Multiply</button>
  <br><br>
  <div v-if="!showButton">
    <label for result>Result: </label>
    <input  type="result" v-model="result" readonly/>
  </div>

</template>

<script>
import {ref} from 'vue'
export default{
  setup(){
    const num1 = ref(0)
    const num2 = ref(0)
    const result = ref(0)
    const showButton = ref(true)

    const multiplyNumbers = () => {
      
      showButton.value = false;
      result.value = num1.value * num2.value;
    }
    return {
      num1, num2, result, showButton, multiplyNumbers
    }
  }
  
}

</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
