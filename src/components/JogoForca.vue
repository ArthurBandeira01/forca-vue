<template>
    <div class="jogo">
        
        <ForcaImage
            :erros="erros"
        />

        <PalavraForca 
            :palavra="palavra"
            :dica="dica"
            :verificarLetra="verificarLetra"
            :etapa="etapa"
        />

        <TecladoForca
            v-if="etapa === 'jogo'"
            :letras="letras"
            :verificarLetra="verificarLetra"
            :jogar="jogar"
        />

        <FinalForca
            v-if="etapa != 'jogo'"
            :etapa="etapa"
            :texto="etapa === 'ganhador' ? 'Parabéns :)' : 'Você perdeu :('"
            :jogarNovamente="jogarNovamente"
        />

    </div>
</template>

<script>

import ForcaImage from './ForcaImage';
import PalavraForca from './PalavraForca';
import TecladoForca from './TecladoForca';
import FinalForca from './FinalForca';

export default{
    name: 'JogoForca',
    props: {
        erros: Number,
        palavra: String,
        dica: String,
        verificarLetra: Function,
        etapa: String,
        letras: Array,
        jogar: Function,
        jogarNovamente: Function
    },
    components: {
        ForcaImage,
        PalavraForca,
        TecladoForca,
        FinalForca
    }
}

</script>

<style>
    .jogo{
        width: 100%;
        display: flex;
        flex-direction: column;
        align-items: center;
        text-align: center;
    }
</style>