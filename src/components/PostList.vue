<template>
    <h3>Посты!</h3>
    <post-item v-for="post in posts" v-bind:post="post"></post-item>
</template>

<script>
import PostItem from "@/components/PostItem";
export default {
    name: "PostList",
    components: {
        PostItem,
    },
    props: {
        posts: {
            type: null,
            required: true,
        }
    }
}
</script>

<style scoped>
</style>