<script>
import AppHeader from './components/AppHeader.vue';
import { store } from './store.js';
import axios from 'axios';

export default {
  components: {
    AppHeader,

  }
  
}
</script>

<template>
  <AppHeader></AppHeader>
</template>

<style lang="scss">
@use './style/generic';
</style>