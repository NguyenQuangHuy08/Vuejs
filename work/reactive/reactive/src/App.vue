<script setup>
import { ref, reactive } from 'vue';
//--------------------------------------
/*
  B1: Khởi tạo biến đếm và truyền vào giá trị index
  B2: Xây dựng hàm như funtion để chuyển đổi
  B3: Nhận thông tin và lấy giá trị

  
*/

var count = ref(0)
const incement = () => {

  count.value++
  console.log(count.value)

}


//--------------------------------

/*
  B1: Xây dụng dối tượng data có thể thay đổi lắng nghe dưới sự của ref
  B2: xây dụng hàm 
*/
const changeName = ref({

  name: 'Huy Nguyễn',
  age: '22',
  hobbies: {
    name: 'coding',
    time: '14'

  }

})

const handeChangeName = () => {

  changeName.value.hobbies.name = 'anh'

}


// -------------------------
// Làm việc với kiểu dữ liệu phức tạp với reactive ()

const number = reactive({ count: 0 })

const inrrecreactive = () => {
  number.count++,
    console.log(number.count)

}

</script>

<template>
  <div>
    <!-- Ví dụ 1 -->
    <div class="ref">
      <h1>anh yêu</h1>
      <h1 class="text-danger">tại sao</h1>
      {{ count }}
      <button @click="incement">Click</button>
    </div>
    <!-- Ví dụ 2 -->
    <div class="deep reactive">
      <h3>Ví dụ về Deep Reacting</h3>
      <div>{{ changeName.name }}, {{ changeName.age }}</div>
      <div>{{ changeName.hobbies.name }}, {{ changeName.hobbies.time }}</div>
      <button @click="handeChangeName">Change name</button>
    </div>
    <!-- Ví dụ 3 làm việc với dữ liệu phức tạp reactive -->
    <div class="reactive">
      <h3>Ví dụ reactive</h3>
      <div>{{ number.count }}</div>
      <button @click="inrrecreactive">Change number reactive</button>
    </div>

    <!-- 
  // Bài tập 1, Tao 1 ref lưu trữ giá ban đầu là 100, và sau do tạo 1 nut button click, mỗi lần click tăng thêm 1 đơn vị
// Bài tập 2, hãy lưu dữ liệu cá nhân( tên, tuổi, mssv, sđt, email) và reactivity sau đó hiển thị ra ngoài giao diện  
  -->

  </div>
</template>

<style scoped></style>
