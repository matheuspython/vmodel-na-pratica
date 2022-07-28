<template>
  <div class="film">
    <img :src="img" alt="">
    <h1>{{name}}</h1>
    <p>{{description}}</p>
  </div>
</template>

<script>
  export default {
    name: "TheMovie",
    props: {
      name: String,
      img: String,
      description: String
    },
    data(){
      return{
        DataImagem: this.img,
        DataName: this.name,
        DataDescription: this.description
      }
    }
  }
</script>

<style scoped>
  .film{
    width: 100%;
    max-width: 200px;
  }
  .film img{
    width: 100%;
    border-radius: 12px 12px 0 0;
  }
  .film h1{
    text-align: center;

  }
</style>