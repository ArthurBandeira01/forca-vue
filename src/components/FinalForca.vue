<template>
    <div class="final">
        <div :class="`final-texto ${etapa}`">
            {{ texto }}
        </div>

        <button
            v-on:click="jogarNovamente"
            class="final-botao">Jogar novamente</button>
    </div>
</template>

<script>


export default{
    name: 'FinalForca',
    props: {
        etapa: String,
        texto: String,
        jogarNovamente: Function
    },
    components: {
       
    }
}

</script>

<style>
   .final-texto{
    margin: 20px 0px;
    font-size: 24px;
    font-weight: bold;
   }

   .final-texto.enforcado{
    color: var(--color-text-error);
   }

   .final-texto.ganhador{
    color: var(--color-text-success);
   }
</style>