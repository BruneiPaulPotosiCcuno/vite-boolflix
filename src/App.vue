<script>
import AppHeader from './components/AppHeader.vue';
import AppSearch from './components/AppSearch.vue';
import { store } from './store.js';
import axios from 'axios';

export default {
  components: {
    AppHeader,

  }
  
}
</script>

<template>
  <AppHeader>
    <AppSearch></AppSearch>
  </AppHeader>
</template>

<style lang="scss">
@use './style/generic';
</style>