<script setup>
import FancyButton from './components/FancyButton.vue';
</script>
 
<template>
<FancyButton>
    <template v-slot:icon="slotProps">{{ slotProps.hover ? '🚀': '🪅'}}</template> 
    <template v-slot:default>Enviar  
    </template>
    </FancyButton>

    
<FancyButton>
    <template v-slot:icon="{hover}">
        {{ hover ? '🚀': '🪅'}}
    </template>
    <template v-slot:default>
        <strong> Cancelar </strong>
    </template>
</FancyButton>
</template>
 
<style scoped>

</style>
