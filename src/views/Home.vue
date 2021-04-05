<template>
  <div class="home">
    <div class="top-block">
      <Header />
      <SwiperBlock />
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'
import Header from '@/components/Header.vue'
import SwiperBlock from '@/components/SwiperBlock.vue'

export default {
  name: 'Home',
  components: {
    Header,
    SwiperBlock
  }
}
</script>

<style scoped>
.top-block {
  width: 100%;
  height: 774px;
  background-image: linear-gradient(to right, #f9f1e7 70%, #fcf8f3 70%);
}
</style>
