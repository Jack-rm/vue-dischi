<template>
  <div class="single-album">
        <img class="img-fluid" :src="albumItem.poster" :alt="albumItem.title">
        <h3>{{ albumItem.title }}</h3>
        <h5>{{ albumItem.author }}</h5>
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
@import '../style/general.scss';
@import '../style/variables.scss';

.single-album{
    text-align: center;

    & h3{
        color: white;
        padding-top: 20px;
        padding-bottom: 20px;
        font-weight: bold;
        text-transform: uppercase;
    }

    & h5,p{
        color: $myLighterGrey;
        margin: 0;
    }

}

</style>