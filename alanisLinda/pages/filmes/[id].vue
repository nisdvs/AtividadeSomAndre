<script setup>
    const route = useRoute();
    console.log("route", route); 

    const {data: filmes} = await useFetch(`http://localhost:8000/filmes/${route.params.id}`)
    const {data: categoria} = await useFetch(`http://localhost:8000/categoria/`)
        query: {'id: route.params.id'}



<template>
    <div>
        <h1>
           #{{ filmes.id }}: {{ filmes.nome }} 
        </h1>
        <br></br>
        <p>
            {{ filmes.descricao }}
        </p>
        <br></br>
        <p>
            {{ filmes.foto}}
        </p>
        <br></br>
        <p>
            {{ filmes.logo}}
        </p>
    
        <select>
                <option v-for="categoria in categoria.results"
                    :key="categoria.id" :value="categoria.nome">
                    {{categoria.nome}}
                </option>
        </select>
</template>