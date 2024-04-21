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
        <section class="app-results">
            <div>
                <h2>Movies</h2>
                <ViewCard v-for="movie in store.movies" :key="movie.id" :cardInfo="movie"></ViewCard>
            </div>
            <div>
                <h2>Series</h2>
                <ViewCard v-for="onlySeries in store.series" :key="onlySeries.id" :cardInfo="onlySeries"></ViewCard>
            </div>
        </section>
</template>

<style scoped lang="scss">
    h2{
        color: red;
    }
</style>