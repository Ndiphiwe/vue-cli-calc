<template>
<div class="container">
  <div class="dsply">
  <Output :sum="sum"/>
  <Operators v-for="operator of operators" :key="operator" :operator="operator" @add="addToSum(operator)"/>
  <button @click="evalSum()" class="btn-warning">=</button>
  <button @click="deleteSum()" class="btn-success">DEL</button>
  <button @click="clearSum()" class="btn-danger">CLR</button>
  </div>
</div>
</template>

<script>
import Output from './components/Output.vue'
import Operators from './components/Operators.vue'
import './assets/global.css'
export default {
  name: 'App',
  components: {
    Output,
    Operators
  },
  data() {
        return {
            sum: "",
            operators: [
                    "1",
                    "2",
                    "3",
                    "4",
                    "5",
                    "6",
                    "7",
                    "8",
                    "9",
                    "0",
                    "+",
                    "-",
                    "*",
                    "/",
                    ".",
            ]
        }
    },
    methods: {
      addToSum(operators){
        this.sum += operators
      },
      clearSum(){
        this.sum = ""
      },
      evalSum(){
        this.sum = eval(this.sum)
      },
      deleteSum(){
        this.sum = this.sum.slice(0, -1)
      }
    },
}
</script>

<style>
#app {
  /* font-family: Avenir, Helvetica, Arial, sans-serif; */
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 10vh;
}
</style>
