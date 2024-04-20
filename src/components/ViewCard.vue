<script>
export default {
    name: 'ViewCard',
    props: {
        cardInfo: Object
    }
}
</script>

<template>
    <div class="result-card">
        <h2>Titolo: {{ cardInfo.title }}</h2>
        <div>Titolo: {{ cardInfo.original_title }}</div>
        <div>Lingua: {{ cardInfo.original_language }}</div> 
        <div>Voto: {{ cardInfo.vote_average }}</div>   

    </div>
</template>    

<style scoped lang="scss">

</style>