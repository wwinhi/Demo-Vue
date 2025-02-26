<!-- <script setup>
import { reactive,computed } from 'vue';

const book = reactive({
  name: 'Book 1',
  chapters :[]
})

const addChapter = () => {
  book.chapters.push('Chapter')
}

// const isPublished = () => book.chapters.length > 0 ? 'có' : 'Không'

// nhược điểm bất kì step nào thay đổi thì nó đều chaỵ lại hàm isPublished -> sinh ra computed
// computed là một đối tượng trong vue được sdung để khai báo các thuộc tính tính toán hay được gọi là 
// computed property là những thuộc tính dựa trên các step khác của chúng ta và được cập nhật tự động nếu 
// như mà step phụ thuộc nó thay đổi giúp chúng ta quản lý dữ liệu trong ứng dụng dễ dàng và hiệu quả hơn 

const isPublished = computed(() => {
  return book.chapters.length > 0 ? 'có' : 'Không'
} )
</script>

<template>
<p id="count">Book name: {{ book.name }}</p>
<p id="count">Đã xuất bản: {{ isPublished }}</p>
<button @click="addChapter">Add chapter</button>
</template> -->

<!-- Writable computed  -->
<script setup>
import { computed, ref } from 'vue';

const firstname = ref('Nguyen Van')
const lastname = ref('A')

const fullname = computed({
  get(){
    return firstname.value + ' ' + lastname.value
  },
  set(newValue) {
    [firstname.value, lastname.value] = newValue.split(',')
  }
})

const changeFullName = () =>{
  fullname.value = 'Nguyen Van,B'
}
</script>
<template>
  <p id="count">Firstname: {{ firstname }}</p>
  <p id="count">Lastname: {{ lastname }}</p>
  <p id="count">Fullname: {{ fullname }}</p>
  <button @click="changeFullName">ChangeFullName</button>
</template>