<template>
  <div class="home">
    <h1>Home</h1>
    <h2>Refs</h2>
    <p>{{ ninjaOne.name }} - {{ ninjaOne.age }}</p>
    <button @click="updateNinjaOne">Update ninja one</button>
    <h2>Reactive</h2>
    <p>{{ ninjaTwo.name }} - {{ ninjaTwo.age }}</p>
    <button @click="updateNinjaTwo">Update ninja two</button>
  </div>
</template>


<script>
import { ref, reactive } from 'vue'


export default {
  name: 'Home',
  setup() {
    //This ref has a value of an object, and this obj has two property.
    const ninjaOne = ref({ name: 'mario', age: 30 })
    //Use Reactive
    const ninjaTwo = reactive({ name: 'luigi', age: 35 })

    const updateNinjaOne = () => {
      ninjaOne.value.age = 40
    }

    //here i wrote, we dont need to use .value to acsses the value in reactive
    const updateNinjaTwo = () => {
      ninjaTwo.age = 45
    }

    return { ninjaOne, updateNinjaOne, ninjaTwo, updateNinjaTwo }
  }
}
</script>
