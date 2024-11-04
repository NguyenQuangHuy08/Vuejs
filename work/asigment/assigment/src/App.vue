<script setup>
import { ref, reactive, onMounted } from 'vue';

// Bài 1
const products = reactive([
  {

    name: 'Bánh kẹo',
    price: '120.000 VNĐ',
    describe: 'Đẹp',
  },
  {
    name: 'Bánh kẹo 1',
    price: '150.000 VNĐ',
    describe: 'Đẹp',
  }
])


//Bai2

const indexNumber = ref(1);

const clickButton = () => {

  indexNumber.value++;
  console.log('Number', indexNumber.value)

}

// Bài 3

const products3 = ref([

  {

    name: 'Bánh kẹo',
    price: '120.000 VNĐ',
    describe: 'Đẹp',
    status: true,
  },
  {
    name: 'Bánh kẹo 1',
    price: '150.000 VNĐ',
    describe: 'Đẹp',
    status: false,
  }

])

const setChangeClick = (index, status) => {
  products3.value[index].status = status;
  console.log(products3.value[index].status);
}

// Bài 4

const students = ref([

  {

    name: 'Huy Nguyễn',
    codeNumber: 'Ph26813',
    class: '11040',
    status: true,
  },
  {
    name: 'Huy',
    codeNumber: '120000 VNĐ',
    class: '1111',
    status: false,
  }

])

//Bai tập thêm tìm số lớn thứ 2 trong mảng

const findMax2 = ref([3, 2, 4, 5]);
// Biến lưu trữ số lớn thứ hai
const secondLargest = ref(null);

// Hàm tính số lớn thứ hai
const findMaxLargest = () => {

  const message = [...new Set(findMax2.value)];

  message.sort((a, b) => b - a);

  secondLargest.value = message[1];
};

onMounted(() => {
  findMaxLargest();
});


</script>

<template>
  <div class="container">
    <div class="title">
      <h5>Assigment</h5>
    </div>
    <div class="bai1">
      <div>
        <h6>Bài 1</h6>
      </div>
      <li v-for="item in products">
        <div>
          <p>{{ item.name }}</p>
          <p>{{ item.price }}</p>
          <p>{{ item.describe }}</p>
        </div>
      </li>
    </div>
    <!--  -->
    <hr>
    <div style="margin-top: 30px;" class="bai2">
      <div>
        <h6>Bài 2</h6>
      </div>
      <div>
        <span style="margin-top: 30px;">Giá trị hiện tại là: </span>
        <span style="margin-left: 10px;">{{ indexNumber }}</span>
        <br>
        <button @click="clickButton" style="margin-top: 10px;" class="btn btn-success">Xin hãy click</button>
      </div>
    </div>
    <hr>
    <!--  -->
    <div class="bai3">
      <div>
        <h6>Bài tập 3</h6>
      </div>
      <div v-for="(product, index)  in products3" class="product-card"
        :class="{ 'in-stock': product.status, 'out-of-stock': !product.status }">
        <p>Name: {{ product.name }}</p>
        <p>Price: {{ product.price }}</p>
        <p>Describe: {{ product.describe }}</p>
        <p>Status: {{ product.status ? 'In Stock' : 'Out of Stock' }}</p>
        <button @click="setChangeClick(index, !product.status)" class="btn btn-success">
          {{ product.status ? 'Set Out of Stock' : 'Set In Stock' }}
        </button>
        <p></p>
        <!--  -->
      </div>
    </div>
    <hr>
    <!--  -->
    <div class="bai4">
      <div>
        <h5>Bài 4</h5>
      </div>
      <div>
        <h6>Danh sách sinh viên</h6>
        <p v-if="students.length > 0">
          <span>Có sinh viên</span>
          <li v-for="student in students">
            <p>Name: {{ student.name }}</p>
            <p>Code number: {{ student.codeNumber }}</p>
            <p>Class: {{ student.class }}</p>
          </li>
        </p>
      </div>
      <!--  -->
      <div>
        <p v-if="students.length === 0" style="color:red;font-weight: bold;">Không có sinh viên nào.</p>
      </div>
    </div>
    <!--  -->
    <hr>
    <div class="sosanh">
      <div>
        <h5>So sánh giữa V-if và v-show</h5>
        <br>
        <p class="v-if">
          - V-if chỉ điều kiện thực vì nó đảm bảo tính lắng nghe của sự kiện và các thành phần con bên trong khối điều
          kiện.
          Tuy nhiên nếu mà điều kiện là sai khi khi kết xuất ban đầu thì nó sẽ không làm gì cả cho đến khi điều kiện trở
          thành
          đúng với lần đầu tiền.
        </p>
        <p class="v-show">
          - V-show phần tử luôn được hiển thị bất kể điều kiện ban đầu, với chức năng chuyển đổi dựa trên CSS.
          (display-none)
        </p>

      </div>
    </div>
    <hr>
    <div class="baitapthem">
      <button @click="findMaxLargest">Tìm số lớn thứ hai</button>
      <br>
      <!-- Hiển thị kết quả trong thẻ span -->
      <span>Dãy số trong mảng là: {{ findMax2 }}</span>
      <br>
      <span v-if="secondLargest !== null">Số lớn thứ hai là: {{ secondLargest }}</span>
    </div>
  </div>
</template>

<style scoped>
.container {

  position: absolute;
  top: 0px;
  left: 10px;

}

/* Bài 3 */
.in-stock {
  background-color: #d4edda;

}

.out-of-stock {
  background-color: #f8d7da;

}
</style>
