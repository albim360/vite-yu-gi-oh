<template>
    <main class="main">
      <div class="container">
        <div class="cards">
          <AppCard
            v-for="card in cards"
            :key="card.id"
            :image-url="card.card_images[0].image_url"
            :name="card.name"
            :archetype="card.archetype"
          />
        </div>
      </div>
    </main>
  </template>
  
  <script>
  import axios from 'axios';
  import AppCard from './AppCard.vue';
  import AppMain from './AppMain.vue'
  
  export default {
    name: 'AppMain',
    components: {
      AppCard,
    },
    data() {
      return {
        cards: [],
      };
    },
    created() {
      axios
        .get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0')
        .then((response) => {
          this.cards = response.data.data;
        });
    },
  };
  </script>
  
  <style lang="scss" scoped>
  .main {
    background-color: #f4f4f4;
  }
  
  .container {
    max-width: 1200px;
    margin: 0 auto;
  }
  
  .cards {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
    grid-gap: 20px;
  }
  </style>
  