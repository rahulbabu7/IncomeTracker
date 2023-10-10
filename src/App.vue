<script setup>
import { reactive,computed } from 'vue';
import Header from './components/Header.vue';
import Form from './components/Form.vue';
const state = reactive({
  income:[2000,3000,3203],
  totalIncome :computed(()=>{
    let sum = 0;
    if(state.income.length >0){
      //method 1 
      // for(let i =0;i<state.income.length;i++){
      //  sum += state.income[i];
      
      // }
      //! In for of loop the loop variable consist of the  array
      for (const i  of state.income) {
        sum +=i
      }
      return sum
    }
  })
})
</script>

<template>
<Header :totalIncome ="state.totalIncome" />  
<!-- passing the total income to the header component -->
<Form  :Income="state.income"/>
</template>

<style scoped>
*{
  margin: 0;
  padding: 0;
  box-sizing:border-box;
  font-family: 'Fira Sans' ,sans-serif;
}
body{
  background: #EEE;
}
</style>
