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
    const posts = ref([
      { id: 0, title: "News Heading 1", body: "Lorem ipsum, dolor sit amet consectetur adipisicing." },
      { id: 1, title: "News Heading 2", body: "Lorem ipsum, dolor sit amet consectetur adipisicing." },
      { id: 2, title: "News Heading 3", body: "Lorem ipsum, dolor sit amet consectetur adipisicing." }
    ])

    return { posts }
  }

}
</script>
