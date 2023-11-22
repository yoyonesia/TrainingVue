<script setup>
import { ref } from 'vue'

defineProps({
  msg: String,
})

const count = ref(0)
const link = ref("http://10.20.214.173:55193/BCAAbacas/login")
const html = ref("<p> Cobain <b>cuk</b> </p>")
const arr = ref([{id:1,name:'nahloh'},{id:2,name:'nahloh'},{id:3,name:'nahloh'},])
</script>

<template>
  <div> 
    <h1>{{ msg }}</h1>

 
    <a :href="link"> Akses Abacas hah</a>
  <div v-html="html"></div>
  <ul>
    <li v-for="arrs in arr" :key="arrs.id">
      {{ arrs.name }}
    </li>
  </ul>
  <button @click="count++">Count is : {{count}}</button>
  </div>
</template>

<style scoped>
button {
  font-weight: bold;
}
</style>
