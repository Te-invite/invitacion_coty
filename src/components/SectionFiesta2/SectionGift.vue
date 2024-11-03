<script>
import IconGift from '../icons/IconGift.vue';
import TitleSection from '../TitleSection.vue';
import Boton from '../Boton.vue';
import Swal from 'sweetalert2';
export default {
    name:'SectionGift',
    components:{
        TitleSection,
        IconGift,
        Boton
    },
    data(){
        return{
            text1:'¡En el salón habrá un urna para puedas dejar tu sobre!',
            text2:'También podes hacerlo desde acá',
            cvu:'0720155088000001807840'
            
        }
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
    <div id="gift" class="content_gift" >
        <TitleSection title="REGALOS">
            <template #icon>
                <IconGift/>
            </template>
        </TitleSection>  
        <div class="content_text_gift">
            <p class="textGift">{{ text1 }}</p>
            <p class="textGift">{{ text2 }}</p>
        </div>
        <div class="content_button">
            <Boton label="DATOS BANCARIOS" customClass="btn-mayor" @click="copyToClipboard(cvu)"/>
        </div>

    </div>
</template>
<style>
.content_gift{
    width:100%;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    margin:1.5rem 0;
}
.content_text_gift{
    width:300px;
    display:flex;
    flex-direction: column;
    justify-content: center;
    margin-bottom:.5rem;
}
.textGift{  
    font-family: var(--body-font);
    font-weight: var(--font-light);
    text-align: center;
    font-size: 1rem;
    margin:0 1rem; 
}
.content_button{
    width:100%;
    display:flex;
    flex-direction: column;
    align-items: center;
}
@media (min-width: 768px) and (max-width: 991px) {
    .textGift{
        font-size: 2.5rem;
    }
}
@media (min-width: 1025px) {
    .textGift{
        font-size: 2.5rem;
    }
}
</style>