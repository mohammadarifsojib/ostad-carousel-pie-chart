<script setup>
    import {ref, onBeforeUnmount, onMounted} from 'vue';

    const items = ref([
        './carousel-1.jpg',
        './carousel-2.jpg',
        './carousel-3.jpg',
        './carousel-4.jpg',
        './carousel-5.jpg'
    ]);

    let carousel = ref(null);

    onBeforeUnmount(() => {
        if (carousel) {
            carousel.destroy();
        }
    })

    onMounted(()=>{
        carousel = new Flickity('#carousel',{})
    })
</script>

<template>
    <div>
        <div class="mx-auto items" id="carousel">
            <div :style="`background-image:url(${item})`" class="item relative" v-for="item, index in items" :key="item">
                <div class="absolute top-0 left-0 w-full h-full bg-black opacity-50"></div>
            </div>
          </div>
    </div>
</template>

<style>
.items {
    width: 600px;
    height: 400px;
  }
  
  .item {
    width: 600px;
    height: 400px;
    background-color: #ccc;
    background-size: cover;
    background-position: center;
  }
  .flickity-button-icon {
    fill: white;
  }
  .flickity-button {
    background: #3898db;
  }
  .flickity-button:hover {
    background: #F90;
  }
  
  .flickity-prev-next-button {
    width: 30px;
    height: 30px;
    border-radius: 5px;
  }
  /* icon color */
  .flickity-button-icon {
    fill: white;
  }
 
  @media screen and (max-width: 768px) {
    .items {
      width: 100%;
      margin: 0 auto;
    }
    .item {
      width: 100%;
      margin: 0 auto;
    }
    
  }
</style>