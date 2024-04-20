<script>
import AppHeader from './components/AppHeader.vue';
import AppView from './components/AppView.vue';
import AppSearch from './components/AppSearch.vue';
import axios from 'axios';
import { store } from './store.js';

export default {
  components: {
    AppHeader,
    AppView
  },
  data() {
    return {
      
    };
  },
  methods: {
    getMoviesFromApi() { 
      const queryParams = {
        api_key: store.apiKey,
        query: store.searchText
      };
      axios.get('https://api.themoviedb.org/3/search/movie', {
        params: queryParams
      }).
      then((response) => {
        store.movies = response.data.results;
      });
    },
  },

}




</script>

<template>
  <AppHeader @searchUser="getMoviesFromApi"></AppHeader>
  <AppView></AppView>
</template>

<style lang="scss">
@use '../src/style/generic.scss' as *;
</style>