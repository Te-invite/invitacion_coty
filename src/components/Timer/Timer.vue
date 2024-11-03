<script>
import Counter from './Counter.vue';
export default {
    name: 'Timer',
    components: { Counter }
};
</script>

<template>
    <div class="section__timer" data-aos="zoom-in">
        <div class="countdown">
            <!--Cargar fecha-->
            <counter :year="2024" :month="12" :date="14" :hour="21" :minute="00" :second="0" :millisecond="31" />
        </div>
    </div>
</template>

<style scoped>
.section__timer{
    width:100%;    
}

@media (min-width: 768px) and (max-width: 991px) {
    .section__timer{
    width:100%;    
}
}

@media (min-width: 1025px) {
    .section__timer {
        width: 100%;
    }

    .background_count {
        width: 100%;
    }
}
</style>