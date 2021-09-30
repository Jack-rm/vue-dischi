<template>
  <div class="albums-container container">
    
    <div class="row row-cols-6" v-if="booleano">  
      <div v-for="(album, index) in albumsGroup" :key="index" class="album-box">
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
  props: {},
  components: {
    Album,
    Loader,
  },

  data: function() {
    return {
      albumsGroup: [],
      index: 0,
      booleano: false,
      
    }
  },
  
  created: function(){
    axios.get('https://flynn.boolean.careers/exercises/api/array/music')
    .then((response) =>{
      this.albumsGroup = response.data.response;
      // console.log(this.albumsGroup);

      setTimeout(() =>{
        this.booleano = true;
      }, 2000);
    })
  }

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

@import '../style/general.scss';
@import '../style/variables.scss';

.albums-container{
  margin-top: 80px;

}

.album-box{
  background-color: $myGrey;
  padding: 20px 20px 10px 20px;
  margin-right: 40px;
  margin-bottom: 20px;
}

</style>
