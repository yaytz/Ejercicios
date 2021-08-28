<template>

  <div class="calculadora">
  <input type="number">
  
  <div class="calculadora-body"> 
  <button class="button">/</button>
  <button class="button">(</button>
  <button class="button">)</button>
  <button class="button">C</button>
  <button class="button">1</button>
  <button class="button">2</button>
  <button class="button">3</button>
  <button class="button">+</button>
  <button class="button">4</button>
  <button class="button">5</button>
  <button class="button">6</button>
  <button class="button">-</button>
  <button class="button">7</button>
  <button class="button">8</button>
  <button class="button">9</button>
  <button class="button">=</button>
  </div>
  </div>
</template>


<script setup>
import { defineProps, reactive } from 'vue'

defineProps({
  msg: String
})

const state = reactive({ count: 0 })
</script>

<style scoped>
a {
  color: #10b9be;
}

</style>
<style scoped>
.calculadora input{
  background: #b9d2d3;
  max-width: 450px;
  margin: 0 auto;
  border: 10px solid #111;
  border-radius: 15px;
  text-align: left;
}
.button{
  background: rgba(0, 0, 0, 0.5);
  border: 1px solid #111; 
  padding: 20px;
  color: #EEE;
  border-radius: 10px; 
  font-size: 22px; 
  cursor: pointer; 
}
.calculadora-body{
  background: #009196;
  padding: 20px;
  display: grid;
  grid-template-columns: 1fr 1fr 1fr 1fr;
  grid-gap: 20px;
}
.calculadora{
  background: #247b7e;
  max-width: 400px;
  margin: 0 auto;
  border: 2px solid #111;
  border-radius: 5px;}
</style>