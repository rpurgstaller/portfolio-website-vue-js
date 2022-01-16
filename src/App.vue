<template>
  <div id="app">
    <div class="main">
      <Header :viewport="viewport" />
      <router-view></router-view>
    </div>
  </div>
</template>

<script>
import Header from '@/components/Header.vue'

import '@/styles/app.scss'

export default {
  name: 'Index',
  components: {
    Header
  },
  data: () => {
    return {
      viewport: {
        width: window.innerWidth,
        height: window.innerHeight,
        is568: window.innerWidth <= 568,
        is768: window.innerWidth <= 768,
        is1024: window.innerWidth <= 1024
      }
    }
  }
}
</script>
