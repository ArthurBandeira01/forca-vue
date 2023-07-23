<template>
    <div class="teclado">
        <button class="teclado-botao"
            v-for="(letra, key) in 'abcdefghijklmnopqrstuvxywzãáéêíóõú'" 
            :key="key"
            :disable="verificarLetra(letra)"
            v-on:click="jogar(letra)">
            {{ letra }}
        </button>
    </div>
</template>

<script>


export default{
    name: 'TecladoForca',
    props: {
        letras: Array,
        verificarLetra: Function,
        jogar: Function
    },
    components: {
       
    }
}

</script>

<style>
   .teclado{
        display: flex;
        flex-wrap: wrap;
        justify-content: center;
        max-width: 80%;
        margin-top: 2em;
   }

   .teclado-botao{
        margin: 10px;
        text-transform: uppercase;
   }
</style>