<template>
  <div class='character' @click='switchCharacter'>
      {{character}}
  </div>
</template>

<script>
export default {
    name: 'character',
    props: ['id'],
    data(){
        return{
            character: {}

        }
    },
    methods:{
        fetchCharacter(id){
            fetch(`https://swapi.co/api/people/${id}`, {
                method: 'GET'
            })
            .then(response => response.json())
            .then(data => this.character = data)
        },

        switchCharacter(){
            let random_id = Math.floor(Math.random() * 83) + 1;
            this.fetchCharacter(random_id)
        }
    },

    created(){
        this.fetchCharacter(this.id)
    }
}
</script>

<style>

</style>