<template>
  <main>
    <NuxtRouteAnnouncer />
    <div class="decoration-bar"></div>
    <header>
      <h1>Revista PÁTINA · ESCRBC</h1>
      <h2>Número actual</h2>
      <p>Estamos trabajando en el número actual de la revista pátina.<br> 
        Si quieres ser revisor escríbenos aquí. Si quieres enviar un artículo, escríbenos aquí.</p>
    </header>
    
    <section class="grid-container">
      <h2>Números anteriores</h2>
      
        <article class="grid-item" v-for="(item, index) in items">
            <img :src="`/images/${item.imgURL}.png`" :alt="item.textAlt" @click="showModal = true; currentItem = index + 1">
          <h3>{{ item.numero }}</h3>
          <div class="grid-item-links">
            <a :href="item.drivePdfDownload" target="_blank" download>Descargar PDF</a>
            <a :href="item.drivePdfView" target="_blank">Ver PDF</a> 
          </div>
        </article>
        <DetailsModal v-show="showModal" @close-modal="showModal = false" :item="items[currentItem - 1]" />
    </section>
    
    <FooterBlock />
  
  </main>
</template>

<style>
  @font-face {
      font-family: 'Butler';
      src: url('/fonts/Butler-Bold.woff2') format('woff2'),
          url('/fonts/Butler-Bold.woff') format('woff');
      font-weight: bold;
      font-style: normal;
  }

  body{
    margin: 0;
  }

  header{
    padding: 20px 40px;
  }
  h1, h2, a{
    font-family: sans-serif;
    font-family: 'Butler';
  }
  .decoration-bar{
    height: 50px;
    width: 100%;
    background-color: #ae152d;
  }
  .grid-container{
    padding: 20px 40px;
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: 20px;
    h2{
      grid-column: 1 / -1;
    }
  }
  .grid-item {
    transition: all .3s ease-in-out;
    background-color: #f0f0f0;
    padding: 20px;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    &:hover{
      scale: 1.05;

    }
    img{
      object-fit: cover;
      height: 200px;
      width: 100%;
      display: block;
    }
    .grid-item-links{
      display: flex;
      justify-content: space-between;
      margin-top: 20px;
      a{
        display: block;
        padding: 5px;
        color: gray;
        text-decoration: none;
        transition: all .5s ease-in-out;
        &:hover{
          background-color: white;
          color: black;
          text-decoration: underline;
        }
      }
      
    }
  }

</style>


<script>

import DetailsModal from '../components/DetailsModal.vue'
import FooterBlock from '../components/FooterBlock.vue'

