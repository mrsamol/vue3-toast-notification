<script setup>
  import {computed, ref } from 'vue'
  import { useHead } from '@vueuse/head'
  const siteData = ref({
      title: `My website`,
      description: `My beautiful website`,
  })
  useHead({
      // Can be static or computed
      title: computed(() => siteData.value.title),
      meta: [
        {
          name: `description`,
          content: computed(() => siteData.value.description),
        },
        ],
     
    })
</script>
<template>
  <div class="about">
    <h1>This is an about page</h1>
  </div>
</template>

<style>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}
</style>
