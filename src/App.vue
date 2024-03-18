<script setup>
import { ref, reactive } from 'vue';


const usuario = reactive({
nome: "",
email: '',
idade: '',
})

function verificacao(usuario) {
    if (usuario.nome.length >= 3 && usuario.nome.length <= 20 && usuario.idade.value >= 18 && usuario.idade.value <= 60) {
        usuario.nome = "";
        usuario.email = '';
        usuario.idade = 0;

    }
}
</script>

<template>
    <form @submit.prevent="verificacao(usuario)">
        <input type="text" v-model.trim.lazy="nome" placeholder="Digite seu nome" required />
        <p>Nome digitado é: {{ nome }} </p>
        <input type="email" v-model.trim.lazy="email" placeholder="Digite seu email" require>
        <p>O email digitado é: {{ email }}</p>
        <input type="number" v-model.trim.number="idade" placeholder="Digite sua Idade " required>
        <p>A idade digitada é: {{ idade }}</p>
        <button @click="verificacao(usuario)" >enviar</button>
    </form>
</template>

<style></style>