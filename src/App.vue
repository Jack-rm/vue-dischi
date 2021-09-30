<template>
  <div id="app">

    <Header />
    <main>
      <AlbumsList />
    </main>
  
  </div>
</template>

<script>
import AlbumsList from './components/AlbumsList.vue';
import Header from './components/Header.vue';


export default {
  name: 'App',
  components: {
    AlbumsList,
    Header,
  }
}
</script>

<style lang="scss">

@import 'style/general.scss';
@import 'style/variables.scss';

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

body{
  background-color: $mainBgColor;
}
</style>
