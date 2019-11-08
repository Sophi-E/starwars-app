<template>
  <div id="app">
    <div>
      <characters 
      v-for='(id, index) in initial_ids'
      :key='index'
      :id='id'
    />
    </div>
    
  </div>
</template>

<script>
import Characters from './components/Characters.vue'
export default {
  name: 'app',
  components: {
    Characters
  },
  data(){
    return{
      title: 'Generate your Team',
      initial_ids : [1, 13, 14]
      
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
