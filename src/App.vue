<script setup>
// import {ref} from 'vue';
// import planItem from './components/plan-picker-item.vue';
// const plans = ref(["El soltero","El adicto","El viajero","El colombiano"]);
import planPicker from './components/plan-picker.vue'; 
import {ref} from 'vue';
const showPlans = ref(true); //(se esta importando) Siempre especificar bien la ruta
</script>
 
<template>
<header>
<div>
<span id="logo">Liquid Gold Box</span>
<img src="./assets/logo.png" alt="logo">  
</div>
</header>
<div class="content">
<h1 class="title">Coffee Plans</h1>
<h2 class="subtitle">
      Viajamos por el mundo para encontrar el mejor café de origen único para ti
</h2>
 
    <!-- <div class="plans">
<plan-item v-for="plan in plans"
      :name="plan"
      v-bind:key="plan"/>
</div> -->
 <label> <input type ="checkbox" v-model="showPlans"/> Mostrar selector de planes ✈️🧳🗺️</label>
<plan-picker v-if="showPlans"/>
 
</div>
</template>
 
<style scoped>
header {
  line-height: 1.5;
}
 
.logo {
  display: block;
  margin: 0 auto 2rem;
}
 
@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }
 
  .logo {
    margin: 0 2rem 0 0;
  }
 
  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
