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

import { computed, ref } from 'vue'


export default {
  name: 'Home',
  setup() {
    //begin it with empty string
    const search = ref('')
    //create a ref and output some array of names (the array is the value of this ref (names))
    const names = ref(['mahtab', 'matin', 'moonteen', 'melina', 'maryam', 'elham', 'mario'])

    const matchingNames = computed(() => {
      //value cause we want the value of the ref, filter method directly on names cause names is a ref object
      return names.value.filter((name) => name.includes(search.value))
    })

   return { names, search, matchingNames }
  }
}
</script>
