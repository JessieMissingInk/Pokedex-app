<template>
    <RouterLink :to="`/pokemons/${pokemon.name}`">
    <div class= "flex items-center space-x-6" w-full p-2 border-green-200 cursor-pointer rounded-md>
      <div :class="types.indexOf(pokemon.type1) == -1 ? 'default' : pokemon.type1" 
            class="w-3 h-3 rounded-full">            
    </div> 
        <span>{{pokemon.name}}</span>
        </div>
</RouterLink>
</template>

<script setup>
defineProps({
    pokemon:{
        type: Object
    }
})

const types = ["bug", "dark", "dragon", "electric", "fairy", "fighting", "fire", "flying", 
"ghost", "grass", "ground", "ice", "normal", "poison", "psychic", "rock", "steel", "water"]
</script>

<style scoped>
.bug{
    @apply bg-green-900;
}
.dark{
    @apply bg-gray-900;
}
.dragon{
    @apply bg-slate-500;
}
.electric{
    @apply bg-yellow-500;
}
.fairy{
    @apply bg-pink-900;
}
.fighting{
    @apply bg-orange-500;
}
.fire{
    @apply bg-red-500;
}
.flying{
    @apply bg-slate-500;
}
.ghost{
    @apply bg-purple-900;
}
.grass{
    @apply bg-green-500;
}
.ground{
    @apply bg-red-900;
}
.ice{
    @apply bg-blue-200;
}
.normal{
    @apply bg-purple-700;
}
.poison{
    @apply bg-purple-500;
}
.psychic{
    @apply bg-pink-300;
}
.rock{
    @apply bg-orange-900;
}
.steel{
    @apply bg-gray-500;
}
.water{
    @apply bg-blue-500;
}
.default{
    @apply bg-black;
}
</style>