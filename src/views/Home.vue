<template>
  <div class="home">
    <h1>Home</h1>
    <p>my name is {{ name }} and my age is {{ age }}</p>
    <button @click="handleClick">click me</button>
    <!-- in template we dont use the value property -->
    <button @click="age++">add 1 to age</button>
    <input type="text" v-model="name">
    
  </div>
</template>

<script>
import { ref } from 'vue'


export default {
  name: 'Home',
  //inside here we can write any kind of normal JS.
  //it runs first before created,before mounted tec
  setup() {

    // const p =  ref(null)

    //:by using ref now they are reactive value
    const name = ref('mario')
    const age = ref(30)

    const handleClick = () => {
      name.value = 'luigi'
      age.value = '35'
    }

    //if we want to use them in our template we have to return whatever values we want to use inside template.
    return { name, age, handleClick }
  },
  //this value right here is reactive
  data() {
    return {
      score: 5
    }
  }
}
</script>
