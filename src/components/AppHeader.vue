<template>
  <header class="header">
    <div class="container">
      <div class="logo">
        <img src="../assets/logo.png" alt="Yu-Gi-Oh! logo" />
      </div>
      <div class="title">Yu-Gi-Oh Card</div>
    </div>
  </header>
</template>

<script>
export default {
  name: 'AppHeader',
  methods: {
    searchCard(event) {
      const cardName = event.target.value.trim();
      if (cardName) {
        this.$emit('search', cardName);
      }
    }
  }
};
</script>

<style lang="scss" scoped>
@import "../style/general.scss";

.header {
  background-color: #fff;
  border-bottom: 1px solid #eaeaea;
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 10px;
}

.logo img {
  height: 50px;
}

.title {
  font-size: 24px;
  font-weight: bold;
  color: goldenrod;
}

/** .searchBar > input {
  width: 333px; 
}**/
</style>
