<template>
<div class="container">
  <transition name="slide">
    <router-view class="page"></router-view>
  </transition>
</div>
</template>

<script>
import locales from './locales.json'

export default {
  created () {
    console.log('page created')
  },
  locales
}
</script>

<style lang="scss">
@import '~@/common/base';
.page {
  transition: transform 300ms, opacity 250ms;
}
</style>
