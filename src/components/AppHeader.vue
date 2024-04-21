<script>
import { store } from '../store.js';

export default {
  name: 'AppHeader',
  data() {
    return {
      store
    };
  },
}
</script>

<template>
  <header>
    <nav class="navbar">
      <div class="navbar-brand">
        <a href="#" class="logo-text">BOOLFLIX</a>
      </div>
      <div class="search-container">
        <input type="text" class="search-input" v-model="store.searchText" placeholder="Cerca..">
        <button @click="$emit('searchUser')" class="search-button">
          <span>Cerca</span>
        </button>
      </div>
    </nav>
  </header>
</template>

<style scoped lang="scss">
header {
  background-color: #000000;
  padding: 10px;
}

.navbar {
  display: flex;
  align-items: center;
  justify-content: space-between;
  max-width: 1200px;
  margin: 0 auto;
}

.navbar-brand {
  .logo-text {
    color: #e50914;
    font-size: 40px;
    font-weight: bold;
    text-decoration: none;
  }
}

.search-container {
  display: flex;
  align-items: center;
  background-color: #ffffff;
  border-radius: 4px;
  overflow: hidden;
}

.search-input {
  border: none;
  padding: 8px 12px;
  font-size: 14px;
  flex-grow: 1;

  &:focus {
    outline: none;
  }
}

.search-button {
  background-color: #e50914;
  color: #ffffff;
  border: none;
  padding: 8px 16px;
  font-size: 14px;
  display: flex;
  align-items: center;
  cursor: pointer;
  margin-left: 10px;

  &:hover {
    background-color: #c11324;
  }

  span {
    margin-left: 8px;
  }
}


</style>