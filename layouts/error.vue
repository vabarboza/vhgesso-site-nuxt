<template>
  <div class="container p-5 has-text-centered error-page">
    <div v-if="error.statusCode === 404">
      <h1 class="title is-1 has-text-weight-bold has-text-danger animate__animated animate__pulse animate__infinite">404</h1>
      <h2 class="subtitle is-3 mt-3">Página Não Encontrada!</h2>
      <p class="is-size-5 mt-4">
        Ops! Parece que o gesso secou e esta página não existe mais ou você digitou um endereço incorreto.
      </p>
    </div>
    <div v-else>
      <h1 class="title is-1 has-text-weight-bold has-text-danger">{{ error.statusCode }}</h1>
      <h2 class="subtitle is-3 mt-3">Ocorreu um Erro!</h2>
      <p class="is-size-5 mt-4">
        Desculpe, uma falha inesperada ocorreu em nossos servidores.
      </p>
    </div>

    <div class="mt-6 pb-6">
      <NuxtLink to="/" class="button is-dark is-medium is-rounded hover-grow">
        <span class="icon is-small mr-2">
          <i class="fas fa-home"></i>
        </span>
        <span>Voltar para o Início</span>
      </NuxtLink>
    </div>
  </div>
</template>

<script>
export default {
  props: ['error'],
  layout: 'default', // Mantém o Cabeçalho (NavBar) e o Rodapé na tela de erro
  head() {
    const titulo = this.error.statusCode === 404 ? 'Página Não Encontrada' : 'Erro Inesperado'
    return {
      title: titulo
    }
  }
}
</script>

<style scoped>
.error-page {
  min-height: 60vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
.title.is-1 {
  font-size: 8rem;
  text-shadow: 2px 2px 10px rgba(0, 0, 0, 0.1);
}
.hover-grow {
  transition: transform 0.3s ease, background-color 0.3s ease;
}
.hover-grow:hover {
  transform: scale(1.05);
  background-color: #363636;
}
</style>
