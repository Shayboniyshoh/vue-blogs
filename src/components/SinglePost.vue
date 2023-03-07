<template>
    <div class="post">
        <h1>{{ post.title }}</h1>
        <p>{{ bodyString }}</p>
    </div>
</template>

<script>
import { computed } from 'vue'
export default {
    props: ['post'],
    setup(props) {
        const bodyString = computed(() => {
            return props.post.body.substring(0, 450) + "..."
        })
        return { bodyString }
    }
}
</script>

<style>
.post {
    max-width: 400px;
    width: 100%;
    background: #eee;
    padding: 20px 30px;
    border-radius: 8px;
    margin: 1rem;
}
</style>