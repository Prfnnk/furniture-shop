<template>
  <div class="wrapper">
    <swiper ref="mySwiper" :options="swiperOptions">
      <swiper-slide v-for="slide in slides" :key="slide.title"
        ><img :src="slide.src" :alt="slide.title" />
        <div class="slide__text">
          <div class="slide__title">{{ slide.title }}</div>
          <div class="slide__description">{{ slide.description }}</div>
          <div class="slide__price">{{ slide.price }}</div>
        </div>
      </swiper-slide>
      <div class="swiper-pagination" slot="pagination"></div>
      <div class="swiper-button-prev" slot="button-prev"></div>
      <div class="swiper-button-next" slot="button-next"></div>
    </swiper>
    <div class="best-offer">
      <div class="best-offer__title">High-Quality Furniture Just For You</div>
      <div class="best-offer__description">
        Our furniture is made from selected and best quality materials that are
        suitable for your dream home
      </div>
      <button class="best-offer__button">Shop Now</button>
    </div>
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
      slides: [
        {
          src: require('../assets/images/swiper-pic-1.png'),
          title: 'Bohauss',
          description: 'Luxury big sofa 2-seat',
          price: 'Rp 17.000.000'
        },
        {
          src: require('../assets/images/swiper-pic-2.png'),
          title: 'Kekhauss',
          description: 'Luxury king-size bed',
          price: 'Rp 15.000.000'
        },
        {
          src: require('../assets/images/swiper-pic-3.png'),
          title: 'Pekhauss',
          description: 'Luxury big sofa for chilling nights',
          price: 'Rp 25.000.000'
        }
      ],
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
  position: relative;
}
.swiper-container {
  padding-top: 70px;
}
.swiper-slide {
  width: 934px;
  height: 553px;
}
.slide {
  &__text {
    position: absolute;
    bottom: 40px;
    right: 40px;
    width: 294px;
    height: 148px;
    background: rgba(255, 255, 255, 0.72);
    backdrop-filter: blur(31px);
    cursor: pointer;
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    justify-content: space-between;
    padding: 24px;

    &:after {
      content: '';
      position: absolute;
      bottom: 24px;
      right: 24px;
      width: 24px;
      height: 24px;
      background-image: url('../assets/images/arrow-right.svg');
      background-size: cover;
      background-repeat: no-repeat;
    }
  }
  &__title {
    font-weight: 600;
    font-size: 28px;
    line-height: 34px;
  }
  &__description {
    font-weight: 400;
    font-size: 16px;
    line-height: 24px;
    color: #616161;
  }
  &__price {
    font-weight: 600;
    font-size: 20px;
    line-height: 30px;
  }
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

  &:hover {
    box-shadow: 0 0 5px rgba(0, 0, 0, 0.2);
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
//rest
.best-offer {
  position: absolute;
  top: -20px;
  left: 100px;
  width: 494px;
  height: 553px;
  background: rgba(255, 255, 255, 0.72);
  backdrop-filter: blur(31px);
  z-index: 2;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  align-items: center;
  padding: 60px;

  &__title {
    font-weight: 700;
    font-size: 56px;
    line-height: 67px;
  }
  &__description {
    font-weight: 400;
    font-size: 20px;
    line-height: 30px;
    color: #898989;
    text-align: left;
  }
  &__button {
    width: 374px;
    height: 78px;
    background: #e89f71;
    color: white;
    border: none;
    cursor: pointer;
    font-family: 'Gilroy', sans-serif;
    font-weight: 600;
    font-size: 20px;
    line-height: 30px;
    outline: none;

    &:hover {
      box-shadow: 0 0 5px rgba(0, 0, 0, 0.2);
    }
  }
}
</style>
