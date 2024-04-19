<template>
    <div class="jogo">
        <forca />
    </div>
</template>


<script>
import forca from './forca'
export default {
    name: 'jogo',
    //reutilizando componentes
    props: {
        
    },
    data() {
        return {
            
        }
    },
    methods: {
       
    },
    componentes: {
      forca
    }
}
</script>

<style>
 .jogo{
    width: 100%;
    display: flex;
    flex-direction: column;
    align-items: center;
    text-align:  center;
 }
</style>