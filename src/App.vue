<template>
  <div class="bg-zinc-800 h-16">
    <h1>Rick and Morty App</h1>
  </div>
    <div v-for="character in characters" :key="character.id">
      {{ character.name }}
    </div>
  
</template>

<script>
//librerias
import axios from "axios";

export default {
  name: "App",
  data() {
    return {
      //se crea una variable que es un arreglo vacio, para al macenar la info
      characters: [],
    };
  },
  mounted() {
    axios
      //se hace una peticion a la API
      .get("https://rickandmortyapi.com/api/character")
      //se captura la respuesta
      .then((res) => {
        //se guarda la informacion en el arreglo vacio
        this.characters = res.data.results;
        console.log(res.data);
      })
      .catch((err) => {
        console.log(err);
      });
  },
};
</script>

<style></style>
