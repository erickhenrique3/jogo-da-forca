<template>
    <div class="formulario">
        <div class="formulario-title">{{ title }}</div>

        <input type="text" class="formulario-title" v-model="inputValue">


        <button 
        @click="OnSubmit"
        :disabled="inputValue.length === 0">{{ button }}</button>

    </div>
</template>


<script>
export default {
    name: 'formulario',
    //reutilizando componentes
    props: {
        title: String,
        button: String,
        action: Function
    },
    data() {
        return {
            inputValue: ''
        }
    },
    methods: {
        OnSubmit() {
           this.action(this.inputValue);
            this.inputValue = '';
        }
    },
}
</script>

<style>
.formulario {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    text-align: center;
    margin-top: 20px;
}

.formulario input {
    padding: 10px 5px;
    border: 0;
    border-radius: 10px;
    margin: 10px 0;
    text-align: center;
    color: var(--color-text-dark);
    font-size: 16px;

}
</style>