<template>
  <div class="sancas-page has-background-white">
    <!-- Hero Banner -->
    <section class="hero is-medium" style="background-color: var(--bulma-dark);">
      <div class="hero-body is-flex is-align-items-center is-justify-content-center">
        <div class="container has-text-centered">
          <h1 class="title is-1 has-text-weight-bold has-text-white animate__animated animate__fadeInDown">Sancas de Gesso</h1>
          <p class="subtitle is-4 mt-3 has-text-light animate__animated animate__fadeInUp animate__delay-1s">
            Sanca ou rebaixamento para os melhores efeitos de iluminação.
          </p>
        </div>
      </div>
    </section>

    <!-- Apresentação (2 Colunas) -->
    <section class="section py-6">
      <div class="container my-5">
        <div class="columns is-vcentered is-variable is-8">
          <div class="column is-6">
            <h2 class="title is-3 has-text-dark mb-4">Diferencial e Luxo</h2>
            <div class="divider mb-5"></div>
            <p class="is-size-5 has-text-grey" style="line-height: 1.8;">
              Sanca ou rebaixamento de teto realmente <strong>fazem a diferença</strong> nos ambientes, trazendo estilo, requinte e beleza inigualáveis.
              <br><br>
              A VH Gesso tem o melhor pacote de soluções de design e iluminação. Criamos abertos, fechados e invertidos, integrando fitas LEDs e lâmpadas dicroicas para atender clientes com projetos únicos e exclusivos.
            </p>
          </div>
          <div class="column is-6">
            <figure class="image is-4by3 image-produto p-2">
              <img :src="imagensProduto[0].src" alt="Projeto de Sancas em Gesso" style="border-radius: 12px; object-fit: cover; box-shadow: 0 10px 30px rgba(0,0,0,0.1);">
            </figure>
          </div>
        </div>
      </div>
    </section>

    <!-- Seção de Benefícios -->
    <section class="section has-background-light py-6" style="background-color: #fafaf9 !important;">
      <div class="container pt-4 pb-6">
        <div class="has-text-centered mb-6">
          <h2 class="title is-3 has-text-dark">Efeitos Luminotécnicos</h2>
        </div>
        <div class="columns is-multiline is-centered">
          
          <div class="column is-4">
            <div class="card premium-card">
              <div class="card-content has-text-centered p-6">
                <span class="icon is-large has-text-primary mb-4">
                  <i class="fas fa-lightbulb fa-3x"></i>
                </span>
                <h3 class="title is-4 has-text-dark">Iluminação Indireta</h3>
                <p class="has-text-grey">
                  Sancas abertas ou invertidas proporcionam uma luz difusa na medida certa, criando um ambiente charmoso e acolhedor.
                </p>
              </div>
            </div>
          </div>

          <div class="column is-4">
            <div class="card premium-card">
              <div class="card-content has-text-centered p-6">
                <span class="icon is-large has-text-primary mb-4">
                  <i class="fas fa-layer-group fa-3x"></i>
                </span>
                <h3 class="title is-4 has-text-dark">Diversidade de Modelos</h3>
                <p class="has-text-grey">
                  Fechadas para focos downlights. Abertas para esconder fitas de LED na calha. Há sempre uma opção que abraça o seu projeto.
                </p>
              </div>
            </div>
          </div>

          <div class="column is-4">
            <div class="card premium-card">
              <div class="card-content has-text-centered p-6">
                <span class="icon is-large has-text-primary mb-4">
                  <i class="fas fa-star fa-3x"></i>
                </span>
                <h3 class="title is-4 has-text-dark">Estética Modernista</h3>
                <p class="has-text-grey">
                  Sensação de requinte e de espaços maiores graças à quebra de linhas retas e blocadas do teto convencional.
                </p>
              </div>
            </div>
          </div>

        </div>
      </div>
    </section>

    <!-- Galeria de Fotos -->
    <section class="section py-6" v-if="imagensGaleria.length > 0">
      <div class="container my-5">
        <div class="has-text-centered mb-6">
          <h2 class="title is-3 has-text-dark">Nossas Obras</h2>
          <div class="divider mx-auto mb-5"></div>
          <p class="subtitle is-5 has-text-grey mt-2">Dê uma olhada no impacto provocado pelas nossas instalações.</p>
        </div>
        
        <div class="columns is-multiline is-centered">
          <div class="column is-3-desktop is-4-tablet is-6-mobile" v-for="(img, idx) in imagensGaleria" :key="idx">
            <figure class="image is-1by1 cursor-pointer hover-grow gallery-item" @click="openModal(img.src)">
              <img :src="img.src" alt="Projeto Sancas" style="object-fit: cover; width: 100%; height: 100%;">
            </figure>
          </div>
        </div>
      </div>
    </section>

    <!-- Call to Action Banner -->
    <section class="hero is-primary is-small action-banner" style="background-color: var(--bulma-dark);">
      <div class="hero-body px-5 py-6">
        <div class="container has-text-centered">
          <h2 class="title is-3 has-text-white mb-4">Inspire-se para o seu projeto?</h2>
          <NuxtLink to="/contato" class="button is-primary is-medium is-rounded has-text-weight-bold cta-btn">
            Solicitar Orçamento Gratuito <i class="fas fa-arrow-right ml-2"></i>
          </NuxtLink>
        </div>
      </div>
    </section>

    <!-- Modal -->
    <div class="modal" :class="{'is-active': isModalOpen}">
      <div class="modal-background" @click="closeModal"></div>
      <div class="modal-content has-text-centered">
        <p class="image">
          <img :src="currentModalImage" style="max-height: 85vh; width: auto; object-fit: contain; margin: 0 auto; display: block; border-radius: 8px;" />
        </p>
      </div>
      <button class="modal-close is-large" aria-label="close" @click="closeModal"></button>
    </div>

  </div>
