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
                'fr',
                'de',
                'es',
                'ja',
            ]
        };
    },
    methods: {
        getFlagUrl() {
            let flagImageName = this.cardInfo.original_language + '.jpg';
            return new URL(`../assets/img/${flagImageName}`, import.meta.url).href;
        },

        convertToStars(vote) {
            return Math.ceil(vote / 2);
        }
    }
}
</script>

<template>
    <div class="result-card">
      <div class="image-media">
        <img :src="'https://image.tmdb.org/t/p/w342' + cardInfo.poster_path" class="card-img" alt="" />
        <div class="card-overlay">
          <div class="card-info">
            <h2>{{ cardInfo.title ? cardInfo.title : cardInfo.name }}</h2>
            <div class="original-title">
              {{ cardInfo.original_title ? cardInfo.original_title : cardInfo.original_name }}
            </div>
            <div class="language">
              <img
                v-if="suportedFlags.includes(cardInfo.original_language)"
                :src="getFlagUrl()"
                :alt="cardInfo.original_language"
              />
              <span v-else>{{ cardInfo.original_language }}</span>
            </div>
            <div class="vote">
                <i class="fa-solid fa-star" v-for="i in convertToStars(cardInfo.vote_average)" :key="i"></i>
            </div>
          </div>
        </div>
      </div>
    </div>
</template>


<style scoped lang="scss">
.result-card {
  background-color: #222;
  color: #fff;
  border-radius: 8px;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
  transition: transform 0.3s ease;
  overflow: hidden;
  position: relative;

  &:hover {
    transform: translateY(-5px);

    .card-img {
      transform: scale(1.05);
    }

    .card-overlay {
      opacity: 1;
      transform: translateY(0);
    }
  }
}

.image-media {
  width: 200px;
  position: relative;
  margin: 1px;
}

.card-img {
  width: 200px;
  max-width: 200px;
  border-radius: 8px 8px 0 0;
  transition: transform 0.3s ease;
}

.card-overlay {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.6);
  opacity: 0;
  transition: opacity 0.3s ease, transform 0.3s ease;
  border-radius: 0 0 8px 8px;
  display: flex;
  align-items: center;
  justify-content: center;
  transform: translateY(100%);
  z-index: 1;
}

.card-info {
  text-align: center;
  padding: 20px;
}

h2 {
  font-size: 20px;
  font-weight: bold;
  margin-bottom: 8px;
  text-shadow: 0 2px 4px rgba(0, 0, 0, 0.5);
}

.original-title {
  font-size: 16px;
  margin-bottom: 8px;
  text-shadow: 0 2px 4px rgba(0, 0, 0, 0.5);
}

.language {
  display: flex;
  align-items: center;
  justify-content: center;
  margin-bottom: 8px;

  img {
    width: 80px;
    height: 50px;
    margin-right: 8px;
  }
}

.vote {
  color: #ffc107;
  font-weight: bold;
  display: flex;
  align-items: center;
  justify-content: center;
  text-shadow: 0 2px 4px rgba(0, 0, 0, 0.5);

  .material-icons {
    font-size: 18px;
    margin-right: 4px;
  }
}

</style>