<script setup>
import { onMounted, ref } from 'vue'
import HelloWorld from './components/HelloWorld.vue'

const prompts = ref([])

onMounted(() => {
  fetch('http://localhost:8000/api/v1/prompt-generations', {
    headers: {
      'Content-Type': 'application/json',
      'Accept': 'application/json',
      'Authorization': `Bearer 8|t6UElHGIyrlmBIIvrJGc3Wv9Gd61Z6V0WfqLfqtC025a180f`
    }
  })
  
  .then(response => response.json())
  .then($result => {
    debugger;
    prompts.value = result.data
  })
})
</script>

<template>
  <HelloWorld />
</template>
