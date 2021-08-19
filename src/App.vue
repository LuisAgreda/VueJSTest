<template>
  <div id="app" class="m-0">
    <px-header />
  </div>
</template>

<script>
import PxHeader from '@/components/PxHeader'

export default {
  name: 'App',
  components: { PxHeader },
}
</script>

<style>
@font-face {
  font-family: 'silkaregular';
  src: local('Merienda'),
    url(./fonts/silka/silka-regular-webfont.ttf) format('truetype');
}

#app {
  font-family: silkaregular, Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #012d26;
  margin-top: 60px;
}
</style>
