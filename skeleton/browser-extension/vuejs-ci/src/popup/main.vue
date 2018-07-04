<template>
<div class="popup">
  <p>{{text}}</p>
</div>
</template>
<script>
import locales from './locales.json'

export default {
  data () {
    return {
      text: ''
    }
  },
  locales,
  mounted () {
    chrome.tabs.query({
      active: true,
      lastFocusedWindow: true
    }, (tabs) => {
      this.text = tabs[0].url
    })
  }
}
</script>

<style lang="scss">
@import '~@/common/base';

html {
  min-width: 260px;
  min-height: 310px;
  background-color: #f5f5f5;
}

.popup {
  color: #555;
  padding: 4px;
  text-align: center;
  font-size: 16px;
  word-break: break-all;
  word-wrap: break-word;
}

</style>
