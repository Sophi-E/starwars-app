<template>
  <div class='film' @click='switchFilm'>
      <div class="container char">
        <p> Title: {{ film.title }} </p>
        <p> Director: {{ film.director }} </p>
        <p> Opening-crawl: {{ film.opening_crawl }} </p>
        <p> Producer: {{ film.producer }} </p>
        
      </div>
  </div>      

</template>

<script>
export default {
    name: 'film',
    props: ['id'],
    data(){
        return{
            film: {}

        }
    },
    methods:{
        fetchFilm(id){
            fetch(`https://swapi.co/api/films/${id}`, {
                method: 'GET'
            })
            .then(response => response.json())
            .then(data => this.film = data)
            .catch(error => console.log(error))
        },

        switchFilm(){
            let random_id = Math.floor(Math.random() * 7) + 1
            this.fetchFilm(random_id)
            console.log(random_id)
        },
    },

    created(){
        this.fetchFilm(this.id)
    }
}
</script>

<style scoped>
    .character{
        width: 100%;
        display: flex;
        flex-direction: row;
    }
    .char{

        border: 1px solid gray;
    }
</style>