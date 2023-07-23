<template>
    <div class="palavra-forca">
        <div class="palavra-letras">
            <div class="palavra-letra" v-for="(letra, key) in palavra" :key="key">
                {{ (verificarLetra(letra) || etapa === 'enforcado') ? letra : '' }}
            </div>
        </div>
        <div class="palavra-dica">
            {{ dica }}
        </div>    
    </div>
</template>

<script>


export default{
    name: 'PalavraForca',
    props: {
        palavra: String,
        dica: String,
        verificarLetra: Function,
        etapa: String
    },
    components: {
        
    }
}

</script>

<style>
    .palavra-forca{
        text-transform: uppercase;
        display: flex;
        flex-direction: column;
        align-items: center;
        text-align: center;
    }
    .palavra-letras{
        display: flex;
        margin-bottom: 20px;
    }
    .palavra-letra{
        display: flex;
        width: 30px;
        margin: 0 5px;
        justify-content: center;
        align-items: center;
        height: 40px;
        border-bottom: 1px solid var(--color-text-light);
    }
</style>