<template>
    <div class="container">
        <div id="ekavue" class="col">
            <h1>Tässä terveiset päälliköltä: {{ msg }}</h1>
            <p> Tästä P2R4C3 => <br>
                <a href="http://aatooseetrii.eu.pythonanywhere.com/aatooseetrii" target="_blank" rel="noopener">Cool & Owned</a>
            </p>
            <ul v-for ="post in posts" v-bind:key="post.id">
                <p><strong>{{post.ntitle}}</strong></p>
                <p>{{post.ndescription}}</p>
                 <p><a :href="post.nlocation" target="_blank">Puiston sivusto</a></p>
            </ul>
        </div>

    </div>
</template>

<script>
    import axios from "axios";
    export default {
        name: "Ekavue",
        props: {
            msg: String
        },
        data() {
            return {
                postBody: '',
                posts: [],
                errors: []
            }
        },
        created() {
            axios.get('http://aatooseetrii.eu.pythonanywhere.com/aatooseetrii/api/')
            .then(response => {
                this.posts = response.data
            })
            .catch(e => {
                this.errors.push(e)
            })
        },
    }
</script>

<style scoped>
    #ekavue {
        font-family:
          Manjari,
          Arial,
          Chilanka
          sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>