<template>
  <div id="app">
    <h1>Jogo da Forca</h1>

    <section v-if="tela == 'inicio'" id="inicio">
      <formulario v-if="etapa === 'palavra'"
      title="Defina a palavra"
      button="Proximo"
      :action="SetPalavra"/>
      
      <formulario v-if="etapa === 'dica'"
      

      title="Defina a dica"
      button="Iniciar jogo"
      :action="SetDica"/>
    </section>



    <section v-if="tela == 'jogo'" id="jogo">
      <jogo/>
    </section>
  </div>
</template>

<script>
import '@/css/global.css';
import formulario from './components/formulario';
import jogo from './components/jogo';

export default {
  name: 'App',
  data() {
    return {
      tela: 'inicio',
      etapa: 'palavra',
      palavra: '',
      dica: '',
      erros: 0
    }
  },
  components: {
    formulario,
    jogo,
    
  },
  methods: {
    SetPalavra(palavra) {
      this.palavra = palavra;
      this.etapa = 'dica';
    },
    SetDica(dica) {
      this.dica = dica;
      this.tela =   'jogo',
      this.etapa = 'jogo';
    }
  },
}
</script>

<style>
#app {
  width: 100%;
  height: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}
</style>
