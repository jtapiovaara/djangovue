<template>
    <div class="container">
        <h2>Tilattua tietoa ja viihdettä</h2>
        <div id="tilausvue" class="col">
            <ul v-for ="sub in subscriptions" v-bind:key="sub.id">
                <h5>{{sub.name}}</h5>
                <p>{{sub.description}}</p>
            </ul>
        </div>
    </div>
</template>

<script>
    import axios from "axios";
    export default {
        name: "mytilaukset",
    data() {
        return{
            postBody: '',
            subscriptions: [],
            errors: []
        }
    },
    created() {
        axios.get('http://127.0.0.1:8000/api/subscription_api/')
        .then(response => {
            this.subscriptions = response.data
        })
        .catch(e => {
            this.errors.push(e)
        })
    }
    }
</script>

<style scoped>
    #tilausvue {
        font-family:
          Manjari,
          Arial,
          Chilanka
          sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: darkgreen;
  margin-top: 60px;
}
</style>