<template>
  <div class="modal-overlay" >
    <div class="modal">
      
      <h2>Artículos · {{ item.textAlt }}</h2>
      <p>Listado de artículos </p>
      <article class="grid-item" v-for="(article, index) in item.articles">
        <a :href="article.link" target="_blank">
          {{article.title}}
        </a>
      </article>
      <button @click="$emit('close-modal')">Cerrar</button>
    </div>
  
  </div>
</template>

<script>
  export default {
    props: ['item'],
  }
</script>


<style>
  .modal-overlay {
    position: fixed;
    top: 0;
    bottom: 0;
    left: 0;
    right: 0;
    display: flex;
    justify-content: center;
    background-color: #000000da;
    .modal {
      background-color: white;
      height: 500px;
      width: 500px;
      margin-top: 50px;
      padding: 40px 60px;
      .grid-item{
        margin-bottom: 10px;
        padding: 0;
        a{
          display: block;
          width: 100%;
          padding: 20px;
          color: black;
          text-decoration: none;
        }
      }
      button {
        background-color: #ae152d;
        width: 150px;
        height: 40px;
        color: white;
        font-size: 14px;
        margin-top: 50px;
        border: none;
      }
    }
  }
  
</style>