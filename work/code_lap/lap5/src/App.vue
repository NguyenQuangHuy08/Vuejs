<script setup>
import { onMounted } from 'vue';
import HomeView from './components/HomeView.vue';
onMounted(() => {
  document.title = 'Xin chào';
})
</script>
<template>
  <div class="container">
    <div class="header">
      <HomeView title="Home view" />
    </div>
    <div class="body">
      <h6>Nội dung</h6>
    </div>
  </div>
</template>
<style scoped>
.container {
  max-width: 1200px;
  position: relative;
  border: 1px solid none;
  width: 1200px;
  height: 900px;
}

.body {
  margin-top: 30px;
}
</style>
