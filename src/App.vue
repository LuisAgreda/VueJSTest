<template>
  <div id="app">
    <px-header />
    <home />
  </div>
</template>

<script>
import PxHeader from '@/components/PxHeader'
import Home from '@/views/Home'

export default {
  name: 'App',
  components: { PxHeader, Home },
}
</script>

<style>
@font-face {
  font-family: 'silka';
  src: local('silka'),
    url(/fonts/silka/silka-regular-webfont.woff2) format('woff2');
}

#app {
  font-family: silka, Avenir, Helvetica, Arial, sans-serif;
  color: #012d26;
}
</style>
