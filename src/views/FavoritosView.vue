<script setup>
import {useFavoritosStore} from '@/store/favoritos';
import { storeToRefs } from 'pinia';
import {RouterLink} from 'vue-router';

const useFavoritos = useFavoritosStore();

const {favoritos} = storeToRefs(useFavoritos);
const {remove} = useFavoritos;

</script>

<template>
    <h1>Favoritos</h1>
    <p v-if="favoritos.length === 0">Sin Favoritos</p>
        <ul class="list-group" v-else>
            <li class="list-group-item" v-for="poke in favoritos" :key="poke.id">
                <div>
                    {{ poke.name }}
                </div>
                <div>
                    <router-link 
                        class="btn btn-sm btn-primary me-2" 
                        :to="`/pokemons/${poke.name}`"
                    >
                        + INFO
                    </router-link>
                    <button 
                        class="btn btn-sm btn-danger" 
                        @click="remove(poke.id)"
                    >
                        Eliminar
                    </button>
                </div>
            </li>
        </ul>

</template>