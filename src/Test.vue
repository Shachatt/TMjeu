<script setup lang="ts">
import { ref, computed } from 'vue';

const tableau:number[] = []
function remplir(){
    for (let i = -5; i <= 5; i++){
        tableau.push(i)
    }
    return tableau
}
remplir()
console.log(tableau)

const somme = ref<number>(0)
function ajouterValeur(chiffre:number){
    return somme.value += chiffre
}

function valider(){
    if (somme.value >= 25 || somme.value <=-25){
        return true
    } else {
        return false
    }
}

</script>

<template>
    <div class="flex items-center flex-col gap-6">
        <p class="text-6xl font-semibold"> Test ! </p>
        <div v-if="valider()">Tu as atteint 25</div>
        <div>{{ somme }}</div>
        <div v-if="!valider()" class="flex items-center justify-center gap-3 ">
            <div v-for="chiffre in tableau" @click="ajouterValeur(chiffre)" class="bg-blue-300 rounded-xl px-2 py-1 hover:bg-blue-400">{{ chiffre }}</div>
        </div>
    </div>
</template>