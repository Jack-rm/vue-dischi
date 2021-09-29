<template>
  <div id="app">
    <header>
      <div class="container-fluid">
        <div class="row">
          <div class="col-12">
            <p>header</p>
          </div>
        </div>
      </div>
    </header>

    <main>
      <AlbumsList />
    </main>
  </div>
</template>

<script>
import AlbumsList from './components/AlbumsList.vue'


export default {
  name: 'App',
  components: {
    AlbumsList,
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

header{
  margin: 0;
  text-align: left;
  background-color: $myGrey;
  color: white
}

body{
  background-color: $mainBgColor;
}
</style>
