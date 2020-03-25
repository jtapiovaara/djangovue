<template>
  <div id="app">
      <b-icon icon="wrench" animation="spin" font-scale="2" ></b-icon>
      <img alt="Vue logo" src="./assets/django_rest_vue.png" class="img-fluid">
      <MyHoveroi />
      <hr>
      <MyKalenteri />
      <hr>
      <MyEkavue msg="Hieno homma.  Eteenpäin!"/>
      <hr>
<!--      <ExampleComponent />-->
<!--      <hr>-->
<!--      <HelloWorld msg="Vue.js, lets do it!"/>-->
      </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import MyEkavue from './components/MyEkavue.vue'
import MyHoveroi from './components/MyHoveroi.vue'
import MyKalenteri from './components/MyKalenteri.vue'
// import ExampleComponent from './components/ExampleComponent'

export default {
  name: 'App',
  components: {
      // ExampleComponent,
      MyHoveroi,
      MyKalenteri,
      MyEkavue,
      // HelloWorld
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
