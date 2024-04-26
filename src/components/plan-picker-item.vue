<template>
   <div @click="select" 
   :class="{'selected-plan':isSelected}"
   class="plan">
        <div class="description">
          <span class="title">  
            {{ name }} 
          </span>
        </div>
      </div>
</template>

<script setup>

import {computed} from 'vue';
//import {ref} from 'vue';
//Crear un evento en setup 

//Crea propiedad seleted plan
const emit= defineEmits(['select']);
const props= defineProps({
  name: {type: String, 
    required: true,
  },
    selectedPlan:{
      type: String
    },
});

//Definir una variable, permitiendo a cada item saber si a sido seleccionada o no
//const selected = ref(false);
//metodo para cambiar a true
const select = ()=> {
  //selected.value=true
    //Detonando el evento
  emit ('select', props.name);
}
//Macro es una funcion especialidad en vue que me permite crear defineProps (que ya las importa), no se tiene que intregrar porque Vue ya lo hace, para agregar  nombre propiedades siempre usar camelcasing
//Esquema de propiedades de manera mas avanzada (objeto), las propiedades van dentro de las llaves {} 
//con el objetivo de proveer un objeto, no un arreglo

//propiedad computada

const isSelected = computed(() => {
  return props.name === props.selectedPlan;
});
</script>

<style scoped>
.selected-plan{
  background-color:darkkhaki;
}
</style>


