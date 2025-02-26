<script setup>
import { reactive, ref } from 'vue';
  
const object = reactive ({
  count: 2,
  user: {
    age: 18 
  },
  array:[1,2,3,4]
})
  const increase = () => {
    object.count++
    object.user.age++
    object.array.push(3)
    // sử dụng reactive thay ref => không cần .value
    // 1 đối tượng cần theo dõi đó là 1 object nên sử dụng reactive
  }
  const decrease = () => {
    object.count--
    object.user.age--
  
  }
</script>

<template>  
 <div>
  <p>Count: {{ object.count }}</p>
  <p>Age: {{ object.user.age }}</p>
  <p>Array: {{ object.array }}</p>
  <button @click="count++">Increase</button> 
  <button @click="increase">Increase</button> 
  <button @click="increase">Increase</button>
  <button @click="decrease">Decrease</button>
 
</div>



</template>
