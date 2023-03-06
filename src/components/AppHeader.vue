<template>
    <header class="header">
      <div class="container">
        <div class="logo">
          <img src="/assets/logo.png" alt="Yu-Gi-Oh! logo" />
        </div>
        <div class="title">Yu-Gi-Oh Card</div>
      </div>
    </header>
  </template>
  
  <style lang="scss" scoped>
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
  }
  </style>
  