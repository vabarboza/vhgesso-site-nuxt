<template>
  <div class="empresa-page has-background-white">
    <!-- Header Section -->
    <section class="hero is-medium" style="background-color: var(--bulma-dark);">
      <div class="hero-body is-flex is-align-items-center is-justify-content-center">
        <div class="container has-text-centered">
          <h1 class="title is-1 has-text-weight-bold has-text-white animate__animated animate__fadeInDown">Nossa História</h1>
          <p class="subtitle is-4 mt-3 has-text-light animate__animated animate__fadeInUp animate__delay-1s">
            Transformando gesso em arte e ambientes em inspiração.
          </p>
        </div>
      </div>
    </section>

    <!-- Nossa Trajetoria Section -->
    <section class="section py-6">
      <div class="container my-6">
        <div class="columns is-vcentered is-variable is-8">
          <div class="column is-6">
            <h2 class="title is-3 has-text-dark mb-4">A VH Gesso</h2>
            <div class="divider mb-5"></div>
            <p class="is-size-5 has-text-grey" style="line-height: 1.8;">
              Com anos de experiência no mercado da construção civil e decoração de interiores, a <strong>VH Gesso</strong> nasceu da paixão por transformar projetos em realidade. 
              <br><br>
              Especializamo-nos no fornecimento de soluções em <b>forros, molduras, nichos, divisórias em drywall</b> e as mais belas <b>sancas e decorações em gesso</b>. Acreditamos que o teto e as paredes não são apenas os limites de uma casa, mas telas em branco onde o requinte e o bom gosto ganham forma.
            </p>
          </div>
          <div class="column is-6">
            <figure class="image is-4by3 image-empresa p-2">
              <img src="https://images.unsplash.com/photo-1600585154340-be6161a56a0c?auto=format&fit=crop&q=80&w=800" alt="Interior moderno em gesso" style="border-radius: 12px; object-fit: cover; box-shadow: 0 10px 30px rgba(0,0,0,0.1);">
            </figure>
          </div>
        </div>
      </div>
    </section>

    <!-- Missão / Visão / Valores (Cards Premium) -->
    <section class="section has-background-light py-6" style="background-color: #fafaf9 !important;">
      <div class="container pt-4 pb-6">
        <div class="columns is-multiline is-centered">
          
          <!-- Missão -->
          <div class="column is-4">
            <div class="card premium-card">
              <div class="card-content has-text-centered p-6">
                <span class="icon is-large has-text-primary mb-4">
                  <i class="fas fa-bullseye fa-3x"></i>
                </span>
                <h3 class="title is-4 has-text-dark">Nossa Missão</h3>
                <p class="has-text-grey">
                  Proporcionar aos nossos clientes ambientes modernos e aconchegantes através do gesso e drywall, combinando materiais de excelência, preço justo e prazos garantidos.
                </p>
              </div>
            </div>
          </div>

          <!-- Visão -->
          <div class="column is-4">
            <div class="card premium-card">
              <div class="card-content has-text-centered p-6">
                <span class="icon is-large has-text-primary mb-4">
                  <i class="fas fa-eye fa-3x"></i>
                </span>
                <h3 class="title is-4 has-text-dark">Nossa Visão</h3>
                <p class="has-text-grey">
                  Ser reconhecida como a principal referência da região em soluções de gesso arquitetônico, destacando-se pela inovação constante e resultados estéticos de alto padrão.
                </p>
              </div>
            </div>
          </div>

          <!-- Valores -->
          <div class="column is-4">
            <div class="card premium-card">
              <div class="card-content has-text-centered p-6">
                <span class="icon is-large has-text-primary mb-4">
                  <i class="fas fa-gem fa-3x"></i>
                </span>
                <h3 class="title is-4 has-text-dark">Nossos Valores</h3>
                <p class="has-text-grey">
                  Transparência,<br>
                  Foco em Qualidade,<br>
                  Respeito ao Cliente e Mão de obra devidamente Qualificada.
                </p>
              </div>
            </div>
          </div>

        </div>
      </div>
    </section>

    <!-- Call to Action Banner -->
    <section class="hero is-primary is-small action-banner" style="background-color: var(--bulma-dark);">
      <div class="hero-body px-5 py-6">
        <div class="container has-text-centered">
          <h2 class="title is-3 has-text-white mb-4">Transforme seu projeto com a VH Gesso!</h2>
          <p class="subtitle is-5 has-text-grey-light mb-5">Fale com um de nossos especialistas e solicite seu orçamento sem compromisso.</p>
          <NuxtLink to="/contato" class="button is-primary is-medium is-rounded has-text-weight-bold cta-btn">
            Entrar em Contato <i class="fas fa-arrow-right ml-2"></i>
          </NuxtLink>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
export default {
  name: 'EmpresaPage',
  head() {
    return {
      title: 'A Empresa',
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: 'Conheça a história, missão e valores da VH Gesso, uma empresa referência em projetos arquitetônicos e soluções em gesso.'
        }
      ]
    }
  }
}
</script>

<style scoped>
.divider {
  height: 4px;
  width: 60px;
  background-color: var(--bulma-primary);
  border-radius: 2px;
}

.image-empresa {
  position: relative;
}

.image-empresa::before {
  content: '';
  position: absolute;
  top: -15px;
  left: -15px;
  right: 35px;
  bottom: 35px;
  background-color: var(--bulma-primary);
  border-radius: 12px;
  z-index: -1;
  opacity: 0.15;
}

.premium-card {
  height: 100%;
  border-radius: 16px;
  border: none;
  box-shadow: 0 4px 15px rgba(0,0,0,0.03);
  transition: all 0.3s cubic-bezier(0.25, 0.8, 0.25, 1);
  background: white;
}

.premium-card:hover {
  transform: translateY(-8px);
  box-shadow: 0 15px 35px rgba(0, 0, 0, 0.08);
}

.action-banner {
  border-top: 4px solid var(--bulma-primary);
}

.cta-btn {
  box-shadow: 0 4px 15px rgba(168, 148, 115, 0.3) !important;
  transition: transform 0.2s ease, box-shadow 0.2s ease;
}

.cta-btn:hover {
  transform: translateY(-2px);
  box-shadow: 0 6px 20px rgba(168, 148, 115, 0.5) !important;
}
</style>
