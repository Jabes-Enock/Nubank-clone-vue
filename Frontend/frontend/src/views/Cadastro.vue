<template>
    <div class="container">
        <CadastroCardDone />
        <AlertCard @changePopupState="changePopupState" v-if="$openPopupCadastro" statusMessage="Tudo Certo!!!!" explicationMessage="Usuário criado com sucesso"> 
            <div class="icon">
                <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="none" stroke="gray" >
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="0.5" d="M10 6H5a2 2 0 00-2 2v9a2 2 0 002 2h14a2 2 0 002-2V8a2 2 0 00-2-2h-5m-4 0V5a2 2 0 114 0v1m-4 0a2 2 0 104 0m-5 8a2 2 0 100-4 2 2 0 000 4zm0 0c1.306 0 2.417.835 2.83 2M9 14a3.001 3.001 0 00-2.83 2M15 11h3m-3 4h2" />
                </svg>
            </div>
        </AlertCard>
    </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import {CadastroCardDone } from '../components/template'
import { AlertCard } from '../components/molecules'
import store from '../store'

export default defineComponent({
    data(){
        return { store }
    },
   components: {
       CadastroCardDone,
       AlertCard
   },
   methods: {
       changePopupState() {
           store.commit('CLOSE_POPUP_CADASTRO')
       }
       
   },
   computed: {
       $openPopupCadastro(){
           return store.getters.$openPopupCadastro
       }
   }
})
</script>

<style scoped>

</style>