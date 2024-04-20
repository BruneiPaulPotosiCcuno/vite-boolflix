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
            <ViewCard v-for="movie in store.movies" :key="movie.id" :cardInfo="movie"></ViewCard>
        </section>
</template>

<style scoped lang="scss">

</style>