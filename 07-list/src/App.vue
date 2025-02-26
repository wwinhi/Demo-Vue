<script setup>
import { ref } from 'vue';


const shoppingItem = ref ([
  {
    name: 'apple',
    price: 7
  },
  {
    name : 'banane',
    price : 12,
  },
  {
    name : 'orange',
    price: 15
  }
])

</script>

<template>
  <div>
    <ul>
      <li v-for="item in shoppingItem" :key="item.name">
        {{ item.name }} - {{ item.price }}
      </li>
    </ul>
    <span v-for="n in 10" :key="n">{{ n }}</span>
  </div>
</template>

