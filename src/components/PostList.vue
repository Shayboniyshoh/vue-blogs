<template>
    <div class="post-list">
        <SinglePost :post="post" v-for="post in posts" :key="post.id" />
    </div>
</template>

<script>
import SinglePost from "./SinglePost.vue";

export default {
    props: ['posts'],
    components: { SinglePost },
    setup(props) {
        console.log(props.posts)
    }
}
</script>

<style>
.post-list {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    margin: 2rem 0;
}
</style>