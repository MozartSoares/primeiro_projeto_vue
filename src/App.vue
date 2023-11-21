<script setup>
import { reactive } from 'vue';

    const nome = "Mozart Soares "
    const meuObj = {
        nome: "Mozart",
        filmeFavorito: "Interestelar"
    }

    function dizOla(nome) {
        return `${nome} diz oi`
    }

    const enderecoImagemBatman = "data:image/jpeg;base64,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"
    const imagemSuperman = "https://upload.wikimedia.org/wikipedia/pt/b/be/Super-Homem.jpg"
    const botaoEstaDesabilitado = true

    const gostaDoBatman = false
    const gostaDoSuperman = false

    const estaAutorizado = true

    // let contador = 0 
    const estado =  reactive({
        contador: 0,
        email: '',
        saldo: 5000,
        transferindo: 0,
        nomes: ["mozart", "gabriela", "julia", 'paulo'],
        nomeAInserir: '',
    })

    function incrementar() {
        estado.contador++
    }

    function decrementar() {
        estado.contador--
    }

    function alteraEmail(evento) {
        estado.email = evento.target.value
    }

    function mostraSaldoFuturo() {
        const {saldo,transferindo} = estado //desestruturação
        return saldo - transferindo
    }
    
    function tornaValido() {
        const {saldo,transferindo} = estado
        return saldo >= transferindo
    }

    function cadastraNome() {
        if(estado.nomeAInserir.length >= 3) {
            estado.nomes.push(estado.nomeAInserir)
        } else {
            alert("O nome deve ter no mínimo 3 caracteres")
        }
    
    }
</script>

<template>
    <h1>{{ dizOla("Rogerio") }}</h1>
    <img v-if="gostaDoBatman" :src="enderecoImagemBatman" alt="">
    <img v-else-if="gostaDoSuperman" :src="imagemSuperman" alt="">
    <h2 v-else>Não curte heróis da DC</h2>

    <h1 v-if="estaAutorizado">Bem vindo</h1>
    <h1 v-else>Não está autorizado</h1>

    <button :disabled="botaoEstaDesabilitado ">enviar mensagem</button>

    <br>
    <hr>

    {{ estado.contador }}


    <button @click="incrementar" type="button">+</button>
    <button @click="decrementar" type="button">-</button>

    <br>
    <hr>

    {{ estado.email }}
    <br>

    <input type="email" @keyup="alteraEmail">

    <br>
    <hr>

    Saldo: {{ estado.saldo }} <br>
    Transferindo: {{ estado.transferindo }} <br>
    Saldo após a transferência: {{ mostraSaldoFuturo() }} <br>
    <input :class="{ invalido:!tornaValido()  }" @keyup="evento => estado.transferindo = evento.target.value" type="number" placeholder="Quantia para transferir">
    <button v-if="tornaValido()">Transferir</button>
    <span v-else>Valor maior que o saldo</span>

    <br>
    <hr>

    <ul>
        <li v-for="nome in estado.nomes">
            {{ nome }}
        </li>
    </ul>
    <input @keyup="evento => estado.nomeAInserir = evento.target.value" type="text" placeholder="Digite um novo nome">
    <button @click="cadastraNome()" type="button">Cadastrar nome</button>

    <h3 v-for="nome in estado.nomes">{{ nome }}</h3>
</template>

<style scoped>

.invalido {
    outline-color: red;
    border-color: red;
}

</style>
