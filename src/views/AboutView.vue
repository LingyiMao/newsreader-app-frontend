<template>
  <div>
    <div class="image-box">
      <img src="../image/filip-mishevski-c5QdMcuFlgY-unsplash.jpg" alt="">
      <img src="../image/roman-kraft-_Zua2hyvTBk-unsplash.jpg" alt="">
    </div>
    <p>This is a NewsReader App that allows people to search the news all over the world. Enjoy!!</p>
  </div>
</template>


<script>
export default {

}
</script>


<style scoped>
div {
  width: 80%;
  margin: auto;
  text-align: center;
}

.image-box {
  display: flex;
  justify-content: space-between;
}

img {
  width: 400px;
  height: 300px;
  border-radius: 20px;
}

p {
  font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
  font-size: 25px;
}
</style>
