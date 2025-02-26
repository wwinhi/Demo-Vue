<script setup>
const message = 'hello world'
const rawHtml = '<span style="color: blue">day la mau xanh </span>'
const buttonId = 'button-id'
const isButtonDisabled = true
const objectOfAttrs = {
    id: 'container',
    class: 'wrapper',
    style: {
        color: 'red',
    }
}
const number = 2
const listString = 'a,b,c,d,f,g,h'
</script>

<template>
<h1>xin chao</h1>
<p>{{ message }}</p>
<span v-html="rawHtml"></span>
<!-- <button :id="buttonId" :disabled="isButtonDisabled">Click here</button> -->
<button :id="buttonId" :disabled="isButtonDisabled">{{ isButtonDisabled ? 'Disable' : 'click here' }}</button>
<button v-bind="objectOfAttrs">click here</button>
<button :id="listString.split(',').join('-')">Number: {{ number * 2 }}</button>
</template>
