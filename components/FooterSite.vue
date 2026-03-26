<template>
  <footer class="footer modern-footer">
    <div class="container">
      <div class="columns is-multiline">
        
        <!-- Coluna 1: Sobre -->
        <div class="column is-12-mobile is-4-desktop mb-4">
          <div class="footer-logo mb-4">
            <h2 class="title is-4 has-text-white has-text-weight-bold">VH Gesso</h2>
            <div class="divider-small"></div>
          </div>
          <p class="has-text-grey-light is-size-6" style="line-height: 1.6;">
            Trabalhando com excelência em forros, molduras, divisórias e gesso acartonado. 
            Transformamos seu ambiente com estilo, qualidade e pontualidade.
          </p>
        </div>

        <!-- Coluna 2: Links Rápidos -->
        <div class="column is-12-mobile is-3-desktop mb-4">
          <h3 class="title is-5 has-text-white mb-4">Links Rápidos</h3>
          <ul class="footer-links">
            <li><NuxtLink to="/">Início</NuxtLink></li>
            <li><NuxtLink to="/empresa">A Empresa</NuxtLink></li>
            <li><NuxtLink to="/produtos/forroliso">Nossos Produtos</NuxtLink></li>
            <li><NuxtLink to="/contato">Contato</NuxtLink></li>
          </ul>
        </div>

        <!-- Coluna 3: Contato -->
        <div class="column is-12-mobile is-5-desktop mb-4">
          <h3 class="title is-5 has-text-white mb-4">Fale Conosco</h3>
          <ul class="footer-contact">
            <li class="mb-3 is-flex is-align-items-center">
              <span class="icon has-text-primary mr-3"><i class="fab fa-whatsapp is-size-5"></i></span>
              <a href="#" class="has-text-grey-light">(15) 99999-9999</a>
            </li>
            <li class="mb-3 is-flex is-align-items-center">
              <span class="icon has-text-primary mr-3"><i class="fas fa-envelope is-size-5"></i></span>
              <a href="mailto:contato@vhgesso.com.br" class="has-text-grey-light">contato@vhgesso.com.br</a>
            </li>
            <li class="mb-3 is-flex is-align-items-start">
              <span class="icon has-text-primary mr-3 mt-1"><i class="fas fa-map-marker-alt is-size-5"></i></span>
              <span class="has-text-grey-light">Sorocaba - SP<br>Atendimento presencial sujeito a agendamento.</span>
            </li>
          </ul>
        </div>
        
      </div>

      <!-- Copyright Bar -->
      <div class="footer-bottom mt-6 pt-5 is-flex is-justify-content-space-between is-align-items-center is-flex-wrap-wrap">
        <p class="has-text-grey is-size-7 mb-3">
          &copy; {{ new Date().getFullYear() }} <strong>VH Gesso</strong>. Todos os direitos reservados.
        </p>
        <div class="social-icons mb-3">
          <a href="#" class="social-link" aria-label="Instagram"><i class="fab fa-instagram"></i></a>
          <a href="#" class="social-link" aria-label="Facebook"><i class="fab fa-facebook-f"></i></a>
          <a href="#" class="social-link" aria-label="WhatsApp"><i class="fab fa-whatsapp"></i></a>
        </div>
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
.modern-footer {
  background-color: var(--bulma-dark); /* Usando p Deep Slate Gray de main.css */
  padding: 4rem 1.5rem 2rem;
  color: #fff;
}

.divider-small {
  height: 3px;
  width: 40px;
  background-color: var(--bulma-primary);
  border-radius: 2px;
}

.footer-links li {
  margin-bottom: 0.8rem;
}

.footer-links a {
  color: #b5b5b5; /* bulma grey-light */
  transition: all 0.3s ease;
  display: inline-block;
}

.footer-links a:hover {
  color: var(--bulma-primary);
  transform: translateX(5px);
}

.footer-contact a:hover {
  color: var(--bulma-primary) !important;
}

.footer-bottom {
  border-top: 1px solid rgba(255, 255, 255, 0.1);
}

.social-icons {
  display: flex;
  gap: 15px;
}

.social-link {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 38px;
  height: 38px;
  background-color: rgba(255, 255, 255, 0.05);
  color: #fff;
  border-radius: 50%;
  transition: all 0.3s ease;
}

.social-link:hover {
  background-color: var(--bulma-primary);
  color: #fff;
  transform: translateY(-3px);
  box-shadow: 0 4px 10px rgba(168, 148, 115, 0.4);
}
</style>