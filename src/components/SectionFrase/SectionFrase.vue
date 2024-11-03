<script>
import ComillaApertura from '../icons/ComillaApertura.vue'
import ComillaCierre from '../icons/ComillaCierre.vue'

export default {
    name:'SectionFrase',
    data(){
        return{
            text:'Te espero para compartir la alegría de Una noche que será mágica, inolvidable y única.'
        }
    },
    components:{
        ComillaApertura, ComillaCierre
    }
}
</script>
<template>
    <div class="container_frase">
        <ComillaApertura/>
        <span class="content_text" >
            <h4 class="texto">{{ text }}</h4>
        </span>
        <ComillaCierre/>
    </div>
</template>
<style>
.container_frase{
    width:100%;
    height:180px;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: space-around;
    margin-top: 2.5rem;
}
.content_text{
    width:320px;
    height:60%;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
}
.texto{
    font-family: var(--body-font);
    font-style: var(--font-style-italic);
    font-weight: var(--font-light);
    text-align: center;
    font-size: 1rem;
}
@media (min-width: 768px) and (max-width: 991px) {
    .container_frase{
        margin:50% 0;
        width:100%;
        height:400px;
        border:1px solid blue;
    }
    .content_text{
        width:80%;
        height:60%;
    }
    .texto{
        font-size: 2rem;
    }
}
@media (min-width: 1025px) {
    .container_frase{
        margin:60% 0;
        width:100%;
        height:300px;
    }
    .content_text{
        width:80%;
        height:60%;
    }
    .texto{
        font-size: 2.5rem;
    }
}
</style>