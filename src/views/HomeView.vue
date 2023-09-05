<script setup>

import { onMounted, reactive, ref } from 'vue';
import ListPokemons from '../components/ListPokemons.vue';

let pokemons = reactive(ref());

onMounted(() => {
    fetch('https://pokeapi.co/api/v2/pokemon/?limit=20&offset=20')
    .then(response => response.json())
    .then(response => {
        pokemons.value = response.results;
        console.log(response);
    })
})

</script>

<template>
    <main>
        <div class="container">
            <div class="row mt-4">
                <div class="col-sm-12 col-md-6">
                    <div class="card" style="width: 35rem;">
                        <img class="card-img-top" src="https://th.bing.com/th/id/OIP.pAolW9twtCLkbdPSMbBGBgHaFj?w=212&h=180&c=7&r=0&o=5&pid=1.7" alt="Imagem Pikachu Card">
                        <div class="card-body">
                            <h5 class="card-title">Pokemon Card</h5>
                            <p class="card-text">Sobre o pokemon</p>
                            <a href="#" class="btn btn-info">Alterar</a>
                        </div>
                    </div>
                </div>
                <div class="col-sm-12 col-md-6">
                    <div class="card">
                        <div class="card-body row">
                            <ListPokemons
                            v-for="pokemon in pokemons"
                            :key="pokemon.name"
                            :name="pokemon.name"
                            :url ="pokemon.url"
                            />
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </main>
</template>

