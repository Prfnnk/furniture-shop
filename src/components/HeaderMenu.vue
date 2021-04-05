<template>
  <div class="menu">
    <a class="menu__item" href="/products">Products</a>
    <a class="menu__item" href="/products">Rooms</a>
    <a class="menu__item" href="/products">Inspirations</a>
  </div>
</template>

<script>
export default {}
</script>

<style lang="scss">
.menu__item {
  color: #3a3a3a;
  font-weight: 400;
  font-size: 16px;
  line-height: 24px;
  margin-right: 43px;
  text-decoration: none;
  outline: none;

  &:hover {
    text-decoration: underline;
    color: gray;
  }
}
</style>
