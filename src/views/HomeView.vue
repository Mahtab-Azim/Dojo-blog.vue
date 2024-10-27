<template>
  <div class="home">
    Home
    <p>my name is {{ name }} and my age is {{ age }}</p>
    <button @click="handleClick">click me</button>
  </div>
</template>

<script>


export default {
  name: 'HomeView',
  //inside here we can write any kind of normal JS.
  setup() {
    console.log('setup')

    let name = 'mario'
    let age = 30

    const handleClick = () => {
      console.log('you clicked me')
    }

    //if we want to use them in our template we have to return whatever values we want to use inside template.
    return { name, age, handleClick }
  },
  //this value right here is reactive
  data() {
    age: 40
  }
}
</script>
