<script setup>
import { ref, reactive } from 'vue';

const books = reactive([
  {
    id: 1,
    name: 'THeaderCode',
    author: 'Lê Văn Hiên',
    isActive: true,
    shippingInfor: {
      location: 'VN',
      address: {
        street: '123',
        city: 'DaNang'
      },
      code: '123'
    },
  },
  {
    id: 2,
    name: 'Network',
    author: 'Nguyen Van B',
    isActive: false,
    shippingInfor: {
      location: 'VN',
      address: {
        street: '123',
        city: 'HCM'
      },
      code: '123'
    },
  }, {
    id: 3,
    name: 'Data Science',
    author: 'Nguyen Van A',
    isActive: false,
    shippingInfor: {
      location: 'VN',
      address: {
        street: '123',
        city: 'Hn'
      },
      code: '123'
    },
  }
])


</script>

<template>
  <div class="container">
    <div class="title">
      <h5>Bài tập lap 4</h5>
    </div>
    <div class="body">
      <!-- 
  1. Hiển thị toàn bộ thông tin của các đối tượng book trong mảng,
2. Chỉ Hiển thị các đối tượng book có isActive = true
3.Chỉ Hiện thị các đối tượng có address HCM      

-->
      <div class="box1">
        <h6>- Hiển thị thông tin của đối tượng book trong mảng</h6>
        <div>
          <li class="books" v-for="item in books">
            <div style="margin-left: 20px;">
              <p>Name: {{ item.name }}</p>
              <p>Author: {{ item.author }}</p>
              <p>Active: {{ item.isActive }}</p>
              <p>Location : {{ item.shippingInfor.location }}</p>
              <p>Street: {{ item.shippingInfor.address.street }}</p>
              <p>City : {{ item.shippingInfor.address.city }}</p>
              <p>Code : {{ item.shippingInfor.code }}</p>
            </div>
          </li>
        </div>
      </div>
      <hr>
      <div class="box2" style="margin-top: 30px;">
        <h6>- Chỉ hiển thị các đối tượng books có isActive = true</h6>
        <!-- Cách 1 -->
        <p style="font-weight: bold;color: black;">Cách 1</p>
        <div class="cach1">
          <div v-for="item in books">
            <div v-if="item.isActive">
              <p>Name: {{ item.name }}</p>
              <p>Author: {{ item.author }}</p>
              <p>Active: {{ item.isActive }}</p>
              <p>Location : {{ item.shippingInfor.location }}</p>
              <p>Street: {{ item.shippingInfor.address.street }}</p>
              <p>City : {{ item.shippingInfor.address.city }}</p>
              <p>Code : {{ item.shippingInfor.code }}</p>
              <p>------------------------------------------</p>
            </div>
          </div>
        </div>
        <p style="font-weight: bold;color: black;">Cách 2</p>
        <div class="cach2">
          <div v-for="item in books.filter(book => book.isActive)">
            <p>Name: {{ item.name }}</p>
            <p>Author: {{ item.author }}</p>
            <p>Active: {{ item.isActive }}</p>
            <p>Location : {{ item.shippingInfor.location }}</p>
            <p>Street: {{ item.shippingInfor.address.street }}</p>
            <p>City : {{ item.shippingInfor.address.city }}</p>
            <p>Code : {{ item.shippingInfor.code }}</p>
            <p>------------------------------------------</p>
          </div>
        </div>
      </div>
      <hr>
      <div class="box3">
        <h6>- Chỉ hiển thị các đối tượng books có adress là HCM</h6>
        <!-- Cách 1 -->
        <p style="font-weight: bold;color: black;">Cách 1</p>
        <div class="cach1">
          <div v-for="item in books">
            <div v-if="item.shippingInfor.address.city === 'HCM'">
              <p>Name: {{ item.name }}</p>
              <p>Author: {{ item.author }}</p>
              <p>Active: {{ item.isActive }}</p>
              <p>Location : {{ item.shippingInfor.location }}</p>
              <p>Street: {{ item.shippingInfor.address.street }}</p>
              <p>City : {{ item.shippingInfor.address.city }}</p>
              <p>Code : {{ item.shippingInfor.code }}</p>
              <p>------------------------------------------</p>
            </div>
          </div>
        </div>
        <p style="font-weight: bold;color: black;">Cách 2</p>
        <div class="cach2">
          <div v-for="item in books.filter(book => book.shippingInfor.address.city === 'HCM')">
            <p>Name: {{ item.name }}</p>
            <p>Author: {{ item.author }}</p>
            <p>Active: {{ item.isActive }}</p>
            <p>Location : {{ item.shippingInfor.location }}</p>
            <p>Street: {{ item.shippingInfor.address.street }}</p>
            <p>City : {{ item.shippingInfor.address.city }}</p>
            <p>Code : {{ item.shippingInfor.code }}</p>
            <p>------------------------------------------</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.container {

  position: absolute;
  margin-top: 10px;
  top: 0px;
  left: 20px;

}

.box1 {

  margin-top: 30px;

}

.books {

  padding: 5px;

}
</style>
