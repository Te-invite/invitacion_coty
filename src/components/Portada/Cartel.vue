<script>
import Cartel from '@/assets/img/marco.webp';
export default {
    name:'Cartel',
    data(){
        return{
            Cartel,
            subtitle:'¡Únete a la celebración de...!',
            title:'Coty',
            title2: 'Mis 15 años'
        }
    }
}
</script>
<template>
    <div class="container_cartel">
        <img :src="Cartel" class="imagen_1" alt="marco">
        <div class="contantent_text">
            <p class="subtitulo_cartel">{{ subtitle }}</p>
            <h1 class="titulo_cartel">{{ title }}</h1>
            <h3 class="titulo_cartel2">{{ title2 }}</h3>
        </div>
        
    </div>
</template>
<style>
.container_cartel{
    width:320px;
    height: 246px;
    display: flex;
    justify-content: center;
    align-items: center;
    position:relative;
}
.imagen_1{
    width:100%;
    height:100%;
    object-fit: contain;
    
}
.contantent_text{
    position:absolute;
    width:100%;
    height:80%;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
}

.subtitulo_cartel{
    font-family: var(--body-font);
    color:var(--second-text-color);
    font-size: .7rem;
    text-align: center;
}
.titulo_cartel2,
.titulo_cartel{
    font-family: var(--portada-font);
    color:var(--title-color);
    text-align: center;
}

.titulo_cartel{
    font-size: 5.5rem;
    line-height: 100%;
    line-height: 70%;
    
}
.titulo_cartel2{
    font-size: var(--h2-font-size);
    font-weight: 900;
}
@media (min-width: 1025px) {
    .container_cartel{
        width:900px;
        height:350px;
    }
    .subtitulo_cartel{
        font-size: var(--h2-font-size);
    }
    .titulo_cartel{
        font-size: 9rem;
    }
}
</style>