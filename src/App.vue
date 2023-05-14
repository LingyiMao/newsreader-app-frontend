<template>
  <header>
    <img src="./image/jon-tyson-XmMsdtiGSfo-unsplash.jpg" alt="">
    <nav>
      <RouterLink to="/">Search the News</RouterLink><p>/</p>
      <RouterLink class="about-title"  to="/about">About</RouterLink>
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

.about-title {
font-size: 14px;
}

nav {
  padding-top: 2rem;
 justify-content: center;
}

header {
  text-align: center;
}

img {
  width: 120px;
  height: 120px;
  box-shadow: 5px 5px 10px 5px gray;
}
</style>
