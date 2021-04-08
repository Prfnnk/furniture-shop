<template>
  <header class="header">
    <div class="header__logo">
      <img src="../assets/images/logo.svg" alt="" />
    </div>
    <HeaderMenu />
    <SearchBar />
    <HeaderRight />
  </header>
</template>

<script>
export default {
  name: 'Header',
  components: {
    HeaderMenu,
    SearchBar,
    HeaderRight
  }
}
import HeaderMenu from './HeaderMenu.vue'
import SearchBar from './SearchBar.vue'
import HeaderRight from './HeaderRight.vue'
</script>

<style>
.header {
  width: 100%;
  padding: 40px 100px 56px;
  display: flex;
  justify-content: space-between;
  align-items: center;
}
</style>
