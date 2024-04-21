<script>
export default {
    name: 'ViewCard',
    props: {
        cardInfo: Object
    },
    data() {
        return {
            suportedFlags: [
                'it',
                'en',
                'fr'
            ]
        };
    },
    methods: {
        getFlagUrl() {
            let flagImageName = this.cardInfo.original_language + '.jpg';

            
            return new URL(`../assets/img/${flagImageName}`, import.meta.url).href;
        }
    },
}
</script>

<template>
    <div class="result-card">
        <!-- TITOLO -->
        <h2>Titolo:{{ cardInfo.title ? cardInfo.title : cardInfo.name }}</h2>
        
        <!-- TITOLO ORIGINAlE -->
        <div>Titolo originale:{{ cardInfo.original_title ? cardInfo.original_title : cardInfo.original_name }}</div>

        <div class="language">Lingua:
            <img v-if="suportedFlags.includes(cardInfo.original_language)" :src="getFlagUrl()" alt="">
            <span v-else>{{ cardInfo.original_language }}</span>
        </div>
        <div>Voto: {{ cardInfo.vote_average }}</div>   

    </div>
</template>    

<style scoped lang="scss">

    .language{
        img{
            width: 50px;
        }
    }

</style>