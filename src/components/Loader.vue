<template>
  <div class="loader-item d-flex justify-content-center ">
        <div class="wave-load">
          <div></div>
          <div></div>
        </div>
        <div class="wave-load">
          <div></div>
          <div></div>
        </div>
        <div class="wave-load">
          <div></div>
          <div></div>
        </div>
  </div>
</template>

<script>
export default {
    name: 'Loader',
    props: ['loadingMsg'],
}
</script>

<style lang="scss" scoped>

.loader-item{
    margin-top: 250px;
}

.wave-load {
  display: inline-block;
  position: relative;
  width: 80px;
  height: 80px;
}
.wave-load div {
  position: absolute;
  border: 4px solid #fff;
  opacity: 1;
  border-radius: 50%;
  animation: wave-load 1s cubic-bezier(0, 0.2, 0.8, 1) infinite;
}
.wave-load div:nth-child(2) {
  animation-delay: -0.5s;
}
@keyframes wave-load {
  0% {
    top: 36px;
    left: 36px;
    width: 0;
    height: 0;
    opacity: 1;
  }
  100% {
    top: 0px;
    left: 0px;
    width: 72px;
    height: 72px;
    opacity: 0;
  }
}

</style>