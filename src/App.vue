<script setup>
   import rickmortyimg from './assets/rick-and-morty-portal-moon-mod-download-35.png';
   const title = 'Rick and Morty';
</script>

<template>

  <div class="container mt-3 p-4 bg-danger text-white reounded text-center">
    <h1>{{title}}</h1>
  </div>

  <div class="container mt-3 p-4 bg-dark text-white reounded text-center">
    <img :src="rickmortyimg" alt="Rick and Morty" class="img-fluid">
    <p>Numeber of characters: {{characters.info.count}}</p>
    <p>{{temp}}</p>
  </div>

  <div class="container mt-3 rounded text-center">
    <table class="table">
      <tr>
        <th>Name</th>
        <th>Image</th>
        <th>species</th>
        <th>gender</th>
        <th>origin-name</th>
        <th>location-name</th>
      </tr>
      <tr v-for="character in characters.results" :key="character.id">
        <td>{{character.name}}</td>
        <td><img class="img-fluid" :src="character.image" alt="character.name"></td>
        <td>{{character.species}}</td>
        <td>{{character.gender}}</td>
        <td>{{character.origin.name}}</td>
        <td>{{character.location.name}}</td>
      </tr>
    </table>
  </div>
</template>

<script>
import {characters} from "@/assets/characters.js";
const temp = [1,2,3,4,5,6,7,8,9,10];
export default {
  name: 'App',
  components: {
  },
  data() {
    return {
      characters,
      temp
    }
  }
}
</script>

