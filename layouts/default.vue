<template>
  <div>
    <NavBar />
    <BannerSite />
    <Nuxt />
    <FooterSite />
  </div>
</template>

<script>
import NavBar from '~/components/NavBar.vue'
import BannerSite from '~/components/BannerSite.vue'
import FooterSite from '~/components/FooterSite.vue';

export default {
  name: 'DefaultLayout',
  components: {
    NavBar,
    BannerSite,
    FooterSite
  }

}
</script>
