<template>
    <div class="app">
        <post-form @create="createPost"></post-form>
        <!-- v-bind:last_post_id=last_post_id=posts[posts.length-1].id -->
        <post-list v-bind:posts="posts"></post-list>
    </div>
</template>

<script>
import PostForm from "@/components/PostForm";
import PostList from "@/components/PostList";

export default {
    components: {
        PostForm,
        PostList,
    },
    data (){
        return {
            posts: null,
        }
    },
    mounted() {
        this.axios.get("http://127.0.0.1:8000/posts/", {
                headers: {
                    'Content-type': 'application/json',
                    'Origin': 'http://127.0.0.1:8000',
                }
            }
        ).then((response) => {
            this.posts = response.data
        })
    },
    methods: {
        createPost(post) {
            // this.posts.push(post);
            this.axios.post("http://127.0.0.1:8000/posts/", post, {
                headers: {
                    'Content-type': 'application/json',
                    'Origin': 'http://127.0.0.1:8000',
                }
            })
        }
    }
}
</script>

<style>
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}
.app {
    padding: 20px;
}

</style>