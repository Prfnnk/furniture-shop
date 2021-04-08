<template>
  <div class="products">
    <div class="advantages">
      <div
        class="advantages__item"
        v-for="advantage in advantages"
        :key="advantage.title"
      >
        <div class="advantage__pic">
          <img :src="advantage.src" alt="advantage.title" />
        </div>
        <div class="advantage__text">
          <div class="advantage__title">{{ advantage.title }}</div>
          <div class="advantage__description">{{ advantage.description }}</div>
        </div>
      </div>
    </div>
    <div class="products__title">Our Products</div>
    <div class="products__block">
      <div
        class="products__block-item"
        v-for="product in products"
        :key="product.title"
      >
        <div class="product__image">
          <img :src="product.img" alt="" />
        </div>
        <div class="product__text">
          <div class="product__title">{{ product.title }}</div>
          <div class="product__description">{{ product.description }}</div>
          <div class="product__price-block">
            <div class="product__price">{{ product.price }}</div>
            <div class="product__price-old">{{ product.oldPrice }}</div>
          </div>
        </div>
        <div class="product__note product__note_new" v-if="product.isNew">
          New
        </div>
        <div class="product__note product__note_sale" v-if="product.isOnSale">
          -{{ product.discount }}%
        </div>
        <div class="product__hover">
          <button class="product__hover-btn">Add to cart</button>
          <div class="product__hover-block">
            <div class="product__hover-action">
              <div class="action__pic">
                <img src="../assets/images/share.svg" alt="share" />
              </div>
              <div class="action__name">Share</div>
            </div>
            <div class="product__hover-action">
              <div class="action__pic">
                <img src="../assets/images/like.svg" alt="like" />
              </div>
              <div class="action__name">Like</div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ProductsBlock',
  data() {
    return {
      advantages: [
        {
          title: 'High Quality',
          description: 'crafted from top materials',
          src: require('../assets/images/trophy.svg')
        },
        {
          title: 'Warrany Protection',
          description: 'Over 2 years',
          src: require('../assets/images/guarantee.svg')
        },
        {
          title: 'Free Shipping',
          description: 'Order over 150 $',
          src: require('../assets/images/shipping.svg')
        },
        {
          title: '24 / 7 Support',
          description: 'Dedicated support',
          src: require('../assets/images/customer-support.svg')
        }
      ],
      products: [
        {
          img: require('../assets/images/image-1.png'),
          title: 'Syltherine',
          description: 'Stylish cafe chair',
          price: 'Rp 2.500.000',
          isNew: false,
          isOnSale: true,
          discount: '30',
          oldPrice: 'Rp 3.500.000'
        },
        {
          img: require('../assets/images/image-2.png'),
          title: 'Leviosa',
          description: 'Stylish cafe chair',
          price: 'Rp 2.500.000',
          isNew: false,
          isOnSale: false,
          discount: '',
          oldPrice: ''
        },
        {
          img: require('../assets/images/image-3.png'),
          title: 'Lolito',
          description: 'Luxury big sofa',
          price: 'Rp 7.000.000',
          isNew: false,
          isOnSale: true,
          discount: '50',
          oldPrice: 'Rp 14.000.000'
        },
        {
          img: require('../assets/images/image-4.png'),
          title: 'Respira',
          description: 'Minimalist fan',
          price: 'Rp 500.000',
          isNew: true,
          isOnSale: false,
          discount: '',
          oldPrice: ''
        },
        {
          img: require('../assets/images/image-5.png'),
          title: 'Grifo',
          description: 'Night lamp',
          price: 'Rp 1.500.000',
          isNew: false,
          isOnSale: false,
          discount: '',
          oldPrice: ''
        },
        {
          img: require('../assets/images/image-6.png'),
          title: 'Muggo',
          description: 'Small mug',
          price: 'Rp 150.000',
          isNew: true,
          isOnSale: false,
          discount: '',
          oldPrice: ''
        },
        {
          img: require('../assets/images/image-7.png'),
          title: 'Pingky',
          description: 'Cute bed set',
          price: 'Rp 7.000.000',
          isNew: false,
          isOnSale: true,
          discount: '50',
          oldPrice: 'Rp 14.000.000'
        },
        {
          img: require('../assets/images/image-8.png'),
          title: 'Potty',
          description: 'Minimalist flower pot',
          price: 'Rp 500.000',
          isNew: true,
          isOnSale: false,
          discount: '',
          oldPrice: ''
        }
      ]
    }
  }
}
</script>

