<script>
import numero from '../../assets/img/xv.webp';
export default {
    name:'TituloPortada',
    data(){
        return{
            numero,
            subtitle:'14 . 12 . 2024'
        }
    }
}
</script>
<template>
    <div class="container_title-portada" data-aos="zoom-in-up">
        <img :src="numero" alt="numero" class="numero" data-aos="fade-down">
        <div class="line"></div>
        <div class="title_portada" data-aos="zoom-in">{{ subtitle }}</div>
        <div class="line"></div>

    </div>
</template>
<style>
.container_title-portada{
    width:100%;
    height: 70%;
    position:absolute;   
    display:flex;
    flex-direction: column;
    align-items: center;
    justify-content: space-around;
    z-index: 2; 
}
.numero{
    width:176px;
    height:auto;
}
.title_portada{
    font-family: var(--portada-font);
    font-weight: var(--font-bold);
    font-style: var(--font-style-italic);
    text-align: center;
    font-size: 1.5rem;
    line-height: 0;
    white-space: nowrap; 
    color:var(--line-color-light);
    margin-bottom:.3rem;
    margin-top: .6rem;

}
.line{
    width: 150px;
    height: 2px;
    background:white;
}
.subtitle_portadaHome{
    font-family:var(--body-font);
    font-weight: var(--font-bold);
    font-style: var(--font-style-italic);
    text-align: center;
    font-size: 2rem;
}
@media (min-width: 768px) and (max-width: 991px) {
    .title_portadaHome{
        font-size: 25rem;
    }
    .title_portada{
        font-size: 6.5rem;
    }
    .line{
        width:400px;
        margin-top:3rem;
    }
    .subtitle_portadaHome{
        font-size: 2rem;
    }
}
@media (min-width: 1025px) {
    .title_portadaHome{
        font-size: 30rem;
    }
    .title_portada{
        font-size: 7.5rem;
    }
    .line{
        width:400px;
        margin-top:3.5rem;
    }
    .subtitle_portadaHome{
        font-size: 2.5rem;
    }
}
</style>