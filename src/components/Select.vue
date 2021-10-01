<template>
  <div class="container">
    <div class="row">
      <div class="col-12 d-flex justify-content-center">

        <select class="form-select" v-model="genreNeedle" @change="$emit('updatedGenre', genreNeedle)">
          <option value="">Select music genre</option>
          <option v-for="(genre,index) in genres" :key="index" :value="genre">
            {{ genre }}
          </option>
        </select>

      </div>
    </div>
  </div>
</template>

<script>
export default {
    name : 'Select',
    props : { genres : Array },
    data() {
      return{
        genreNeedle : '',
      }
    }
}
</script>

<style lang="scss" scoped>

.form-select{
  width: 400px;
}

</style>