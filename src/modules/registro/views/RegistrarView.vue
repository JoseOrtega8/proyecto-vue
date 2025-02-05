<template>
<div>
    <h2>Formulario de registro</h2>
    <Form :validation-schema="schema" @submit="onSubmit">
        <div class="form">
            <label for="Nombre">Nombre: </label>
            <Field v-model="nombre" type="text" name="nombre"id="nombre"placeholder="ingrese su nombre"/>
            <ErrorMessage name="nombre"></ErrorMessage>
        </div>
        <div class="form"> <label for="Email">Email: </label>
            <Field v-model="email" type="email" name="email" id="correo" placeholder="ingrese su email"/>
            <ErrorMessage name="email"></ErrorMessage>
        </div>
        <div class="form">
            <button type="submit">Registrar</button>
        </div>
    </Form>
</div>

</template>

<script setup>
import { ref } from 'vue';
import {Form, Field, ErrorMessage} from 'vee-validate'
import { schema } from '../schemas/validationsSchema';
import { useRegistrarStore } from '../stores/registrarStore';
const registrarStore = useRegistrarStore();
const nombre = ref('');
const email = ref('');
const onSubmit = () => {
    registrarStore.guardarRegistro(nombre.value,email.value)
    console.log("Se ha enviado correctamente")
}
</script>

<style>
.form{
    margin-bottom: 10px;
}
</style>