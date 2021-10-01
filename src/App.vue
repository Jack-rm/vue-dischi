<template>
  <div id="app">

    <Header />
    <main>
      <Select @updatedGenre="executeSearch" :genres="genres"/>
      <AlbumsList @getGenres="storeGenres" :selectedGenre="genreNeedle" />
    </main>
  
  </div>
</template>

<script>
import AlbumsList from './components/AlbumsList.vue';
import Header from './components/Header.vue';
import Select from './components/Select.vue';

export default {
  name: 'App',
  data : function (){
    return{
      genres : [],
      genreNeedle : '',
    }
  },
  components: {
    Header,
    Select,
    AlbumsList,
  },
  methods:{
    storeGenres(genres){
      this.genres = [...genres]
    },

    executeSearch(needle){
      this.genreNeedle = needle;
    }
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

main{
  padding-top: 35px;
}

</style>
