<template>
  <SpotifyApp/>
</template>

<script>
import SpotifyApp from './components/SpotifyApp.vue';

export default {
  name: 'App',
  components: {
    SpotifyApp,
  },
};
</script>

<style lang="scss">
#app {
  font-family: 'Lato', sans-serif;
  font-style: normal;
  font-weight: 400;
  font-size: 12px;
}
</style>
