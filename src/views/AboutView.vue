<template>
  <div class="about">
    <TheAbout />
  </div>
</template>

<script setup lang="ts">
    import TheAbout from '../components/TheAbout.vue'

</script>

<style>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}
</style>
