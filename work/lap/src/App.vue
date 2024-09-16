<script setup>
// import libraty reactive

import { ref, reactive } from 'vue';

// Bài tập 1
var numberIndex = ref(100);

const clickButtonIndexUp = () => {

  numberIndex.value++,
    console.log(numberIndex.value)

}

const clickResetNumberByIndex = () => {

  numberIndex.value = 100,
    console.log(numberIndex = ref(100))
}

//Bài tập 2

const dataHuman = ref({

  name: 'Nguyễn Văn Huy',
  age: '22',
  studenCode: 'PH26813',
  phoneNumber: '0373289304',
  email: 'znguyenvanhuy0803@gmail.com',

})


</script>

<template>
  <div class="container">
    <div>
      <h1 class="text-danger">Bài tập lap</h1>
    </div>

    <!-- Bài 1: Tạo ra 1 ref lưu trữ giá trị ban đầu là 100 và sau 
     đó tạo một nút botton click, mỗi click tăng thêm 1 đơn vị
      -->
    <div class="baiTap1">
      <h4>Bài tập 1</h4>
      <br>
      <span>Giá trị ban đầu : {{ numberIndex }}</span>
      <br>
      <button @click="clickButtonIndexUp" type="button" class="btn btn-primary" style="margin-top: 10px;">Submit
        up</button>
      <button @click="clickResetNumberByIndex" type="button" class="btn btn-primary"
        style=" margin-top: 10px;margin-left: 10px;">Submit reset</button>
    </div>
    <hr>
    <!-- Bài tập 2: Bài tập 2, hãy lưu dữ liệu cá nhân( tên, tuổi, mssv, sđt, email) và reactivity sau đó hiển thị ra ngoài giao diện -->
    <div class="baiTap2">
      <h4>Bài tập 2</h4>
      <br>
      <h6 style="color: black;">Name : {{ dataHuman.name }}</h6>
      <h6 style="color: black;">Age : {{ dataHuman.age }}</h6>
      <h6 style="color: black;">StudenCode : {{ dataHuman.studenCode }}</h6>
      <h6 style="color: black;">PhoneNumber : {{ dataHuman.phoneNumber }}</h6>
      <h6 style="color: black;">Email : {{ dataHuman.email }}</h6>

    </div>
  </div>
</template>

<style scoped></style>