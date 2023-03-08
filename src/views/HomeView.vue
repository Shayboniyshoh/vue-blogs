<template>
  <div class="home">
    <h1>Welcome to Blogs</h1>
    <PostList :posts="posts" />
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

    return { posts }
  }

}
</script>
<style>
.home {
  margin: 2rem 0;
}
</style>