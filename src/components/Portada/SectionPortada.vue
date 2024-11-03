<script>
import Cartel from './Cartel.vue';
import PanelControl from './PanelControl.vue';
export default {
    name:'SectionPortada',
    components:{
        Cartel,
        PanelControl
    }, 
    data(){
        return{
            subtitle:"La música de fondo es una parte esencial de la experiencia."
        }
    }
}
</script>
<template>
    <div class="container_portada container">
        <Cartel/>
        <span class="container_text_portada">
            <h1 class="subtitle_portada">{{ subtitle }}</h1>
        </span>
        <PanelControl/>
    </div>
</template>
<style>
.container_portada{
    background-image:url('@/assets/img/background_home.webp') ;
    width: 100%;
    height:100vh;
    object-fit: cover;
    background-position: cover;
    background-repeat: no-repeat;
    overflow: hidden;
}
.container{
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
}
.container_text_portada{
    display: flex;
    width:300px;
    justify-content: center;
    margin-top: 1rem;
}

.subtitle_portada{
    font-family: var(--body-font);
    color:var(--second-text-color);
    font-size: .7rem;
    text-align: center;
}
@media (min-width: 1025px) {
    .container_portada{
        min-width: 100vw;
        height:100vh;
        background-repeat: repeat;
    }
}
</style>