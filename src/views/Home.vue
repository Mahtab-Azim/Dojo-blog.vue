<template>
  <div class="home">
    Home
    <p ref="p">my name is {{ name }} and my age is {{ age }}</p>
    <button @click="handleClick">click me</button>
  </div>
</template>

<script>
import { ref } from 'vue';


export default {
  name: 'HomeView',
  //inside here we can write any kind of normal JS.
  //it runs first before created,before mounted tec,
  setup() {
    console.log(this)

    //we can't use this value before we return it (return is down)
    const p =  ref(null)

    let name = 'mario'
    let age = 30

    const handleClick = () => {
      //also output the value property
      console.log(p, p.value)
      //p.value to get that DOM element
      p.value.classList.add('test')
      //we can also change the text content of a ref
      p.value.textContent = 'hello, mahtech'
    }

    //if we want to use them in our template we have to return whatever values we want to use inside template.
    return { name, age, handleClick, p }
  },
  //this value right here is reactive
  // data() {
  //   age: 40
  // }
}
</script>
