<script>
import background2 from '../../assets/img/background_invitacion.webp'
import SectionGift from './SectionGift.vue';
import SectionMusic from './SectionMusic.vue';
import CintaPlateada from '../icons/CintaPlateada.vue';
export default {
    name: 'SectionEvento',
    data() {
        return {
            background2
        }
    },
    components: {
        SectionGift,
        SectionMusic,
        CintaPlateada,
    }
}
</script>
<template>
    <div class="container_evento">
        <img :src="background2" class="background2" alt="tapiz">

        <div class="content_evento">
            <!-- Regalos -->
            <SectionGift />
            <CintaPlateada data-aos="fade-down"/>
            <!-- Musica -->
            <SectionMusic />
        </div>
    </div>

</template>
<style>
.container_evento {
    width: 100%;
    height:auto;
    display: flex;
    flex-direction: column;
    align-items: center;
    margin-top: 1rem;
}

.background2 {
    width: 100%;
    height: 750px;
}

.content_evento {
    margin-top: 2rem;
    position: absolute;
    z-index: 0;

}

.curvaRight {
    position: absolute;
    bottom: 0%;
    right: 0;
    width: 100%;
    height: auto;
    z-index: 1;
}

@media (min-width: 768px) and (max-width: 991px) {
    .container_evento {
        margin-top:3rem;
    }
    .content_evento {
        width: 100%;
        height: auto;
    }

    .curvaRight {
        bottom: 4%;
    }

    .background2 {
        width: 100%;
        height: 90%;
    }

    .content_evento {
        margin-top: 2rem;

    }
}

@media (min-width: 1025px) {

    .content_evento {
        width: 100%;
    }

    .curvaRight {
        bottom: 0;
    }

    .background2 {
        width: 100%;
        height: 1300px;
    }
}
</style>