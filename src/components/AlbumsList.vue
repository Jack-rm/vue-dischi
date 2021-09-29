<template>
  <div class="albums-container container">
    <div class="row row-cols-6">
      <div v-for="(album, index) in albumsGroup" :key="index" class="album-box">
        <Album :albumItem="album"/>
      </div>
    </div>
  </div>
</template>

<script>
import axios from 'axios';
import Album from './Album.vue'

export default {
  name: 'AlbumsList',
  props: {
    msg: String
  },
  components: {
    Album,
  },
  data: function() {
    return {
      albumsGroup: [],
      index: 0,
    }
  },
  created: function(){
    axios.get('https://flynn.boolean.careers/exercises/api/array/music')
    .then((response) =>{
      this.albumsGroup = response.data.response;
      console.log(this.albumsGroup);
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
