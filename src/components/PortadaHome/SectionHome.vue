<script>
import imgPortada from '../../assets/img/img_portada.webp';
import TituloPortada from './TituloPortada.vue';
import pluma1 from '../../assets/img/img1.webp'
export default {
    name:'SectionHome',
    data(){
        return{
            imgPortada, 
            pluma1       
        }
    },
    components:{
        TituloPortada
    }


}
</script>
<template>
    <div class="container_portada_home">
        <img :src="imgPortada" class="fotoPortada overlay" alt="foto">
        <!--titulo-->
        <div class="container_title_portada">
            <img :src="pluma1" alt="pluma" class="pluma1" data-aos="fade-right">
            <TituloPortada class="tit_portada"/>
        </div>
    </div>
</template>
<style>
.container_portada_home{
    width:100%;
    height:587px;
    display:flex;
    flex-direction: column;
}
.fotoPortada{
    width:100%;
    height:100%;
    object-fit: cover;
    position:relative;
}
.container_title_portada{
    display: flex;
    height:240px;
    width:100%;
    flex-direction: column;
    justify-content: flex-start;
    align-content: center;
    position: absolute;
    z-index: 3;
    top:60%;
    right:0;
}
.tit_portada{
    position: relative;
    z-index: 3;
}
.pluma1{
    position: absolute;
    top:25%;
    left:0%;
}
@media (min-width: 768px) and (max-width: 991px) {
    .container_title_portada{
        width:100%;
        height:600px;
        top: 70%;
        margin-bottom: 2rem;
    }
    .fotoPortada{
        width:100vw;
        height:950px;
    }
    .pluma1{
        width: 300px;
        height:auto;
        top:25%;
    }
}

@media (min-width: 1025px) {
    
    .fotoPortada{
        width:100%;
        height:1000px;
    }
    .container_title_portada{
        height:400px;
        width:100%;
        top:90%;
    }
    .pluma1{
        width: 300px;
        height:auto;
        top:25%;
    }
}
</style>