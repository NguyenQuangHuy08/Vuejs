<script setup>
  // Tạo tiêu đề
  const title = 'Huy Nguyen';
  
  // Object chứa các thuộc tính cho div
  const box = {
    id: 'myBox',
    class: 'box-class',
    style: {
      width: '300px',
      height: '300px',
      border: '1px solid black',
      display: 'flex',
      justifyContent: 'center',
      alignItems: 'center',
      textAlign: 'center'
    }
  };

  // Buổi 2: Demo 


</script>

<template>
  <h1>{{ title }}</h1>
  <div :id="box.id" :class="box.class" :style="box.style">
    Nguyễn Quang Huy
  </div>
  <!--Buổi 2 Demo bootstrap -->
  <div class="text-danger">
      text-primary
  </div>


</template>

<style>
  .box-class {
    background-color: #f0f0f0;
  }
</style>
