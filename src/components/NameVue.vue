<script>
export default{
    name:'NameVue',
    data(){
        return{
            title:'Coty',
            subtitle:'Mis 15 años'
        }        
    }
}
</script>
<template>
    <div class="container_name" data-aos="zoom-in-up">
        <h1 class="title_nombre">{{ title }}</h1>
        <h4 class="sutitle_nombre">{{ subtitle }}</h4>
    </div>
</template>
<style>
.container_name{
    width:100%;
    height: 150px;
    display: flex;
    flex-direction: column;
    justify-content: flex-start;
    align-items: center;
}
.title_nombre,
.sutitle_nombre{
    font-family: var(--portada-font);
}

.title_nombre{
    background: linear-gradient(90deg, #E18E92 0%, #A6706A 12%, #F6DEDF 20%, #E9ADB0 35%, #F2D0D2 52%, #A6706A 66%, #A6706A 75%, #E6A1A4 100%);
    background-clip: text;
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    font-size: 100px;
    line-height: 100%;    
}
.sutitle_nombre{
    color:var(--title-color);
    font-size: var(--h2-font-size);
    line-height: 80%;
}
@media (min-width: 768px) and (max-width: 991px) {
    .container_name{
        width:100%;
        height: 350px;
        margin-top:400px;
        position: relative;
        z-index: 3;
    }
    .title_nombre{
        font-size: 250px;
    }
    .sutitle_nombre{
        font-size: 70px;
    }
}
@media (min-width: 1025px) {
    .container_name{
        width:100%;
        height: 550px;
        margin-top:30%;
        position: relative;
        z-index: 3;
    }
    .title_nombre{
        font-size: 450px;
    }
    .sutitle_nombre{
        font-size: 100px;
    }

}
</style>