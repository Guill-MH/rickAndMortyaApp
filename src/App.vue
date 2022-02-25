<template>
 <h1 class="title">HelloWorld</h1>
</template>

<script>

export default {
  name: 'App',
  async mounted() {
   const res = await fetch('https://rickandmortyapi.com/api/character')
   const data = await res.json()
   console.log(data)
  },
};
</script>

<style>

</style>
