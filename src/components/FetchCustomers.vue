<script setup>
import {ref,onMounted} from 'vue'
const title =ref('Fetching Data Example')
const customers =ref([]);

const fetchData = async () =>{
    try{
        const response = await fetch('http://localhost:8090/BCAAbacas/abacas/area',
        {
            method: "GET",
            mode:"cors"
        });
        if(response.ok){
            const data = await response.json();
            
            customers.value = data;
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
        <li v-for="customer in customers" :key="customer.name">
            <ul>{{customer.name}}</ul>
        </li>
    </ul>
</div>
</template>