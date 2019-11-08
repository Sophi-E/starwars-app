<template>
  <div class='character'>
      {{character}}
  </div>
</template>

<script>
export default {
    name: 'character',
    data(){
        return{
            character: {}
        }
    },
    methods:{
        fetchCharacter(){
            fetch('https://swapi.co/api/films/1/', {
                method: 'GET'
            })
            .then(response => response.json())
            .then(data => this.character = data)
        }
    },

    created(){
        this.fetchCharacter()
    }
}
</script>

<style>

</style>