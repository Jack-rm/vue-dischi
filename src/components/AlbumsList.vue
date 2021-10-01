<template>
  <div class="albums-container container">

    <div class="row row-cols-6" v-if="loadingStatus">  
      <div class="album-box" v-for="(album, index) in filteredAlbumsGroup" :key="index">
        <Album :albumItem="album"/>
      </div>
    </div>

    <div class="row" v-else>
      <div class="loader-wrapper">
        <Loader loadingMsg="Loading ..." />
      </div>
    </div>
  </div>
</template>

<script>
import axios from 'axios';
import Album from './Album.vue';
import Loader from './Loader.vue'

export default {
  
  name: 'AlbumsList',
  props: {
    selectedGenre : String,
  },
  components: {
    Album,
    Loader,
  },
  data: function() {
    return {
      index: 0,
      loadingStatus: false,

      albumsGroup: [],
      genres: [],
      
    }
  },
  computed: {
    filteredAlbumsGroup() {

        if (this.selectedGenre === ""){
          return this.albumsGroup;
        }
          return this.albumsGroup.filter(
            (element) => element.genre === this.selectedGenre)
    }

  },

  created: function(){
    axios
      .get('https://flynn.boolean.careers/exercises/api/array/music')
      .then((response) =>{
        this.albumsGroup = [...response.data.response]
        // console.log(this.albumsGroup);

        this.albumsGroup.forEach((element) => {
          if (!this.genres.includes(element.genre)) {
            this.genres.push(element.genre);
          }

        this.$emit("getGenres", this.genres);
        
        });
        
        setTimeout(() =>{
          this.loadingStatus = true;
        }, 2000);
    })
  },


}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

@import '../style/general.scss';
@import '../style/variables.scss';

.albums-container{
  margin-top: 60px;

}

.album-box{
  background-color: $myGrey;
  padding: 20px 20px 10px 20px;
  margin: 0px 20px;
  margin-bottom: 20px;
}

</style>
