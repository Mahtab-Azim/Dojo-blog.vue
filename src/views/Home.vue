<template>
  <div class="home">
    <h1>Home</h1>
    <!-- Remind: we use v-model for Two-way Binding with data and input form -->
    <input type="text" v-model="search">
    <p>Search term - {{ search }}</p>
    <div v-for="name in matchingNames" :key="name">{{ name }}</div>
  </div>
</template>


<script>

import { computed, ref, watch } from 'vue'


export default {
  name: 'Home',
  setup() {
 
    const search = ref('')
    const names = ref(['mahtab', 'matin', 'moonteen', 'melina', 'maryam', 'elham', 'mario'])

    //the first argument is what we want to watch,the 2nd argument is a func wich will fire every time that search ref value changes
    //it is watch
   watch(search, () => {
    console.log('watch function raf')
   })
    

    const matchingNames = computed(() => {
      return names.value.filter((name) => name.includes(search.value))
    })

   return { names, search, matchingNames }
  }
}
</script>
