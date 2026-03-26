<template>
  <div class="forroliso-page has-background-white">
    <!-- Hero Banner -->
    <section class="hero is-medium" style="background-color: var(--bulma-dark);">
      <div class="hero-body is-flex is-align-items-center is-justify-content-center">
        <div class="container has-text-centered">
          <h1 class="title is-1 has-text-weight-bold has-text-white animate__animated animate__fadeInDown">Forro Liso</h1>
          <p class="subtitle is-4 mt-3 has-text-light animate__animated animate__fadeInUp animate__delay-1s">
            Versatilidade, requinte e acabamento impecável para o seu ambiente.
          </p>
        </div>
      </div>
    </section>

    <!-- Apresentação (2 Colunas) -->
    <section class="section py-6">
      <div class="container my-5">
        <div class="columns is-vcentered is-variable is-8">
          <div class="column is-6">
            <h2 class="title is-3 has-text-dark mb-4">Elegância e Plasticidade</h2>
            <div class="divider mb-5"></div>
            <p class="is-size-5 has-text-grey" style="line-height: 1.8;">
              É a tendência do momento, amplamente utilizado para revestir paredes e tetos graças à sua <strong>versatilidade, plasticidade e acabamento perfeito</strong>.
              <br><br>
              Um forro liso bem executado traz um toque sutil e fino ao espaço. Aliado a uma boa iluminação e pintura, a diferença de classe e sofisticação é notória em qualquer projeto arquitetônico moderno.
            </p>
          </div>
          <div class="column is-6">
            <figure class="image is-4by3 image-produto p-2">
              <img :src="imagensForro[0].src" alt="Ambiente com Forro Liso" style="border-radius: 12px; object-fit: cover; box-shadow: 0 10px 30px rgba(0,0,0,0.1);">
            </figure>
          </div>
        </div>
      </div>
    </section>

    <!-- Seção de Benefícios -->
    <section class="section has-background-light py-6" style="background-color: #fafaf9 !important;">
      <div class="container pt-4 pb-6">
        <div class="has-text-centered mb-6">
          <h2 class="title is-3 has-text-dark">Por que escolher o Forro Liso?</h2>
          <p class="subtitle is-5 has-text-grey mt-2">Vantagens de um acabamento profissional em gesso.</p>
        </div>
        <div class="columns is-multiline is-centered">
          
          <div class="column is-4">
            <div class="card premium-card">
              <div class="card-content has-text-centered p-6">
                <span class="icon is-large has-text-primary mb-4">
                  <i class="fas fa-magic fa-3x"></i>
                </span>
                <h3 class="title is-4 has-text-dark">Estética Clean</h3>
                <p class="has-text-grey">
                  Proporciona superfícies perfeitamente planas e sem emendas aparentes, ideais para decorações modernas e minimalistas.
                </p>
              </div>
            </div>
          </div>

          <div class="column is-4">
            <div class="card premium-card">
              <div class="card-content has-text-centered p-6">
                <span class="icon is-large has-text-primary mb-4">
                  <i class="fas fa-lightbulb fa-3x"></i>
                </span>
                <h3 class="title is-4 has-text-dark">Iluminação Embutida</h3>
                <p class="has-text-grey">
                  Permite a instalação de spots, luminárias e fitas de LED diretamente no teto, escondendo fiações de forma segura e elegante.
                </p>
              </div>
            </div>
          </div>

          <div class="column is-4">
            <div class="card premium-card">
              <div class="card-content has-text-centered p-6">
                <span class="icon is-large has-text-primary mb-4">
                  <i class="fas fa-volume-mute fa-3x"></i>
                </span>
                <h3 class="title is-4 has-text-dark">Conforto Térmico e Acústico</h3>
                <p class="has-text-grey">
                  Atua como um excelente isolante físico, ajudando a regular a temperatura ambiente e abafando ruídos entre pavimentos.
                </p>
              </div>
            </div>
          </div>

        </div>
      </div>
    </section>

    <!-- Galeria de Fotos -->
    <section class="section py-6">
      <div class="container my-5">
        <div class="has-text-centered mb-6">
          <h2 class="title is-3 has-text-dark">Nossas Obras</h2>
          <div class="divider mx-auto mb-5"></div>
          <p class="subtitle is-5 has-text-grey mt-2">Confira alguns de nossos projetos finalizados com Forro Liso.</p>
        </div>
        
        <div class="columns is-multiline is-centered">
          <div class="column is-3-desktop is-4-tablet is-6-mobile" v-for="(img, idx) in imagensGaleria" :key="idx">
            <figure class="image is-1by1 cursor-pointer hover-grow gallery-item" @click="openModal(img.src)">
              <img :src="img.src" alt="Projeto Forro Liso" style="object-fit: cover; width: 100%; height: 100%;">
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
  name: 'ForroLisoPage',
  head() {
    return {
      title: 'Forro Liso',
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: 'O Forro Liso é a tendência do momento para revestir paredes e tetos, oferecendo estética clean, iluminação embutida e isolamento.'
        }
      ]
    }
  },
  data() {
    return {
      isModalOpen: false,
      currentModalImage: '',
      imagensForro: [
        { src: require('~/assets/images/produtos/forroliso/01.jpeg') },
        { src: require('~/assets/images/produtos/forroliso/02.jpeg') },
        { src: require('~/assets/images/produtos/forroliso/03.jpeg') },
        { src: require('~/assets/images/produtos/forroliso/04.jpeg') },
        { src: require('~/assets/images/produtos/forroliso/05.jpeg') },
        { src: require('~/assets/images/produtos/forroliso/06.jpeg') },
        { src: require('~/assets/images/produtos/forroliso/07.jpeg') },
        { src: require('~/assets/images/produtos/forroliso/08.jpeg') }
      ]
    }
  },
  computed: {
    imagensGaleria() {
      // Retorna as imagens a partir da segunda (índice 1) para a galeria,
      // pois a primeira (índice 0) está sendo exibida no topo.
      return this.imagensForro.slice(1);
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