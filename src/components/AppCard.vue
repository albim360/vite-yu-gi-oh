<template>
    <div class="card">
      <div class="card-image">
        <img :src="imageUrl" alt="">
      </div>
      <div class="card-info">
        <h2>{{ name }}</h2>
        <p>{{ archetype }}</p>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    name: 'AppCard',
    props: {
      imageUrl: {
        type: String,
        required: true,
      },
      name: {
        type: String,
        required: true,
      },
      archetype: {
        type: String,
        required: true,
      },
    },
  };
  </script>
  
  <style scoped>
  .card {
    background-color: #fff;
    box-shadow: 0 2px 2px rgba(0, 0, 0, 0.2);
    border-radius: 8px;
    overflow: hidden;
  }
  
  .card-image {
    height: 200px;
    display: flex;
    justify-content: center;
    align-items: center;
  }
  
  .card-image img {
    height: 100%;
  }
  
  .card-info {
    padding: 20px;
    text-align: center;
  }
  
  .card-info h2 {
    margin-top: 0;
    margin-bottom: 10px;
  }
  
  .card-info p {
    margin-top: 0;
    margin-bottom: 0;
  }
  </style>
  