<template>
  <div class="search">
    <input
      class="search__input"
      type="text"
      placeholder="Search for minimalist chair"
    />
  </div>
</template>

<script>
export default {
  name: 'SearchBar'
}
</script>

<style lang="scss">
.search {
  position: relative;
  width: 473px;
  height: 45px;

  &__input {
    width: 100%;
    height: 100%;
    border: none;
    font-size: 14px;
    line-height: 21px;
    color: #616161;
    padding-left: 44px;
  }

  &:before {
    content: '';
    width: 20px;
    height: 20px;
    background-image: url('../assets/images/Search.svg');
    background-size: cover;
    background-repeat: no-repeat;
    position: absolute;
    left: 12px;
    top: 12px;
  }
}
</style>
