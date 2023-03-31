<template>
    <div class="box">
        <div class="columns">
            <div class="column is-8"  role="form" aria-label="Formulário para criação de uma nova tarefa">
                <input type="text" 
                    class="input" 
                    placeholder="Qual tarefa você deseja iniciar ?"
                    v-model="descricao"
                />
            </div>            
            <div class="column">
                <TemporizadorItem @aoTemporizadorFinalizado="finalizarTarefa"/>
            </div>
        </div>
    </div>
</template>

<script lang="ts">
    import { defineComponent } from 'vue';
    import TemporizadorItem from '../components/Temporizador.vue'

    export default defineComponent({
        name: "FomularioItem",
        components:{
            TemporizadorItem
        },
        data (){
            return {
                descricao : ''
            }
        },
        methods :{
            finalizarTarefa (tempoDecorrido: number) : void {
                console.log('tempo tarfa :' + tempoDecorrido)
                console.log('descricao tarfa :' + this.descricao)
                this.descricao = ''
            }
        }
       
    })

</script>