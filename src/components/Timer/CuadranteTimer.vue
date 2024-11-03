<script>

import TimerVue from './Timer.vue'
export default {
    name:'CuadranteTimer',
    components:{TimerVue},
    
}
</script>
<template>
    <div class="backImg">
        <TimerVue class="timer"/>
    </div>
</template>
<style>
.backImg{
    width:100%;
    height:300px;
    background-image: url('../../assets/img/cuadrante.svg');
    background-size: cover;
    background-position: center;
    display: flex;
    flex-direction: column;
    justify-content: center;
    position: relative;
}
.timer{
    position: absolute;
    z-index: 2;
}
@media (min-width: 768px) and (max-width: 991px) {
    .backImg{
        width:100%;
        height:600px;
    }
}
@media (min-width: 1025px) {
    .backImg{
        width:100%;
        height:950px;
    }
}
</style>