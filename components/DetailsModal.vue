<template>
  <div class="modal-overlay" @click="$emit('close-modal')">
    <div class="modal">
      
      <h2>Artículos · </h2>
      <p>Listado de artículos de Google Scholar</p>
      
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
  }

  .modal {

    background-color: white;
    height: 500px;
    width: 500px;
    margin-top: 50px;
    padding: 40px 60px;
    
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
</style>