<template>
  <div class="home">
    <h1>Welcome to Blogs</h1>
    <div v-if="error">{{ error }}</div>
    <div v-if="posts.length">
      <PostList :posts="posts" />
    </div>
    <div v-else>
      <p>Loading...</p>
    </div>
  </div>
</template>

<script>
import PostList from "../components/PostList.vue";
import { ref } from "vue";

export default {
  name: 'HomeView',
  components: { PostList },
  setup() {
    const posts = ref([])
    const error = ref(null)

    const load = async () => {
      try {
        const data = await fetch('http://localhost:3000/posts')
        if (!data.ok) {
          throw Error('No data available')
        }
        posts.value = await data.json()
        console.log(posts.value)

      } catch (err) {
        error.value = err.message
        console.log(error.value)
      }
    }
    load()
    return { posts, error }
  }

}
</script>
<style>
.home {
  margin: 2rem 0;
}
</style>