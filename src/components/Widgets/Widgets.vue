<script setup>
defineProps({
  title: String,
  value: Number,
  description: String
})
</script>

<template>
  <div class="widget">
    <h3>{{ title }}</h3>

    <div class="value">
      {{ value }}
    </div>

    <p>{{ description }}</p>
  </div>
</template>