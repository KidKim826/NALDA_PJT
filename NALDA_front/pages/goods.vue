<template>
  <div>
    <HeaderComponent />
    <nuxt-child></nuxt-child>
    <FooterComponent />
  </div>
</template>

<script>
export default {
  name: 'GoodsPage',
  components: {},
}
</script>

<style scoped>
::-webkit-scrollbar {
  display: none;
}
</style>
