<template>
  <div class="home">
    <h1>Home</h1>
    <PostList v-if="showPosts" :posts="posts" />
    <button @click="showPosts = !showPosts">toggle posts</button>
    <button @click="posts.pop()">delete a post</button>
  </div>
</template>

<script>
import PostList from '../components/PostList.vue'
import { ref } from 'vue'


export default {
  name: 'Home',
  components: { PostList },
  setup() {
 
   const posts = ref([
    { title: 'welcome to the blog', body: 'Lorem ipsum odor amet, consectetuer adipiscing elit. Sapien parturient lectus odio maximus nam semper senectus. Diam ultrices lacinia platea bibendum et condimentum leo. Risus pharetra euismod in non sodales duis pulvinar nostra. Potenti consectetur mus, venenatis maecenas senectus per fames litora. Laoreet dictum curae dolor congue libero netus cursus consequat.', id: 1 },
    { title: 'tap 5 css tips', body: '', id: 2 },
   ])
   const showPosts = ref(true)
  
   return { posts, showPosts }
  }
}
</script>
