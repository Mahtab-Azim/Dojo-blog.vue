<template>
  <div class="home">
    <h1>Home</h1>
    <!-- Remind: we use v-model for Two-way Binding with data and input form -->
    <input type="text" v-model="search">
    <p>Search term - {{ search }}</p>
    <div v-for="name in matchingNames" :key="name">{{ name }}</div>
    <button @click="handleClick">stop watching</button>
  </div>
</template>


<script>

import { computed, ref, watch, watchEffect } from 'vue'


export default {
  name: 'Home',
  setup() {
 
    const search = ref('')
    const names = ref(['mahtab', 'matin', 'moonteen', 'melina', 'maryam', 'elham', 'mario'])

    //the first argument is what we want to watch,the 2nd argument is a func wich will fire every time that search ref value changes
    //it is watch
   const stopWatch = watch(search, () => {
    console.log('watch function ran')
   })


   //we just pass in a function we don't pass in anything to watch as the 1st argument like we did with watch
   //this ryn initially when the component first loads or when the setup function first runs
   const stopEffect = watchEffect(() => {
    console.log('watchEffect function ran', search.value)
   })
    

    const matchingNames = computed(() => {
      return names.value.filter((name) => name.includes(search.value))
    })

    const handleClick = () => {
      stopWatch()
      stopEffect()
    }

   return { names, search, matchingNames, handleClick }
  }
}
</script>
