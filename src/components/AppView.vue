<script>
import { store } from '../store.js';
import ViewCard from './ViewCard.vue';

export default {
  name: 'AppView',
  data() {
    return {
      store
    };
  },
  components: {
    ViewCard
  }
}
</script>

<template>
    <section class="bg-black">
        <div class="container p-5">
    <div class="row mb-4">
      <div class="col-12">
        <h1 class="section-title">Movies</h1>
      </div>
    </div>
    <div class="row">
      <div class="col-12">
        <div class="movie-grid">
          <ViewCard v-for="movie in store.movies" :key="movie.id" :cardInfo="movie"></ViewCard>
        </div>
      </div>
    </div>
    <div class="row mt-5">
      <div class="col-12">
        <h1 class="section-title">Series TV</h1>
      </div>
    </div>
    <div class="row">
      <div class="col-12">
        <div class="series-grid">
          <ViewCard v-for="series in store.series" :key="series.id" :cardInfo="series"></ViewCard>
        </div>
      </div>
    </div>
  </div>
    </section>

</template>

<style scoped lang="scss">


.container {
background: rgb(0,0,0);
background: linear-gradient(90deg, rgba(0,0,0,1) 0%, rgba(78,78,78,1) 47%, rgba(0,0,0,1) 100%);
}

.section-title {
  font-size: 24px;
  font-weight: bold;
  color: #e5e5e5;
  text-transform: uppercase;
  letter-spacing: 2px;
  margin-bottom: 20px;
  position: relative;

  &::after {
    content: '';
    position: absolute;
    bottom: -8px;
    left: 0;
    width: 60px;
    height: 4px;
    background-color: #e50914;
  }
}

.movie-grid,
.series-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
  gap: 20px;
}

@media (max-width: 768px) {
  .movie-grid,
  .series-grid {
    grid-template-columns: repeat(auto-fill, minmax(150px, 1fr));
  }
}
</style>