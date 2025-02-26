<script setup>
import { nextTick, ref } from 'vue';

const count = ref (0)
const increase = async () => {
  count.value++
  // console.log(document.getElementById('count').innerText)
  await nextTick()
  // nextTick dùng khi cần sử lý với DOM thật ngay trước khi nó tăng lên vẫn chưa có có cập nhật sau có nextTick mới cập nhật và tối ưu hiệu suất
  console.log(document.getElementById('count').innerText)
}
</script>
<template>
  <div>
    <p id="count">Count: {{ count }}</p>
    <button @click="increase">Increase</button>
  </div>
</template>