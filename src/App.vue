<script>
import axios from 'axios';
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
import { store } from './data/store';
const baseUri = 'https://api.themoviedb.org/3';
const apiKey = 'bad7ca77233bc46b9ff0f547289a5f01';

export default {
  components: { AppHeader, AppMain },
  methods: {
    searchMovie(searchedTerm) {
      axios.get(`${baseUri}/search/movie?api_key=${apiKey}&query=${searchedTerm}&language=it`).then(res => {
        store.movies = res.data.results;
      })
    }
  }
}
</script>

<template>
  <AppHeader @searched-term="searchMovie" />
  <AppMain />
</template>