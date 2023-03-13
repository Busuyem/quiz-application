<script setup>
  import { RouterView } from 'vue-router';
</script>

<template>
    <div class="container">
        <RouterView />
    </div>
</template>

<style scoped>
.container{
  max-width: 1000px;
  margin: 0 auto;
  margin-bottom: 10px;
  margin-top: 30px;
}
</style>