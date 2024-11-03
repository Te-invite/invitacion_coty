<script>
import foto1 from '../assets/img/carrusel1.jpg';
import foto2 from '../assets/img/carrusel2.jpg';
import foto3 from '../assets/img/carrusel3.jpg';


export default {
  name: 'Carrousel',
  data() {
    return {
      foto1,
      foto2,
      foto3

    }
  }
}
</script>
<template>
  
  <div class="container_carrousel" data-aos="fade-up">
    <div id="carouselExampleFade" class="carousel slide carousel-fade carousel_photo" data-bs-ride="carousel" data-bs-interval="2500">
    <div class="carousel-inner">
      <div class="carousel-item active">
        <img :src="foto1" class="d-block w-100" alt="...">
      </div>
      <div class="carousel-item">
        <img :src="foto2" class="d-block w-100" alt="...">
      </div>
      <div class="carousel-item">
        <img :src="foto3" class="d-block w-100" alt="...">
      </div>
    </div>
    <button class="carousel-control-prev" type="button" data-bs-target="#carouselExampleFade" data-bs-slide="prev">
      <span class="carousel-control-prev-icon" aria-hidden="true"></span>
      <span class="visually-hidden">Previous</span>
    </button>
    <button class="carousel-control-next" type="button" data-bs-target="#carouselExampleFade" data-bs-slide="next">
      <span class="carousel-control-next-icon" aria-hidden="true"></span>
      <span class="visually-hidden">Next</span>
    </button>
  </div>
  
  </div>
</template>
<style>
.container_carrousel{
  width:100%;
  height:100%;
  margin: 1.5rem;
}
.carousel_photo{
  min-width: 100vw;
}

</style>