export default {
  components: { DetailsModal, FooterBlock },
  data() {
    
    return {
      showModal: false,
      currentItem: "1",
      items: ref([
        {  
          textAlt: "Primer número Revista Pátina",
          imgURL: "1",
          numero: "Número 1",
          drivePdfView: 'https://drive.google.com/file/d/1nbdy_H0RzbjSL29R7iydnxykiCWCd1GV/view',
          drivePdfDownload: "https://drive.google.com/uc?export=download&id=1nbdy_H0RzbjSL29R7iydnxykiCWCd1GV",
          articles:[
            { key: 1, title: "Articulo 1", link: "#" },
            { key: 2, title: "Articulo 2", link: "#" }
          ]
        }, 
        { 
          textAlt: "Número 2 Revista Pátina",
          imgURL: "2",
          numero: "Número 2",
          drivePdfView: 'https://drive.google.com/file/d/129zUD0sCeV6DwWc3IO_Y21LoO7ByDTK6/view',
          drivePdfDownload: "https://drive.google.com/uc?export=download&id=129zUD0sCeV6DwWc3IO_Y21LoO7ByDTK6",
          articles:[
  
          ]
        }, 
        { 
          textAlt: "Número 3 Revista Pátina",
          imgURL: "3",
          numero: "Número 3",
          drivePdfView: 'https://drive.google.com/file/d/17ADO6ic__pNd7kJxcOskZ-7C2tqL9kN8/view',
          drivePdfDownload: "https://drive.google.com/uc?export=download&id=17ADO6ic__pNd7kJxcOskZ-7C2tqL9kN8",
          articles:[
     
          ]
        }, 
        { 
          textAlt: "Número 4 Revista Pátina",
          imgURL: "4",
          numero: "Número 4",
          drivePdfView: 'https://drive.google.com/file/d/1OdnoJ_87YFStNxXdVgu3Kop3hJnEkP0l/view',
          drivePdfDownload: "https://drive.google.com/uc?export=download&id=1OdnoJ_87YFStNxXdVgu3Kop3hJnEkP0l",
          articles:[
    
          ]
        }, 
        { 
          textAlt: "Número 5 Revista Pátina",
          imgURL: "5",
          numero: "Número 5",
          drivePdfView: 'https://drive.google.com/file/d/1z_g5JSVb3abEz2cc-w_K5CFvxnzxYNTm/view',
          drivePdfDownload: "https://drive.google.com/uc?export=download&id=1z_g5JSVb3abEz2cc-w_K5CFvxnzxYNTm",
          articles:[
  
          ]
        }, 
        { 
          textAlt: "Número 6 Revista Pátina",
          imgURL: "6",
          numero: "Número 6",
          drivePdfView: 'https://drive.google.com/file/d/1t5kyEgHSDCJ2_zqWDKzSJt2fpYOo8HMk/view',
          drivePdfDownload: "https://drive.google.com/uc?export=download&id=1t5kyEgHSDCJ2_zqWDKzSJt2fpYOo8HMk",
          articles:[
     
          ]
        }, 
        { 
          textAlt: "Número 7 Revista Pátina",
          imgURL: "7",
          numero: "Número 7",
          drivePdfView: 'https://drive.google.com/file/d/1c3WtmGhJFjsUVbGJACsq9GIlCPiJUks8/view',
          drivePdfDownload: "https://drive.google.com/uc?export=download&id=1c3WtmGhJFjsUVbGJACsq9GIlCPiJUks8",
          articles:[
 
          ]
        }, 
        { 
          textAlt: "Número 8 Revista Pátina",
          imgURL: "8",
          numero: "Número 8",
          drivePdfView: 'https://drive.google.com/file/d/1Jy09mNbgRf9WQLuSqft4XpF6LyCXo8de/view',
          drivePdfDownload: "https://drive.google.com/uc?export=download&id=1Jy09mNbgRf9WQLuSqft4XpF6LyCXo8de",
          articles:[
     
          ]
        }, 
        { 
          textAlt: "Número 9 Revista Pátina",
          imgURL: "9",
          numero: "Número 9",
          drivePdfView: 'https://drive.google.com/file/d/1QvHui9pmS7rZjV93vGsKF--FIKFJ7Gg1/view',
          drivePdfDownload: "https://drive.google.com/uc?export=download&id=1QvHui9pmS7rZjV93vGsKF--FIKFJ7Gg1",
          articles:[
      
          ]
        }, 
        { 
          textAlt: "Números 10 y 11 Revista Pátina",
          imgURL: "10_11",
          numero: "Números 10 y 11",
          drivePdfView: 'https://drive.google.com/file/d/1RYjAHyeY1X45GYewT2Oj7piR3qaQp4Te/view',
          drivePdfDownload: "https://drive.google.com/uc?export=download&id=1RYjAHyeY1X45GYewT2Oj7piR3qaQp4Te",
          articles:[
     
          ]
        }, 
        { 
          textAlt: "Número 12 Revista Pátina",
          imgURL: "12",
          numero: "Número 12",
          drivePdfView: 'https://drive.google.com/file/d/1CAMk6QkWEDuCx3CaCuh51zc-WEHcdz19/view',
          drivePdfDownload: "https://drive.google.com/uc?export=download&id=1CAMk6QkWEDuCx3CaCuh51zc-WEHcdz19",
          articles:[
     
          ]
        },
        { 
          textAlt: "Números 13 y 14 Revista Pátina",
          imgURL: "13_14",
          numero: "Números 13 y 14",
          drivePdfView: 'https://drive.google.com/file/d/16GnCNK2QD_0k0-GffF85KP59e5HpUyA7/view',
          drivePdfDownload: "https://drive.google.com/uc?export=download&id=16GnCNK2QD_0k0-GffF85KP59e5HpUyA7",
          articles:[
   
          ]
        },
        { 
          textAlt: "Número 15 Revista Pátina",
          imgURL: "15",
          numero: "Número 15",
          drivePdfView: 'https://drive.google.com/file/d/1wKDqfTeho-GrqpncvHt6wzNkk2Tp9a3M/view',
          drivePdfDownload: "https://drive.google.com/uc?export=download&id=1wKDqfTeho-GrqpncvHt6wzNkk2Tp9a3M",
          articles:[
    
          ]
        },
        { 
          textAlt: "Número 16 Revista Pátina",
          imgURL: "16",
          numero: "Número 16",
          drivePdfView: 'https://drive.google.com/file/d/1Cs9Kg1DudCRWFOVFrVXurpS3j9zjVF88/view',
          drivePdfDownload: "https://drive.google.com/uc?export=download&id=1Cs9Kg1DudCRWFOVFrVXurpS3j9zjVF88",
          articles:[
   
          ]
        },
        { 
          textAlt: "Números 17 y 18 Revista Pátina",
          imgURL: "17_18",
          numero: "Números 17 y 18",
          drivePdfView: 'https://drive.google.com/file/d/1AL7Tzh71xKfhdD2T-J3KksTahh2UGs4b/view',
          drivePdfDownload: "https://drive.google.com/uc?export=download&id=1AL7Tzh71xKfhdD2T-J3KksTahh2UGs4b",
          articles:[
        
          ]
        },
        { 
          textAlt: "Número 19 Revista Pátina",
          imgURL: "19",
          numero: "Número 19",
          drivePdfView: 'https://drive.google.com/file/d/1nOhOI4cL-bhDufi1Qnqk81tSwR24kgDz/view',
          drivePdfDownload: "https://drive.google.com/uc?export=download&id=1nOhOI4cL-bhDufi1Qnqk81tSwR24kgDz",
          articles:[
     
          ]
        }
      ]),
        
      
    };
  }
};
</script>