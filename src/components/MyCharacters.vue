<template>
  <div class="w-80  m-auto p-4 mb-10 flex justify-center rounded-md font-mono bg-slate-700 shadow-lg shadow-lime-500/40">
    <div class="flex flex-col ">
      <img v-bind:src="character.image" alt="personaje" class="rounded-md" />
      <p>Name: {{ character.name }}</p>
      <p>Sex: {{ character.gender }}</p>
      <p>Species: {{ character.species }}</p>
    </div>
  </div>
</template>

<script>
export default {
  props: ["character"],
};
</script>
