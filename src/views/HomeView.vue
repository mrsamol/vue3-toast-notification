<script setup>
import TheWelcome from '../components/TheWelcome.vue'
import {computed, ref } from 'vue'
  import { useHead } from '@vueuse/head'
  const siteData = ref({
      title: `Home`,
      description: `Beautiful Home`,
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
  <main>
    <TheWelcome />
  </main>
</template>
