<template>
  <div id="app">
<!--      <b-icon icon="wrench" animation="spin" font-scale="2" ></b-icon>-->
<!--      <img alt="Vue logo" src="./assets/django_rest_vue.png" class="img-fluid">-->
<!--      <MyHoveroi />-->
<!--      <hr>-->
<!--      <MyKalenteri />-->
<!--      <hr>-->
<!--      <MyEkavue msg="Hieno homma.  Eteenpäin!"/>-->
<!--      <hr>-->
      <MyLmms />
        <img alt="Vue logo" src="./assets/lähiluonto_logo.jpg" class="img-fluid">
      <hr>
<!--      <ExampleComponent />-->
<!--      <hr>-->
<!--      <HelloWorld msg="Vue.js, lets do it!"/>-->
      <MyTilaukset />
      <hr>
      </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
// import MyEkavue from './components/MyEkavue.vue'
import MyLmms from './components/MyLmms.vue'
// import MyHoveroi from './components/MyHoveroi.vue'
// import MyKalenteri from './components/MyKalenteri.vue'
// import ExampleComponent from './components/ExampleComponent'
import MyTilaukset from './components/MyTilaukset'

export default {
  name: 'App',
  components: {
      // MyHoveroi,
      // MyKalenteri,
      MyLmms,
      // MyEkavue,
      // ExampleComponent,
      // HelloWorld
      MyTilaukset
  }
}
</script>

<style>
#app {
  font-family:
          Chilanka,
          Arial,
          TimesNewRoman
          sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
