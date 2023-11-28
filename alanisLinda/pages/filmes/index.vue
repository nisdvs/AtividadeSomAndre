<script setup>
    const {data: filmeFilmes } = await useFetch('http://localhost:8000/filmes')
</script>

<template>
    <div>
        <h1>
            "Filmes Page!"
        </h1>
        <div v-for="(filmReceived,index) in filmeFilmes.results"
        :key="index">
        <NuxtLink :to="`/filmes/${filmReceived.id}`">
            <img :src="filmReceived.link">
        </NuxtLink >
            <h2>
                {{ filmReceived.nome }}
            </h2>
            <h2>
                {{ filmReceived.banner }}
            </h2>
        </div>
    </div>
</template>