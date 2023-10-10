<script setup>
const {Income} = defineProps(['income'])
import { reactive } from 'vue';
const formData = reactive({
    desc:null,
    value:null,
    date:null
})

const formhandler  = ()=>{
Income.push({
  desc:formData.desc,
  value:formData.value,
  date:formData.date
})
}
</script>

<template>

<form action="" method="post" @submit.prevent="formhandler">
    <input type="text" 
    placeholder="Description..." 
    v-model="formData.desc"
    >
    <input type="number"
     name="amount" id="amount"
     placeholder="Amount"
     v-model="formData.value"
     >
    <input type="date" 
    name="incdate" id="incdate" 
    v-model="formData.date"
    >
    <input type="submit" 
    value="submit"
    >
</form>

<h3>{{ Income }}</h3>
</template>

<style scoped>
  form {
    display: flex;
    justify-content: center;
    margin-top: 30px;
  }

  form input {
    color: #191717;
    border: none;
    outline: none;
    font-size: 20px;
  }

  form input::placeholder {
    color: #000000;
  }

  form input:not([type="submit"]) {
    display: block;
    background: #FFF;
    border: none;
    outline: none;
    padding: 5px 15px;
  }

  form input[type="submit"] {
    display: block;
    background: none;
    border: none;
    outline: none;

    color: #FFF;
    font-weight: 500;
    text-shadow: 0px 1px 3px rgba(0, 0, 0, 0.2);
    padding: 5px 15px;
    background-color: #FFCE00;

    cursor: pointer;
  }

  form input:first-of-type {
    border-radius: 8px 0px 0px 8px;
  }

  form input:last-of-type {
    border-radius: 0px 8px 8px 0px;
  }
</style>