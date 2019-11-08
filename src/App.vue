<template>
  <div id="app">
    <div>
      <films 
      v-for='(id, index) in initial_ids'
      :key='index'
      :id='id'
    />
    </div>
    
  </div>
</template>

<script>
import Films from './components/Films.vue'
export default {
  name: 'app',
  components: {
    Films
  },
  data(){
    return{
      title: 'Get Your Favorite Starwars Film',
      initial_ids : [1, 3, 4] 
    }
  }
}
</script>

<style>
body{
  background-color: #2c3e50;
}
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: antiquewhite;
  margin-top: 60px;
}
</style>
