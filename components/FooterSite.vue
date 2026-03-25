<template>
  <footer class="footer mt-5 pb-6">
    <div class="container">
      <div class="content has-text-centered">
        <p>
          <strong>VH Gesso</strong> &copy; {{ new Date().getFullYear() }}. Todos os direitos reservados.
        </p>
        <p class="is-size-7">
          Trabalhando com excelência em forros, molduras, divisórias e gesso acartonado.
        </p>
      </div>
    </div>
  </footer>
</template>

<script>
export default {
  name: 'FooterSite'
}
</script>

<style scoped>
.footer {
  background-color: #f5f5f5;
  padding: 3rem 1.5rem;
}
</style>