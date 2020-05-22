<template>
    <div class="container">
        <h2>Luonnonmuistomerkkejä</h2>
        <div id="ekavue" class="col">
            <ul v-for ="lmm in lmms.results" v-bind:key="lmm.id">
                <p><strong>{{lmm.nimi}} | {{lmm.svuosi}}</strong></p>
                <p>{{lmm.kuvaus}}</p>
                <p><small>{{lmm.diaari}}</small></p>
<!--                <img alt="Vue logo" src="./assets/lähiluonto_logo.jpg" class="img-fluid">-->
                <b-link type="text/css" href="https://photos.google.com/album/AF1QipMXTl1BLqzjofEZ3DKQ765d2Y7WCCI-vmdrIbqg/photo/AF1QipNONfCoDU1Gs-_l3Gf34UH0poUSd4Xxln0o4Y8i" target="_blank">{{lmm.nimi}}</b-link>
<!--                <iframe src="https://maps.google.com/maps?q={{ lmm.kohdeLat }}, {{ lmm.kohdeLon }}&z=15&output=embed"-->
<!--                                    width="600" height="450" style="border:0" class="rounded img-fluid">-->
<!--                </iframe>-->
                <hr>
            </ul>
        </div>
    </div>
</template>

<script>
    import axios from "axios";
    export default {
        name: "mylmms",
        props: {
            msg: String
        },
        data() {
            return {
                postBody: '',
                lmms: [],
                errors: []
            }
        },
        created() {
            axios.get('http://127.0.0.1:8000/peli/peli/')
            .then(response => {
                this.lmms = response.data
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
  color: darkgreen;
  margin-top: 60px;
}
</style>