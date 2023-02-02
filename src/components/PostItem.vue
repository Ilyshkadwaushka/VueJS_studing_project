<template>
    <div class="post">
        <div><strong>{{ post.title }}:</strong> {{ post.body }}</div>
    </div>
</template>

<script>
export default {
    name: "PostItem",
    props: {
        post: {
            type: Object,
            required: true,
        }
    }
}
</script>

<style scoped>
.post {
    padding: 15px;
    border: 2px solid teal;
    margin-top: 15px;
}
</style>