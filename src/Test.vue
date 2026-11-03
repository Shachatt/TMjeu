<script setup lang="ts">
import { ref, computed } from 'vue';

const chiffre = ref<number>(0)
const array = [4,87,9,2,56,0]

function augmenter(){
    return chiffre.value += 1
}
function diminuer(){
    return chiffre.value -= 1
}

const atteintDix = computed(() => {
    if (chiffre.value === 10){
        return true
    } else {
        return false
    }
}) 

const uneListe:number[] = []
function pour(){
    for (let i = 0; i = array.length; i++) {
        uneListe.push(i)
    }
    return uneListe
}
console.log(uneListe)
</script>

<template>
    <div class="flex items-center flex-col gap-6">
        <p class="text-4xl"> Hello world ! </p>
        <div>
        </div>
        <div class="flex items-center justify-center gap-3">
        </div>
    </div>
</template>