<template>
  <div>
    <NavBar />
    <BannerSite />
    <Nuxt />
  </div>
</template>

<script>
import NavBar from '~/components/NavBar.vue'
import BannerSite from '~/components/BannerSite.vue'

export default {
  name: 'DefaultLayout',
  components: {
    NavBar,
    BannerSite,
  }

}
</script>
