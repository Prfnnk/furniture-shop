<template>
  <div class="header__right">
    <div class="header__right-item">
      <img src="../assets/images/Heart.svg" alt="" />
    </div>
    <div class="header__right-item">
      <img src="../assets/images/Cart.svg" alt="" />
    </div>
    <div class="header__right-item">
      <img src="../assets/images/profile.png" alt="" />
    </div>
  </div>
</template>

<script>
export default {
  name: 'HeaderRight'
}
</script>

<style lang="scss">
.header {
  &__right {
    width: 152px;
    display: flex;
    justify-content: space-between;

    &-item {
      width: 24px;
      cursor: pointer;

      &:last-child {
        width: 40px;
      }
    }
  }
}
</style>