</template>

<script>
export default {
  name: 'SancasPage',
  head() {
    return {
      title: 'Sancas de Gesso',
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: 'Sancas de gesso abertas, fechadas e invertidas. Confira as opções ideais de iluminação embutida e requinte para salas e quartos.'
        }
      ]
    }
  },
  data() {
    return {
      isModalOpen: false,
      currentModalImage: '',
      imagensProduto: [
        { src: require('~/assets/images/produtos/sanca/01.jpg') },
        { src: require('~/assets/images/produtos/sanca/02.jpg') },
        { src: require('~/assets/images/produtos/sanca/03.jpg') },
        { src: require('~/assets/images/produtos/sanca/04.jpg') },
        { src: require('~/assets/images/produtos/sanca/05.jpg') },
        { src: require('~/assets/images/produtos/sanca/06.jpg') },
        { src: require('~/assets/images/produtos/sanca/07.jpg') },
        { src: require('~/assets/images/produtos/sanca/08.jpg') },
        { src: require('~/assets/images/produtos/sanca/09.jpg') },
        { src: require('~/assets/images/produtos/sanca/10.jpg') }
      ]
    }
  },
  computed: {
    imagensGaleria() {
      // Retornar as imagens da galeria a partir da imagem índice 1
      return this.imagensProduto.slice(1);
    }
  },
  mounted() {
    document.addEventListener('keydown', this.handleKeydown)
  },
  beforeDestroy() {
    document.removeEventListener('keydown', this.handleKeydown)
  },
  methods: {
    openModal(imageSrc) {
      this.currentModalImage = imageSrc
      this.isModalOpen = true
    },
    closeModal() {
      this.isModalOpen = false
      this.currentModalImage = ''
    },
    handleKeydown(e) {
      if (e.key === 'Escape' && this.isModalOpen) {
        this.closeModal()
      }
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
.mx-auto {
  margin-left: auto;
  margin-right: auto;
}

.image-produto {
  position: relative;
}
.image-produto::before {
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

.gallery-item {
  border-radius: 12px;
  overflow: hidden;
  box-shadow: 0 4px 15px rgba(0,0,0,0.08);
}
.cursor-pointer {
  cursor: pointer;
}
.hover-grow {
  transition: transform 0.4s cubic-bezier(0.25, 0.8, 0.25, 1), box-shadow 0.4s ease;
}
.hover-grow:hover {
  transform: scale(1.05);
  box-shadow: 0 15px 30px rgba(0,0,0,0.15);
  z-index: 2;
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
