<template>
  <div class="molduras-page has-background-white">
    <!-- Hero Banner -->
    <section class="hero is-medium" style="background-color: var(--bulma-dark);">
      <div class="hero-body is-flex is-align-items-center is-justify-content-center">
        <div class="container has-text-centered">
          <h1 class="title is-1 has-text-weight-bold has-text-white animate__animated animate__fadeInDown">Molduras de Gesso</h1>
          <p class="subtitle is-4 mt-3 has-text-light animate__animated animate__fadeInUp animate__delay-1s">
            O toque final de acabamento com requinte.
          </p>
        </div>
      </div>
    </section>

    <!-- Apresentação (2 Colunas) -->
    <section class="section py-6">
      <div class="container my-5">
        <div class="columns is-vcentered is-variable is-8">
          <div class="column is-6">
            <h2 class="title is-3 has-text-dark mb-4">Requinte e Sofisticação</h2>
            <div class="divider mb-5"></div>
            <p class="is-size-5 has-text-grey" style="line-height: 1.8;">
              Molduras de Gesso há tempos é o toque final de acabamento colocando requinte nos perímetros dos ambientes. Nós da VH Gesso utilizamos molduras fabricadas com <strong>materiais de qualidade</strong> e disponibilizamos mão de obra altamente qualificada.
              <br><br>
              Com opções à pronta entrega e modelos atuais com estilos contemporâneos de arquitetura moderna, garantimos um detalhe sutil que faz toda a diferença esteticamente.
            </p>
          </div>
          <div class="column is-6">
            <figure class="image is-4by3 image-produto p-2">
              <img :src="imagensProduto[0].src" alt="Ambiente com Molduras de Gesso" style="border-radius: 12px; object-fit: cover; box-shadow: 0 10px 30px rgba(0,0,0,0.1);">
            </figure>
          </div>
        </div>
      </div>
    </section>

    <!-- Seção de Benefícios -->
    <section class="section has-background-light py-6" style="background-color: #fafaf9 !important;">
      <div class="container pt-4 pb-6">
        <div class="has-text-centered mb-6">
          <h2 class="title is-3 has-text-dark">Por que escolher Molduras?</h2>
        </div>
        <div class="columns is-multiline is-centered">
          
          <div class="column is-4">
            <div class="card premium-card">
              <div class="card-content has-text-centered p-6">
                <span class="icon is-large has-text-primary mb-4">
                  <i class="fas fa-gem fa-3x"></i>
                </span>
                <h3 class="title is-4 has-text-dark">Acabamento Refinado</h3>
                <p class="has-text-grey">
                  Dá um toque clássico ou moderno à junção entre a parede e o teto, escondendo quaisquer imperfeições.
                </p>
              </div>
            </div>
          </div>

          <div class="column is-4">
            <div class="card premium-card">
              <div class="card-content has-text-centered p-6">
                <span class="icon is-large has-text-primary mb-4">
                  <i class="fas fa-shapes fa-3x"></i>
                </span>
                <h3 class="title is-4 has-text-dark">Variedade de Modelos</h3>
                <p class="has-text-grey">
                  Temos opções à pronta entrega em perfis escalonados, retos ou decorados para o estilo da sua casa.
                </p>
              </div>
            </div>
          </div>

          <div class="column is-4">
            <div class="card premium-card">
              <div class="card-content has-text-centered p-6">
                <span class="icon is-large has-text-primary mb-4">
                  <i class="fas fa-home fa-3x"></i>
                </span>
                <h3 class="title is-4 has-text-dark">Valorização do Espaço</h3>
                <p class="has-text-grey">
                  Aumenta o valor estético do seu ambiente de forma prática e com um investimento bastante acessível.
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
          <p class="subtitle is-5 has-text-grey mt-2">Confira alguns de nossos projetos com Molduras.</p>
        </div>
        
        <div class="columns is-multiline is-centered">
          <div class="column is-3-desktop is-4-tablet is-6-mobile" v-for="(img, idx) in imagensGaleria" :key="idx">
            <figure class="image is-1by1 cursor-pointer hover-grow gallery-item" @click="openModal(img.src)">
              <img :src="img.src" alt="Projeto Molduras" style="object-fit: cover; width: 100%; height: 100%;">
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
          <p class="subtitle is-5 has-text-grey-light mb-5">Nossa equipe especialista está pronta para transformar seu ambiente.</p>
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
  name: 'MoldurasPage',
  head() {
    return {
      title: 'Molduras de Gesso',
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: 'Molduras de gesso para acabamentos requintados. Confira nossos modelos de molduras clássicas e modernas.'
        }
      ]
    }
  },
  data() {
    return {
      isModalOpen: false,
      currentModalImage: '',
      imagensProduto: [
        { src: require('~/assets/images/inicio/02.jpg') }
      ]
    }
  },
  computed: {
    imagensGaleria() {
      // Retorna as imagens a partir da segunda (índice 1) para a galeria
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
