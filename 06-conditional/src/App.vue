<script setup>
import { ref, useShadowRoot } from 'vue';



const isVisible =ref(true)
const toggleLogin = () => {
  isLoggedIn.value =  !isLoggedIn.value;
}

const isLoggedIn = ref(false)
const toggleShow = () => {
  isVisible.value =  !isVisible.value;
}

const userStatus = ref('online')

const changeStatus = () => {
if (userStatus.value === 'online') {
  userStatus.value = 'away'
} else if (userStatus.value === 'away'){
  userStatus.value = 'busy'
} else if (userStatus.value ==='busy'){
  userStatus.value = 'online'
}
}
// v-if sử dụng khi trong trường hợp ta muốn thêm xóa hẳn cái phần tử đó ra khỏi dom
// v-show khi muốn hiển thị hoặc ẩnẩn
</script>

<template>
  <div> 
    <h1 v-if="isLoggedIn">Chào mừng người dùng đã đăng nhập</h1>
    <h1 v-else>Chào mừng khách</h1>
    <button class="btn" @click="toggleLogin">{{ isLoggedIn ? "Đăng nhập" : "Đăng xuất" }}</button>
    <br>	
    <h1 v-if="userStatus === 'online'">Người dùng đang online</h1>
    <h1 v-else-if="userStatus === 'away'">Người dùng đang vắng mặt</h1>
    <h1 v-else-if="userStatus === 'busy'">Người dùng đang bận </h1>
    <h1 v-else> Không rõ trạng thái </h1>
    <button class="btn" @click="changeStatus">Thay đổi trạng thái</button>
    <br>
    <h1 v-show="isVisible">Nội dung này ẩn hoặc hiển thị</h1>
    <button class="btn" @click="toggleShow">{{ isVisible ? "Ẩn" : "Hiện" }}</button>
  </div>
</template>

<style>
.btn{
  border: none;
  background:rgb(89, 89, 242);
  color:rgb(210, 252, 252);
  padding: 10px 14px;
  border-radius: 6px;
  cursor: pointer;
}
.btn:hover{
  background:rgb(113, 113, 238);
}
</style>