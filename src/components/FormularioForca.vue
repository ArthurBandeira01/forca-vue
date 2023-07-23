<template>
    <div class="formulario">
        <div class="formulario-title">{{title}}</div>

        <input type="text" class="formulario-input" v-model="inputValue">

        <button
            v-on:click="onSubmit"
            :disable="inputValue.length === 0">{{button}}</button>
    </div>
</template>

<script>

export default{
    name: 'FormularioVue',
    props: {
        title: String,
        button: String,
        action: Function
    },
    data(){
        return{
            inputValue: ''
        }
    },
    methods: {
        onSubmit: function(){
            this.action(this.inputValue);
            this.inputValue = '';
        }
    }
}

</script>

<style>
    .formulario{
        display: flex;
        flex-direction: column;
        align-items: center;
        text-align: center;
        justify-content: center;
        margin-top: 1em;
    }

    .formulario-input{
        padding: .5em;
        border: 0;
        border-radius: 5px;
        margin: 10px 0;
        outline: none;
        text-align: center;
        color: var(--color-text-dark);
        font-size: 16px;
    }
</style>