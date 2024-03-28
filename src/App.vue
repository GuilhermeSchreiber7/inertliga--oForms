<script setup>
import { ref } from 'vue';



 const nome = ref('');
 const email = ref('');
 const idade =  ref(0) ;
const msg = ref(false);

function verificacao() {
    if (nome.value.length >=3
        && nome.value.length <= 20
        && idade.value >= 18
        && idade.value <= 60
        && email.value != '') {
        msg.value = true
    }
}
</script>

<template>
    <form @submit.prevent="verificacao">
    <div>
        <label for="inputName">Nome</label>
        <input type="text" v-model.trim.lazy="nome" placeholder="Digite seu nome" id="inputName" required />
        <p>Nome digitado é: {{ nome }} </p>
    </div>
    <div>
        <label for="inputEmail">Email</label>
        <input id="inputEmail" type="email" v-model.trim.lazy="email" placeholder="Digite seu email" require>
        <p>O email digitado é: {{ email }}</p>
    </div>
    <div>
        <label for="inputAge">Idade</label>
        <input id="inputAge" type="number" v-model.trim.number="idade" placeholder="Digite sua Idade " required>
        <p>A idade digitada é: {{ idade }}</p>
    </div>
        <div>
        <button type="submit">enviar</button>
        </div>
    </form>
     <div v-show="msg">
    <p>confirmação registro</p>
    <div>
        <p>Nome: {{ nome }}</p>
        <p>Idade: {{ idade }}</p>
        <p>Email: {{ email }}</p>
    </div>
    </div>

</template>

<style></style>