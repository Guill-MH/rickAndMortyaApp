<template>
  <div class="bg-slate-700 h-16 flex items-center shadow-xl">
    <img
      v-bind:src="require('@/assets/log.png')"
      alt=""
      class="w-16 md:w-31 lg:w-31"
    />
    <h1 class="font-bold text-2xl text-slate-300">Rick and Morty App</h1>
  </div>
  <div class="w-full slate-300  flex flex-wrap justify-center p-3 bg-slate-900 ">
    <MyCharacter
      v-for="character in characters"
      v-bind:key="character.id"
      v-bind:character="character"
    />
  </div>
</template>

<script>
//librerias
import axios from "axios";
//Componentes
import MyCharacter from "./components/MyCharacters.vue";

export default {
  name: "App",
  components: {
    MyCharacter, //character
  },
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
