<script>
import Boton from '../Boton.vue';
import iconM from '../../assets/img/listadetemasnegro-1-1.gif';
import TitleSection from '../TitleSection.vue';
import Swal from 'sweetalert2';
export default {
    name:'SectionMusic',
    components:{
        TitleSection,
        Boton
    },
    data(){
        return{
            text1:'SUGIERE UN TEMA INFALTABLE PARA QUE ESTE EN ALGÚN MOMENTO DE LA NOCHE ',
            text2: '¡Hagamos juntos una fiesta inolvidable!',
            iconM 
        }
    },
    methods: {
        togglePopUp(){
            this.popup = !this.popup
        },
        redirectToSheet() {
        Swal.fire({
            title: 'Info!',
            text: 'Será redirigido a YouTube. Para continuar presione OK, o Cancelar para cerrar.',
            icon: 'info',
            showCancelButton: true, // Habilita el botón "Cancelar"
            confirmButtonText: 'OK',
            cancelButtonText: 'Cancelar', // Texto del botón "Cancelar"
        }).then((result) => {
            if (result.isConfirmed) {
                // Si el usuario presiona "OK"
                window.open("https://www.youtube.com/playlist?list=PL4WV8HJeFYo-KcVAGGmZJTnsdTZo_JGdD&jct=nUMSA2MDMc1nYvLTYnyhgA");
            } else if (result.dismiss === Swal.DismissReason.cancel) {
                // Si el usuario presiona "Cancelar", cierra el popup de SweetAlert
                this.togglePopUp();
            }
        });
    }    
    }
}
</script>
<template>
    <div  class="content_music" id="sectionmusic" data-aos="zoom-in-left">
        <TitleSection title="MÚSICA">
            <template #icon>
                <img :src="iconM" alt="icon_music" class="iconMusica">
            </template>
        </TitleSection>  
        <span class="content_text_music">
            <p class="textMusic">{{ text1 }}</p>
            <p class="textMusic1">{{ text2 }}</p>
        </span> 
        <Boton label="SUGERIR CANCIÓN" customClass="btn-mayor" @click="redirectToSheet()"/>   
    </div>
</template>
<style>
.content_music{
    margin-top:1rem;
    width:100%;
    height:100%;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
 
}
.content_text_music{
    width:300px;
    height:100%;
    display: flex;
    flex-direction: column;
    align-items: center;
}
.textMusic{
    font-family: var(--body-font);
    font-weight: var(--font-light);
    text-align: center;
    line-height:90%;
    font-size: .8rem;
}
.textMusic1{
    font-family: var(--body-font);
    font-weight: var(--font-bold);
    color:var(--first-text-color);
    line-height:100%;
    text-align: center;
    font-size: 1rem;
}
.iconMusica{
    width:60px;
    height:60px;
}
@media (min-width: 768px) and (max-width: 991px) {
    .textMusic{
        font-size: 2.5rem;
    }
}
@media (min-width: 1025px) {
    .content_music{
    width:100%;
    height:300px;
    }
    .textMusic{
        font-size: 2.5rem;
    }
}
</style>