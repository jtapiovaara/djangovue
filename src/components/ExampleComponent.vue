<template>
    <div class="container">
<!--        <ul v-if="posts && posts.length">-->
        <ul>
            <li v-for ="post in posts" v-bind:key="post.id">
                <p><strong>{{post.title}}</strong></p>
                <p>{{post.body}}</p>
            </li>
        </ul>
<!--        <ul v-if="errors && errors.length">-->
<!--            <li require-v-for="error of errors">-->
<!--                {{error.message}}-->
<!--            </li>-->
<!--        </ul>-->
    </div>
</template>

<script>
    import axios from 'axios';
    export default {
        name: "ExampleComponent.vue",
        data() {
            return {
                posts: [],
                errors: []
            }
        },
        created() {
            axios.get(`http://jsonplaceholder.typicode.com/posts`)
            .then(response => {
                    // JSON responses are automatically parsed.
                this.posts = response.data
            })
            .catch(e => {
                this.errors.push(e)
            })
        }
    }
</script>

<style scoped>

</style>