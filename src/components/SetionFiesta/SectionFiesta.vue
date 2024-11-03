<script>
import TitleSection from '../TitleSection.vue';
import iconFiesta from '../../assets/img/fiestamarronclaro1.gif'
import FormularioAsistencia from '../FormularioAsistencia.vue';
import imgen3 from '../../assets/img/imgen3.webp';
import imagen2 from '../../assets/img/img2.webp';
import Boton from '../Boton.vue';
import Carrusel from '../Carrusel.vue';
export default {
    name:'SectionFiesta',
    components:{
        TitleSection,
        FormularioAsistencia,
        Boton,
        Carrusel
    },
    data(){
        return{
            frase:'¡Armemos tremendo fiestón!',
            iconFiesta,
            mapUrl:'https://maps.app.goo.gl/MsACbqgvppbFmEzp6',
            imgen3,
            imagen2
        };
    },
    methods:{
        openMap(){
            window.open(this.mapUrl, '_blank');
        }   
    }
  
}
</script>
<template>
    <div id="fiesta" class="container_fiesta" >
        <!--Titulo de la sesion-->
        
        <TitleSection title="FIESTA">
            <template #icon>
                <img :src="iconFiesta" alt="" class="iconFiesta">
            </template>
        </TitleSection>
        <!--Frase-->
        <span class="content_fraseFiesta" data-aos="fade-down-left">
            <p class="textFraseFiesta text1">{{ frase }}</p>
            <p class="textFraseFiesta text2">Te espero en la <strong>Sociedad Italiana</strong> a las 21:00 h.</p>
        </span>
        <Boton label="¿CÓMO LLEGAR?" customClass="btn-mayor" @click="openMap()"/>
        <div class="sesionCarrusel">
            <img :src="imgen3" alt="plumas superiores" class="plumasTop" data-aos="fade-left">
            <Carrusel/>
            <img :src="imagen2" alt="plumas inferiores" class="plumasBottom" data-aos="fade-right">
        </div>
        
        <FormularioAsistencia/>
    </div>
    
</template>
<style>
.container_fiesta{
    width:100%;
    height:100%;
    display:flex;
    flex-direction: column;
    align-items: center;    
    margin-top:1rem;
}
.content_fraseFiesta{
    width:260px;
    height:100%;
    display:flex;
    flex-direction: column;
    justify-content: center;
}
.textFraseFiesta{
    text-align: center;
    font-family: var(--body-font);
    font-size:1rem;
    color:var(--first-text-color);
}
.text1{
    font-weight: normal;
    line-height:60%;
}
.text2{
    font-weight: lighter;
    line-height:100%;
}
.iconFiesta{
    width:60px;
    height:60px;
}
.sesionCarrusel{
    position: relative;
}

.plumasTop{
    position:absolute;
    right:5%;
    top: -25%;
    z-index:2;
}
.plumasBottom{
    position:absolute;
    left:5%;
    bottom:-25%;
    z-index:2;
}
@media (min-width: 768px) and (max-width: 991px) {
    .container_fiesta{
        margin-top:5rem;
        width:100%;
        height:1300px;
    }
    .textFraseFiesta{
        font-size:2rem;
    }
    .curvaLeftPlateada{
        bottom:-15%;
    }
}

@media (min-width: 1025px) {
    .container_fiesta{
        margin-top:5rem;
        width:100%;
        min-height:1500px;
        margin-bottom:10%;
    }
    .textFraseFiesta{
        font-size:2rem;
    }
    .curvaLeftPlateada{
        bottom:-20%;
    }
}
</style>


