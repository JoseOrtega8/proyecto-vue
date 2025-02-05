<template>
    <h3>Popiedades Computadas</h3>
    <input type="text" v-model="valor">
    {{ valorCalculado}}
    
    <resultadoSection v-if="mostrarElemento" :resultado="valorCalculado"></resultadoSection>
<div v-else-if="isNaN(valor)">Debe ser un numero</div>
<div v-else>Aqui no se muestra nada</div>
</template>


<script setup>
import { ref,computed } from 'vue';
import resultadoSection from '../components/resultadoSection.vue';
const valor = ref('');
const valorCalculado = computed(()=>{
    return valor.value *3
});

const mostrarElemento = computed(()=>{
    return valor.value >10;
})

</script>

<style scoped>

</style>