<template>
  <div id="app">
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
  font-family: 'silka';
  src: local('silka'),
    url(./fonts/silka/silka-regular-webfont.ttf) format('truetype');
}

#app {
  font-family: silka, Avenir, Helvetica, Arial, sans-serif;
  color: #012d26;
}
</style>
