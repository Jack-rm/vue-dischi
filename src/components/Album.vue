<template>
  <div class="single-album">
        <img class="img-fluid" :src="albumItem.poster" :alt="albumItem.title">
        <h3>{{ albumItem.title }}</h3>
        <p>{{ albumItem.author }}</p>
        <p>{{ albumItem.year }}</p>
  </div>
</template>

<script>
export default {
    name: 'Album',
    props: ['albumItem'],
}
</script>

<style lang="scss">
.single-album{
    text-align: center;

    & h3{
        color: white;
        padding-top: 10px;
        font-weight: bold;
    }
}

</style>