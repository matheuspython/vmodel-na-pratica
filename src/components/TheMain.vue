<template>
  <main>
    <h1 class="title">what`s your favorite movie</h1>
    <div class="container">
      <form class="form">
        <input placeholder="input field" type="text" v-model="nameOfFilm">
        <button v-on:click="search" type="button"> search </button>
      </form>
      <section class="films">
        <Movie 
          v-for="film in listOfFilms" 
          :key="film" 
          :name="film.Title" 
          :img="film.Poster" 
          :description="film.Plot" 
        />
      </section>
    </div>
  </main>
</template>

<script>
import Movie from './Movie.vue'
export default {
  name: "TheMain",
  data() {
    return {
      nameOfFilm: "",
      listOfFilms: [],
      search: async () => {
        const response = await fetch(`https://www.omdbapi.com/?i=tt3896198&apikey=d6c1c92a&t=${this.nameOfFilm}`);
        const data = await response.json();
        this.listOfFilms.push(data);
        // this.nameOfFilm = ''
      }
    };
  },
  components: { Movie }
}
</script>

<style scoped>
  main {
    width: 100%;
  }
  .form{
    width: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 5px;
    flex-wrap: wrap;
  }
  .form input{
    width: 100%;
    height: 35px;
    max-width: 300px;
    padding-left: 15px;
  }
  .form button{
    width: 150px;
    height: 35px;
    cursor: pointer;
    border: 0;
    background-color: #2660b2;
    color: #fff;
    transition: .4s;
  }
  .form button:hover{
    background-color: #93b0d8;
  }
  .title{
    text-align: center;
    margin: 19px 0;
  }

.container {
  width: 100%;
  max-width: 1280px;
  margin: 0 auto;
}
.films{
  width: 100%;
  margin-top: 20px;
  display: flex;

  justify-content: center;
  align-items: center;
  gap: 15px;
  flex-wrap: wrap;
}
</style>