<style lang="scss">
.products {
  width: 100%;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  margin: 88px 0;
  padding: 0 100px;

  &__title {
    font-weight: 700;
    font-size: 40px;
    line-height: 48px;
    text-align: center;
    margin-top: 88px;
  }

  &__block {
    width: 100%;
    margin-top: 32px;
    display: flex;
    justify-content: space-between;
    flex-wrap: wrap;

    &-item {
      width: 23%;
      height: 446px;
      display: flex;
      flex-direction: column;
      align-items: center;
      margin-bottom: 32px;
      cursor: pointer;
      position: relative;

      &:hover .product__hover {
        visibility: visible;
      }
    }
  }
}
.product {
  &__text {
    background: #f4f5f7;
    width: 100%;
    height: 145px;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    align-items: flex-start;
    padding: 16px 30px 30px 16px;
  }
  &__title {
    font-weight: 600;
    font-size: 24px;
    line-height: 29px;
  }
  &__description {
    font-weight: 400;
    font-size: 16px;
    line-height: 24px;
    color: #898989;
  }
  &__price-block {
    width: 100%;
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
  &__price {
    font-weight: 600;
    font-size: 20px;
    line-height: 30px;

    &-old {
      font-weight: 400;
      font-size: 16px;
      line-height: 24px;
      text-decoration-line: line-through;
      color: #b0b0b0;
    }
  }
  &__note {
    position: absolute;
    top: 24px;
    right: 24px;
    width: 48px;
    height: 48px;
    border-radius: 50%;
    color: white;
    font-weight: 500;
    font-size: 16px;
    line-height: 24px;
    display: flex;
    justify-content: center;
    align-items: center;

    &_new {
      background: #2ec1ac;
    }
    &_sale {
      background: #e97171;
    }
  }
  &__hover {
    visibility: hidden;
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: rgba($color: #3a3a3a, $alpha: 0.7);
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    color: white;
    cursor: initial;

    &-btn {
      cursor: pointer;
      outline: none;
      border: none;
      background-color: white;
      font-weight: 600;
      font-size: 16px;
      line-height: 24px;
      color: #e89f71;
      height: 48px;
      width: 202px;
      margin-bottom: 24px;

      &:hover {
        box-shadow: 0 0 10px rgba(0, 0, 0, 0.5);
      }
    }
    &-block {
      display: flex;
    }
    &-action {
      display: flex;
      align-items: center;
      cursor: pointer;
      font-weight: 600;
      font-size: 16px;
      line-height: 24px;

      &:hover {
        font-weight: 700;
      }

      &:first-child {
        margin-right: 48px;
      }
    }
  }
}
.action__pic {
  width: 24px;
  margin-right: 8px;
}
.advantages {
  width: 100%;
  height: 85px;
  display: flex;
  justify-content: space-between;
  align-items: center;

  &__item {
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding-left: 22px;
  }
}
.advantage {
  &__pic {
    width: 40px;
    margin-right: 24px;
  }
  &__text {
    display: flex;
    flex-direction: column;
  }
  &__title {
    font-weight: 600;
    font-size: 18px;
    line-height: 27px;
  }
  &__description {
    color: #898989;
    font-weight: 500;
    font-size: 16px;
    line-height: 24px;
  }
}
</style>
