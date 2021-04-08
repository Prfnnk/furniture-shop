<template>
  <div class="home">
    <div class="top-block">
      <Header />
      <SwiperBlock />
    </div>
    <ProductsBlock />
  </div>
</template>

<script>
// @ is an alias to /src
import Header from '@/components/Header.vue'
import SwiperBlock from '@/components/SwiperBlock.vue'
import ProductsBlock from '@/components/ProductsBlock.vue'

export default {
  name: 'Home',
  components: {
    Header,
    SwiperBlock,
    ProductsBlock
  }
}
</script>

<style scoped>
.top-block {
  width: 100%;
  background-image: linear-gradient(to right, #f9f1e7 70%, #fcf8f3 70%);
}
</style>
