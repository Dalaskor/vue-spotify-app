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
html, body {
    scrollbar-color: rgba(52, 52, 52, 0.6) rgba(52, 52, 52, 0.6);
    scrollbar-width: thin;
}
/* полоса прокрутки (скроллбар) */
::-webkit-scrollbar {
    width: 5px; /* ширина для вертикального скролла */
    height: 5px;
    background-color: rgba(52, 52, 52, 0.6);
}

/* ползунок скроллбара */
::-webkit-scrollbar-thumb {
    background-color: rgba(52, 52, 52, 0.6);
    border-radius: 9em;
    box-shadow: inset 1px 1px 10px #f3faf7;
}

::-webkit-scrollbar-thumb:hover {
    background-color: #253861;
}

/* Стрелки */

::-webkit-scrollbar-button:vertical:start:decrement {
    background: linear-gradient(120deg, #02141a 40%, rgba(0, 0, 0, 0) 41%),
        linear-gradient(240deg, #02141a 40%, rgba(0, 0, 0, 0) 41%),
        linear-gradient(0deg, #02141a 30%, rgba(0, 0, 0, 0) 31%);
    background-color: #f6f8f4;
}

::-webkit-scrollbar-button:vertical:end:increment {
    background:
        linear-gradient(300deg, #02141a 40%, rgba(0, 0, 0, 0) 41%),
        linear-gradient(60deg, #02141a 40%, rgba(0, 0, 0, 0) 41%),
        linear-gradient(180deg, #02141a 30%, rgba(0, 0, 0, 0) 31%);
    background-color: #f6f8f4;
}

::-webkit-scrollbar-button:horizontal:start:decrement {
    background:
        linear-gradient(30deg, #02141a 40%, rgba(0, 0, 0, 0) 41%),
        linear-gradient(150deg, #02141a 40%, rgba(0, 0, 0, 0) 41%),
        linear-gradient(270deg, #02141a 30%, rgba(0, 0, 0, 0) 31%);
    background-color: #f6f8f4;
}

::-webkit-scrollbar-button:horizontal:end:increment {
    background:
        linear-gradient(210deg, #02141a 40%, rgba(0, 0, 0, 0) 41%),
        linear-gradient(330deg, #02141a 40%, rgba(0, 0, 0, 0) 41%),
        linear-gradient(90deg, #02141a 30%, rgba(0, 0, 0, 0) 31%);
    background-color: #f6f8f4;
}
body{
  background: #121212;
}
#app {
  font-family: 'Lato', sans-serif;
  font-style: normal;
  font-weight: 400;
  font-size: 12px;
  color: #ffffff;
}
</style>
