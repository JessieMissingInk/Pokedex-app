<template>
    <div class="flex flex-col p-10 space-y-30">
       <h1 class="text-6xl text-gray-900 font-semibold">
        {{pokemonDetails?.name}}</h1>
        <img :src="image" :alt="pokemonDetails?.name" class="w-full h-full rounded-lg" />
       </div>
       <div class="p-5">
            <div class="flex items-center space-x-11">
                <span>Primary Type</span> 
                <span>{{ pokemonDetails?.type1 }}</span>
            </div>

            <div class="flex items-center space-x-11" v-if="pokemonDetails?.type2">
                <span>Secondary Type</span> 
                <span>{{ pokemonDetails?.type2 }}</span>
            </div>
        </div>

        <div class="p-5">
            <div class="flex items-center space-x-11">
                <span>Height</span> 
                <span>{{ pokemonDetails?.stats?.height_m }}m</span>
            </div>

            <div class="flex items-center space-x-11">
                <span>Weight</span> 
                <span>{{ pokemonDetails?.stats?.weight_kg }}kg</span>
            </div>
        </div>
</template>

<script setup>
import { useRoute } from "vue-router";
import pokemons from "@/assets/sampledataset.json";
import { onMounted, ref } from "vue";

import axios from "axios";

const route= useRoute();

const pokemonDetails= ref({});

const image = ref("")

onMounted(() => {
  pokemonDetails.value = pokemons.filter(
    (item) => item.name.toLowerCase() == route.params.name.toLowerCase())[0];

axios.get (`https://pokeapi.co/api/v2/pokemon/${pokemonDetails.value.name.toLowerCase()}`).then(data =>{
image.value = data.data.sprites.other['official-artwork'].front_default
})
});
</script>
