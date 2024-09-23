<script setup>

import { ref } from 'vue';

// Bài 1

// Cách 1
const nameUsers = ref([

  'Nguyễn Quang Huy',
  'HuyBg08',
  'Nguyễn Văn Huy',
  'Nguyễn Thị Loan'

])

//Cách 2

const nameUsers2 = ref([

  { name: 'Nguyễn Quang Huy' },
  { name: 'Nguyễn Thị Loan' },
  { name: 'HuyBg08' }
])

// Bài 2

const todoLists = ref([

  { name: 'Code Java', completed: true },
  { name: 'Code C#', completed: false },
  { name: 'Code C++', completed: true },
  { name: 'Code Angular', completed: true },
  { name: 'Code Vue', completed: true },
])


// Cách 1
// const clickButtonTodoList = (index) => {

//   todoLists.value
//   todoLists.value[index].completed = !todoLists.value[index].completed;
//   console.log(todoLists.value(index).completed)
// }

//Cách 2
const setCompleted = (index, completed) => {
  todoLists.value[index].completed = completed;
  console.log(todoLists.value[index].completed)
};

</script>

<template>
  <div class="container">
    <div class="title">
      <h3>Bài tập lap 3</h3>
    </div>
    <div class="ba1">
      <h5 style="margin-top: 30px;">Bài tập 1</h5>
      <!-- Hiển thị danh sách các tên người dùng  từ một mảng dữ liệu. Mỗi tên sẽ được
       hiển thị trong một thẻ li>. Hướng dẫn khởi tạo một mảng users trong setup với một
       số tên người dùng. Sử dụng v-for để hiển thị tên sách người dùng-->
      <div class="cach1">
        <!-- Khởi tạo v-for tên biến và giá trị ban đầu ở trong mảng sau đó key -->
        <p style="margin-top: 20px;color: black;font-weight: bold;">Cách 1</p>
        <li v-for="(user, index) in nameUsers" :key="index">
          {{ user }}
        </li>
      </div>
      <div class="cach2">
        <span style="margin-top: 20px;color: black;font-weight: bold;">Cách 2</span>
        <li v-for="item in nameUsers2">
          {{ item.name }}
        </li>
      </div>
    </div>
    <hr>
    <div class="bai2">
      <h5 style="margin-top: 30px;">Bài tập 2</h5>
      <!-- Bài tập 2: Danh sách công việc với trạng thái hoàn thành. Tạo một danh sách công việc
       to do list. Mỗi công việc có thể dánh dấu là đã hoàn thành hoặc chưa hoàn thành. Công việc
       đã hoàn thành sẽ được hiển thị với dấu gạch ngang. Hướng dẫn. khởi tạo một mảng todo list
       chứa các đối tượng công việc (mỗi công việc có title và completed).Sử dụng v-for để hiển 
       thị danh sách công việc.Sử dụng Class Binding hoặc Style Binding để thay đổi kiểu dáng của
        công việc đã hoàn thành.Thêm một nút để đánh dấu một công việc là hoàn thành hoặc chưa 
        hoàn thành.-->
      <span>Danh sách công việc</span>
      <div class="">
        <li v-for="(list, index) in todoLists" :key="index">
          <span class="span" :class="{ active: list.completed }">{{ list.name }}</span>
          <!-- check -->
          <input style="margin-left: 100px;" type="radio" :checked="list.completed"
            @change="setCompleted(index, true)" />
          <label>Hoàn thành</label>

          <input type="radio" :checked="!list.completed" @change="setCompleted(index, false)" />
          <label>Chưa hoàn thành</label>
        </li>
      </div>
    </div>
  </div>
</template>

<style scoped>
.container {

  position: absolute;
  top: 0px;
  left: 10px;

}

li>* {

  padding: 10px;
  margin: 10px;
}

/* Bài 2 */

.span.active {

  font-weight: bold;
  color: black;

}

.span:not(.active) {

  font-weight: bold;
  color: red;
}
</style>
