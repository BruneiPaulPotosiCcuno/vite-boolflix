<script>
export default {
    name: 'AppHeader'
}
</script>

<template>
    <header>
        <AppHeader></AppHeader>
        <AppSearch  @searchFilm="getMoviesFromApi">Search</AppSearch>
        <ListMovies></ListMovies>
    </header>
</template>

<style scoped lang="scss">

@use '../style/partials/variables' as *;

</style>