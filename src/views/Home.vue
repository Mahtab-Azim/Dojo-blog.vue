<template>
  <div class="home">
    <h1>Home</h1>
    <p>{{ name }}</p>
  </div>
</template>


<script>
import { computed, ref } from 'vue'


export default {
  name: 'Home',
  setup() {
    //its just return a simple value:
   const name = computed(() => {
    // this value assigned to name essentially when we output it (out put the name)
    return 'mahtab'
   })

   return{ name }
  }
}
</script>
