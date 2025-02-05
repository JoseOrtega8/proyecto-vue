<template>
<div class="header">
{{ mensajeRecibido }}
<Weather></Weather>
</div>
</template>

<script setup>
import Weather from './Weather.vue'
import { defineProps,ref,watch } from 'vue';
const props = defineProps(['mensaje']);
const mensajeRecibido = ref(props.mensaje);
watch(()=>props.mensaje,(newValue)=>{
    mensajeRecibido.value = newValue
})
</script>

<style>
.header{
    display: flex;
    justify-content: center;
    align-items: center;
    padding: 10px 20px;
    top: 0;
    right: 0;
    left: 0;
    background-color:rgb(76, 97, 92);
}
.h3{
    margin: 0;
}

</style>