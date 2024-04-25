<template>
  <h1 class="titles">
    <div class="description">
      <span class="title">{{ name }}</span>
    </div>
  </h1>
</template>

<script setup>
import { defineProps } from 'vue';

const title = defineProps({
  name: { type: String }
});
</script>

  