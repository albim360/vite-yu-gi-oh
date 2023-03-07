<template>
  <main class="main">
    <div class="container">
      <div class="searchBar">
        <input type="search" name="" id="" placeholder="Cerca una carta" v-model="filter" />
      </div>
      <div class="cards">
        <AppCard v-for="card in cards" :key="card.id" :image-url="card.card_images[0].image_url" :name="card.name" :archetype="card.archetype" />
      </div>
    </div>
  </main>
</template>

<script>
import axios from 'axios';
import AppCard from './AppCard.vue';

export default {
  name: 'AppMain',
  components: {
    AppCard,
  },
  props: {
    filter: {
      type: String,
      default: '',
    },
  },
  data() {
    return {
      cards: [],
    };
  },
  watch: {
    filter: function(newVal) {
      this.getCards(newVal);
    },
  },
  created() {
    this.getCards(this.filter);
  },
  methods: {
    getCards(filter) {
      let url = 'https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0';
      if (filter) {
        url += `&fname=${filter}`;
      }
      axios.get(url).then((response) => {
        this.cards = response.data.data;
      });
    },
  },
};
</script>

<style lang="scss" scoped>
.main {
  background-color: bisque;
  margin: 10px 0;
}

.searchBar {
  padding: 20px 0;
}

.searchBar > input {
  width: 15%;
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
