<template>
  <nav class="navbar container" role="navigation" aria-label="main navigation">
    <div class="navbar-brand">
      <NuxtLink class="navbar-item" to="/">
        <img class="animate__animated animate__pulse" src="~/assets/images/logo.png" />
      </NuxtLink>

      <a role="button" class="navbar-burger" aria-label="menu" aria-expanded="false" :class="{ 'is-active': isMenuActive }" @click="isMenuActive = !isMenuActive">
        <span aria-hidden="true"></span>
        <span aria-hidden="true"></span>
        <span aria-hidden="true"></span>
        <span aria-hidden="true"></span>
      </a>
    </div>

    <div class="navbar-menu" :class="{ 'is-active': isMenuActive }">
      <div class="navbar-start">
        <NuxtLink class="navbar-item" to="/">
          Inicio
        </NuxtLink>

        <NuxtLink class="navbar-item" to="/empresa">
          A Empresa
        </NuxtLink>

        <div class="navbar-item has-dropdown is-hoverable">
          <a class="navbar-link">
            Produtos
          </a>

          <div class="navbar-dropdown">
            <NuxtLink class="navbar-item" to="/produtos/forroliso">
              Forro Liso
            </NuxtLink>
            <NuxtLink class="navbar-item" to="/produtos/molduras">
              Molduras
            </NuxtLink>
            <NuxtLink class="navbar-item" to="/produtos/gesso-acartonado">
              Gesso Acartonado
            </NuxtLink>
            <NuxtLink class="navbar-item" to="/produtos/sancas">
              Sancas
            </NuxtLink>
            <NuxtLink class="navbar-item" to="/produtos/colunas-decorativas">
              Colunas Decorativas
            </NuxtLink>
            <NuxtLink class="navbar-item" to="/produtos/gesso-decorado">
              Gesso Decorado
            </NuxtLink>
          </div>
        </div>

        <div class="navbar-item has-dropdown is-hoverable">
          <a class="navbar-link">
            Parceria
          </a>

          <div class="navbar-dropdown">
            <NuxtLink class="navbar-item" to="/parceiros-especiais">
              Parceiros Especiais
            </NuxtLink>
            <NuxtLink class="navbar-item" to="/parceiros">
              Parceiros
            </NuxtLink>
            <NuxtLink class="navbar-item" to="/seja-parceiro">
              Quero ser um parceiro
            </NuxtLink>
          </div>
        </div>

        <NuxtLink class="navbar-item" to="/sobre">
          Contato
        </NuxtLink>

      </div>

      <div class="navbar-end">
        <div class="navbar-item">
          <div class="buttons">
            <a href="#" class="navbar-item mr-n2" target="_blank" rel="noopener noreferrer">
              <span class="icon">
                <i class="fab fa-instagram fa-lg"></i>
              </span>
            </a>
            <a href="#" class="navbar-item mr-n2" target="_blank" rel="noopener noreferrer">
              <span class="icon">
                <i class="fab fa-whatsapp fa-lg"></i>
              </span>
            </a>
            <a href="#" class="navbar-item" target="_blank" rel="noopener noreferrer">
              <span class="icon">
                <i class="fab fa-facebook-square fa-lg"></i>
              </span>
            </a>
          </div>
        </div>
      </div>
    </div>
  </nav>
</template>

<script>
export default {
  name: 'NavBar',
  data() {
    return {
      isMenuActive: false
    }
  }
}
</script>

<style scoped>
.mr-n2 {
  margin-right: -10px;
}
</style>
