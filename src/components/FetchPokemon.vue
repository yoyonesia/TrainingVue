<script setup>
import {ref,onMounted} from 'vue'
const title =ref('Fetching Data Example')
const pokemons =ref([]);

const fetchData = async () =>{
    try{
        const response = await fetch('https://pokeapi.co/api/v2/pokemon');
        if(response.ok){
            const data = await response.json();
            
            pokemons.value = data.results;
        }else{
            console.log('err');
        }
    }catch(error){
        console.log(error);
    }
} ;
onMounted(fetchData);
</script>
<template>
    
<div>
    <h1>{{title}}</h1>
    <ul>
        <li v-for="pokemon in pokemons" :key="pokemon.name">{{pokemon.name}}</li>
    </ul>
</div>
</template>