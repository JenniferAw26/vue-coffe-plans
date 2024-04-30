<template>
  <div ref="plansWrapper" class="plans">
  <plan-picker-item
  @select="printSelected"
  :selected-plan="selectedPlan"
        v-for="plan in plans"
        :name="plan"
        v-bind:key="plan"/>
        <p>Counter: {{ counter }}</p>
  </div>
  </template>
   
  <script setup>
  import {ref, onMounted, onUnmounted} from 'vue';
  import planPickerItem from './plan-picker-item.vue';
  const plans = ref([
  "El soltero",
  "El adicto",
  "El viajero"]);

  const plansWrapper=ref(null);
  const selectedPlan= ref(null);

  const printSelected=(playload) => {
    selectedPlan.value=playload;
  }

  //Creando una referencia reactiva para un contador 
  const counter= ref(0);
   const processId = setInterval(() =>{
    console.log('Incrementando contador⏲️')
    counter.value++;
  },1000);

  ///Registrando el CB(Call back) onMounted
  onMounted(()=>{
      //Obteniendo la referencia del elemento plans
//console.log (plansWrapper.value);
console.log ('Componente Plan Picker montado✅');
  });

  //Registrando el unMounted
  onUnmounted(()=>
{
  console.log('Comnponente Plan Picker desmontado ❎');
  clearInterval(processId);
});


  </script>

  