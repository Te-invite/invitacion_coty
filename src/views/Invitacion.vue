<script>
import SectionHome from '../components/PortadaHome/SectionHome.vue';
import CurvaOscura from '../components/icons/CurvaOscura.vue';
import NameVue from "../components/NameVue.vue";
import SesionFrase from '../components/SectionFrase/SesionFrase.vue';
import SectionFiesta from '../components/SetionFiesta/SectionFiesta.vue';
import SectionEvento from '../components/SectionFiesta2/SectionEvento.vue';
import SectionRedes from '../components/SectionRedes.vue';
import SectionFooter from '../components/SectionFooter.vue';
import BotonAudio from "../components/BotonAudio.vue";
import CuadranteTimer from '../components/Timer/CuadranteTimer.vue';
import plumaDerec from '../assets/img/imagen0.webp';
import CurvaRightPlateada from '../components/icons/CurvaRightPlateada.vue';
import CurvaLeftPlateada from '../components/icons/CurvaLeftPlateada.vue';
export default {
    name:'Invitacion',
    components:{
        SectionHome,
        CurvaOscura,
        SesionFrase,
        SectionFiesta,
        SectionEvento,
        SectionRedes,
        SectionFooter,
        BotonAudio,
        NameVue,
        CuadranteTimer,
        CurvaRightPlateada,
        CurvaLeftPlateada
    },
    methods: {
        scrollTo(hash) {
            const element = document.querySelector(hash);
            if (element) {
                element.scrollIntoView({ behavior: 'smooth' });
            }
        }
    },
    data(){
        return {
            plumaDerec
        }
    }
}
</script>
<template>
    <div class="container_invitacion">
        <!--Portada Home -->
        <div class="portada_home">
            <CurvaOscura class="curva_oscura" />     
            <SectionHome/>
        </div>
        <!--Nombre-->
        <NameVue/>
        <!-- Frase -->
        <SesionFrase/>
        <!--Temporizador-->
        <div class="sectionTimer">
            <img :src="plumaDerec" alt="plumas" class="plumaDerec" data-aos="fade-left">
            <CuadranteTimer/>
        </div>
        <!-- Sesion Fiesta -->
        <SectionFiesta/>
        <div class="sesionEvento">
            <CurvaRightPlateada class="curvaR"/>
            <CurvaLeftPlateada class="curvaL"/>
            <SectionEvento/>
        </div>
        <SectionRedes/>
        <BotonAudio class="=btnMusic"/>
        <div class="sesionesTarjetas">
            <div class="opciones">
            <a href="#fiesta" class="opcion" @click.prevent="scrollTo('#fiesta')">FIESTA</a>
            <a href="#asistencia" class="opcion" @click.prevent="scrollTo('#asistencia')">ASISTENCIA</a>
            <a href="#gift" class="opcion" @click.prevent="scrollTo('#gift')">REGALOS</a>
            <a href="#sectionmusic" class="opcion" @click.prevent="scrollTo('#sectionmusic')">MÚSICA</a>
        </div>
        </div>
         <SectionFooter/>
        
    </div>
</template>
<style>

.container_invitacion{
    width:100%;
    min-height: 100vh;
    overflow-x: hidden;
    display: flex;
    flex-direction: column;
    align-content: center;
    justify-content: space-around;
}
.portada_home{
    width:100%;
    height:587px;
    position:relative;
    display:flex;
    justify-content: center;
    margin-bottom:3rem;
}
.curva_oscura{
    left: 0;
    bottom:10%;
    position:absolute;
    z-index:3;
    
}

.curva_oscura{
    bottom:-25%;
}
.sectionTimer{
    width:100%;
    position: relative;

}
.plumaDerec{
    position: absolute;
    right: 0;
    bottom:40%;
    z-index: 2;
}
.section_frase{
    position:relative;
}
.box_section{
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
}
.box_section {
    font-size: .5rem;
}
.curvaR{
    position:absolute;
    top:-6%;
    right:0;
}
.curvaL{
    position:absolute;
    bottom:-6%;
    left:0;
}
.sesionEvento{
    width:100%;
    height:100%;
    position:relative;
}
.opcion_menu {
    margin-left: 1rem;
    font-family: var(--font_family_principal);
    color: var(--color__font_primary);
    font-size: .6rem;
    text-decoration: none;

    font-style: italic;
}
.sesionesTarjetas{
    width: 100%;
    display: flex;
    flex-direction: column;
    align-items: center;
}
.opciones {
    width: 90%;
    display: flex;
    flex-direction: row;
    justify-content: space-around;
    align-items: center;
}

.opcion {
    font-family: "Playfair";
    font-style: italic;
    font-size: .5rem;
    text-align: center;
    color: #8b8b8b;
    text-decoration: none;
}
@media (min-width: 768px) and (max-width: 991px) {
    .portada_home{
        width: 100%;
        height:570px;
        border:1px solid red;
    }
    .container_invitacion{
        width:100%;
        max-height: 100%;
    }
    .curva_oscura{
        bottom:-0%;
    }
 
    .opcion {
        font-size: 1rem;
    }
    
}
@media (min-width: 1025px) {
    .container_invitacion{
        width:100%;
        max-height: 100%;
    }
    .curva_oscura{
        bottom:-120%;
    }

    .opcion {
        font-size: 1.5rem;
    }
}
</style>