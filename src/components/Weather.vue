<template>
<h3> La temperatura actual es: {{ weatherStore.temperatura }}</h3>

</template>

<script setup>
import { useWeather } from '@/composables/useWeather';
import { onMounted } from 'vue';
import { useWeatherStore } from '@/stores/weatherStore';
onMounted(()=>{
    useWeather();
})
const weatherStore = useWeatherStore();
</script>


<style scoped >

</style>