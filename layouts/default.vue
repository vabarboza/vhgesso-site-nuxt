<template>
  <div>
    <NavBar />
    <Nuxt />
  </div>
</template>

<script>
import NavBar from '~/components/NavBar.vue'
export default {
  name: 'DefaultLayout',
  components: {
    NavBar,
  }

}
</script>
