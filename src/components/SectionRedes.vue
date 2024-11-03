<script>

import IconInstagram from '../assets/img/igwallnegro.gif';
import Swal from 'sweetalert2';
import Boton from './Boton.vue';
export default {
    name: 'SectionRedes',
    data() {
        return {
            text: 'NO PUEDEN FALTAR LOS RECUERDOS',
            hastag: '#Los15deCony',
            IconInstagram
        }
    },
    components: {

        Boton
    },
    methods: {
        copyToClipboard(text) {
            const el = document.createElement('textarea');
            el.value = text;
            document.body.appendChild(el);
            el.select();
            document.execCommand('copy');
            document.body.removeChild(el);
            Swal.fire({
                title: 'OK!',
                icon: 'success',
                text: '¡El texto ha sido copiado!',
                confirmButtonText: 'OK'
            });
        }

    }
}
</script>
<template>
    <div class="containerRedes">
        <img :src="IconInstagram" alt="icono_instagram" class="iconInst">
        <span class="content_textRedes" data-aos="flip-left">
            <h4 class="textoRedes">{{ text }}</h4>
            <p class="text_hashtag" data-aos="zoom-out-right">{{ hastag }}</p>
            <p class="tex_hashtag">Quiero ver cómo te preparás para la fiesta y todo lo que vivas en
                ella.<strong>¡etiquetame!</strong></p>
        </span>
        <Boton label="COPIAR #" customClass="btn-mayor" @click="copyToClipboard(hastag)" />
    </div>
</template>
<style>
.containerRedes {
    margin: 2rem 0;
    width: 100%;
    height: 300px;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: space-between;
}

.content_textRedes {
    width: 300px;
    height: 60%;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
}

.textoRedes {
    font-family: var(--portada-font);
    color: var(--first-text-color);
    font-weight: var(--font-light);
    text-align: center;
    font-size: 1rem;
}

.iconInst {
    width: 60px;
    height: 70px;
}

.text_hashtag {
    margin-top: 1rem;
    font-family: var(--portada-font);
    color:var(--title-color);
    font-size: 3rem;
    line-height: 100%;
    text-align: center;
}
.tex_hashtag{
    font-family: var(--body-font);
    color:var(--title-color);
    font-size: .8rem;
    text-align: center;
}

@media (min-width: 768px) and (max-width: 991px) {
    .containerRedes {
        margin: 2rem 0;
        width: 100%;
        height: 100%;
    }

    .content_textRedes {
        width: 80%;
        height: 60%;
    }

    .textoRedes {
        font-size: 3rem;
    }

    .text_hashtag {
        margin-top: 1rem;
        font-size: 2rem;
    }
}

@media (min-width: 1025px) {
    .containerRedes {
        width: 100%;
        height: 400px;
    }

    .content_textRedes {
        width: 80%;
        height: 60%;
    }

    .textoRedes {
        font-size: 3rem;
    }

    .text_hashtag {
        margin-top: 1rem;
        font-size: 2rem;
    }
}
</style>