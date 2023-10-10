<script setup>
const {totalIncome} = defineProps(['totalIncome'])

</script>

<template>
    <header>
        <h1>
    Income Tracker
</h1>
<div class="total-income">
    <h3  v-if="totalIncome>0">
        RS:{{ totalIncome }}
    </h3>
    <h3 v-else>
        RS:0
    </h3>
   
</div>
    </header>

</template>

<style scoped>
header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 15px 30px;
  background-color: #313131;
  border-bottom: 5px solid #FFCE00;
}

header h1 {
  color: #EEE;
  font-size: 28px;
}

header .total-income {
  font-family: 'Fira Code', 'Fira Sans', sans-serif;
  background-color: #FFCE00;
  color: #FFF;
  font-size: 16px;
  font-weight: 900;
  padding: 5px 10px;
  min-width: 100px;
  text-align: center;
  border-radius: 80px;
  box-shadow: inset 0px 0px 6px rgba(0, 0, 0, 0.25);
  text-shadow: 0px 3px 3px rgba(0, 0, 0, 0.25);
}
/* header .total-income  h3{
   
    
} */
</style>