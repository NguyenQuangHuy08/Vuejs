<script setup>
import { ref } from 'vue';

// Bài tập 1

const isActive = ref(false)

const clickButton = () => {

  isActive.value = !isActive.value;
  console.log('Trạng thái của button: ', isActive.value)

}

// Bài tập 2

// Để giá trị mặc định cuả hộp là 100
const boxSize = ref(100);

</script>

<template>
  <div class="container">
    <div class="title">
      <h3 style="color: black;font: bold;">Bài tập lap2</h3>
    </div>
    <div class="bai1">
      <h5 style="margin-bottom: 30px;">Bài tập 1</h5>

      <!--  Bài tập 1: Sử dụng class binding để thay đổi giao diện theo trạng thái
    Tạo một thành phần vue đơn giản hiển thị một nút bấm, Khi nhấn nút, trạng thái
    của nút bấm sẽ thayy đổi giữa đã kích hoạt và chưa kích hoạt. Đồng thời màu nền
    cũng sẽ thay đổi tương ứng 
    Hướng dẫn: Tạo một biến isActive trong setup với ref() để lưu trạng thái kích 
    hoạt.Sử dụng Class Binding để thêm lớp active khi trạng thái là true.Sử dụng 
    điều kiện để thay đổi nội dung hiển thị của nút dựa trên giá trị của isActive
  -->
      <h6>Vui lòng nhấn button</h6>
      <button class="btn btn - success" @click="clickButton" :class="{ active: isActive }">{{ isActive ? 'Đã kích hoạt'
        : 'Chưa kích hoạt'
        }}</button>
      <hr>
      <div class="bai2">
        <h5 style="margin-bottom: 30px;">Bài tập 2</h5>
        <!-- 
        Sử dụng style binding để điều chỉnh kích thước hộp 
        Tạo một thành phần vue hiển thị một hộp vuông. Khi người dùng kéo thanh trượt, kích thước của
        hộp của hộp sẽ thay đổi tương ứng với giá trị của thanh trượt. Hướng dẫn. Tạo một biến boxsize 
        trong setup với ref để lưu giá trị kích thước của hộp. Sử dụng style binding để áp dụng giá trị 
        boxSize vào thuộc tính width và height
        -->
        <!-- 
          Chú ý: sử dụng v-model để lắng nghe sự thay đổi của sự kiện
        -->
        <h6>Vui lòng kéo thanh trượt</h6>
        <input type="range" min="100" :max="2000" v-model="boxSize">
        <div class="box" :style="{ width: boxSize + 'px', height: boxSize + 'px' }">
          <span>Giá trị của box : {{ boxSize }} px</span>
        </div>

      </div>
    </div>
  </div>
</template>

<style scoped>
.container {
  height: 100px;
  position: absolute;
  top: 0;
  left: 100px;
}

.title {

  margin-bottom: 70px;

}

/* Bài tập 1 */
button.active {
  background-color: red;

}

button:not(.active) {

  background-color: aquamarine;
}

/*  Bài tập 2 */
.box {

  background-color: lightblue;
  margin-top: 20px;
}
</style>
