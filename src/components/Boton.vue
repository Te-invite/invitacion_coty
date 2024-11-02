<script>
export default{
    name:'Boton',
    props: {
    label: {
      type: String,
      required: false 
    },
    customClass: {
      type: String,
      default: 'btn-mayor'
    }
  }

}
</script>
<template>
   <button type="button" :class="['btn', customClass, 'btn-lg']">
      {{ label }}
    </button>
</template>
<style>
.btn-mayor{
    width: 260px;
    background: transparent;
    color:var(--title-color);
    border-radius: 10px;
    border: 1px solid var(--color_btn);
    padding: .75rem 1rem;
    font-weight: var(--font-regular);
    font-style: var(--font-style-normal);
}
.btn-mayor:hover{
  color:white;
  background:  linear-gradient(45deg, #b76e79, #d4b1a0);
}
</style>