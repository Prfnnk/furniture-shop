<template>
  <div class="wrappper">
    <swiper ref="mySwiper" :options="swiperOptions">
      <swiper-slide
        ><img src="../assets/images/swiper-pic-1.png" alt=""
      /></swiper-slide>
      <swiper-slide
        ><img src="../assets/images/swiper-pic-2.png" alt=""
      /></swiper-slide>
      <swiper-slide
        ><img src="../assets/images/swiper-pic-3.png" alt=""
      /></swiper-slide>
      <div class="swiper-pagination" slot="pagination"></div>
      <div class="swiper-button-prev" slot="button-prev"></div>
      <div class="swiper-button-next" slot="button-next"></div>
    </swiper>
  </div>
</template>

<script>
import { Swiper, SwiperSlide, directive } from 'vue-awesome-swiper'
import { Swiper as SwiperClass, Pagination, Navigation } from 'swiper/core'
import 'swiper/swiper-bundle.css'

SwiperClass.use([Pagination, Navigation])

export default {
  name: 'carousel',
  data() {
    return {
      swiperOptions: {
        pagination: {
          el: '.swiper-pagination',
          clickable: true,
          type: 'bullets'
        },
        navigation: {
          nextEl: '.swiper-button-next',
          prevEl: '.swiper-button-prev',
          clickable: true
        },
        loop: true,
        slidesPerView: 'auto',
        spaceBetween: 32,
        centeredSlides: true
        // Some Swiper option/callback...
      }
    }
  },
  computed: {
    swiper() {
      return this.$refs.mySwiper.$swiper
    }
  },
  mounted() {
    console.log('Current Swiper instance object', this.swiper)
    // this.swiper.slideTo(3, 32, 1000, false)
  },
  components: {
    Swiper,
    SwiperSlide
  },
  directives: {
    swiper: directive
  }
}
</script>

<style lang="scss">
.wrapper {
  width: 100%;
  height: 623px;
}
.swiper-container {
  padding-top: 70px;
}
.swiper-slide {
  width: 934px;
  height: 553px;
}
// pagination bullets
.swiper-container-horizontal > .swiper-pagination-bullets {
  top: 0;
  left: calc(50% - 60px);
  width: 120px;
}
.swiper-pagination {
  top: 0;
  left: calc(50% - 60px);
  width: 120px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  height: 27px;
}
.swiper-pagination-bullet {
  width: 27px;
  height: 27px;
  display: flex;
  justify-content: center;
  align-items: center;
  background: transparent;
  opacity: 1;
  border: 1px solid transparent;

  &:after {
    content: '';
    width: 11px;
    height: 11px;
    background: #d8d8d8;
    border-radius: 50%;
    display: block;
  }
}
.swiper-pagination-bullet-active {
  border: 1px solid #e89f71;

  &:after {
    background: #e89f71;
  }
}
// navigation arrows
.swiper-button-prev,
.swiper-button-next {
  top: 25px;
  border-radius: 50%;
  width: 48px;
  height: 48px;
  background: #e89f71;
  color: white;
  font-size: 14px;

  &:after {
    font-size: 14px;
  }
}
.swiper-button-next {
  right: 100px;
}
.swiper-button-prev {
  background: rgba($color: #e89f71, $alpha: 0.3);
  color: #e89f71;
  right: 156px;
  left: initial;
}
</style>
