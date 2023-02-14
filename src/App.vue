<template>
  <header>
    <nav>
      <RouterLink to="/">Articles</RouterLink><p>/</p>
      <RouterLink to="/about">About</RouterLink>
    </nav>
  </header>

  <RouterView />
</template>


<script setup>
import { RouterLink, RouterView } from 'vue-router'
</script>

    
<style scoped>
a {
  text-decoration: none;
  font-family: 'Inter', sans-serif;
  font-weight: 700;
  color: black;
}

a:hover {
  color: gray;
}

p {
    margin: 0;
    padding: 0 1em;
}

</style>
