<script setup>
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>

  <nav class="navbar bg-dark navbar-dark">
    <div class="container">
      <router-link class="navbar-brand" to="/">
        <img 
          src="@/assets/logo.svg" 
          alt="Logo" 
          width="30" 
          height="24" 
          class="d-inline-block align-text-top"
        >
        PokeAPI
      </router-link>
      <div>
        <router-link 
          active-class="active"
          class="btn btn-outline-secondary me-2" 
          to="/"
          >Home</router-link
        >
        <router-link
          active-class="active" 
          class="btn btn-outline-secondary me-2" 
          to="/pokemons"
          >Pokemons</router-link
        >
        <router-link
          active-class="active" 
          class="btn btn-outline-secondary" 
          to="/favoritos"
          >Favoritos</router-link
        >
      </div>
    </div>
  </nav>

  <div class="container text-center">
    <RouterView />
  </div>

</template>

