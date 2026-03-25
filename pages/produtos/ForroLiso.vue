<template>
  <div>
    <div class="container p-5">
      <section class="bordered has-text-centered">
        <p class="subtitle is-6 has-text-weight-semibold m-5">PRODUTOS</p>
      </section>

      <section class="mt-2">
        <div class="container">
          <div class="columns is-mobile is-centered">
            <div class="column is-narrow is-centered">
              <figure class="image cursor-pointer hover-grow" @click="openModal(require('~/assets/images/produtos/forroliso/01.jpeg'))">
                <img src="~/assets/images/produtos/forroliso/01.jpeg" style="width: 350px;" />
              </figure>
            </div>
          </div>
        </div>
      </section>

      <section class="has-text-centered">
        <p class="subtitle is-5 has-text-weight-semibold m-5">Forro Liso</p>
        <p>É a tendência do momento usado para revestir paredes e teto pela sua versatilidade, plasticidade e
          acabamento. Ele trás um toque sutil e fino, paredes com bom acabamento de Gesso Liso e uma boa tinta
          é notória sua diferença e classe.</p>
      </section>
    </div>

    <div class="container pl-5 pr-5 pb-6">
      <div class="fixed-grid has-4-cols has-1-cols-mobile">
        <div class="grid">
          <div class="cell" v-for="(img, idx) in imagensForro" :key="idx">
            <figure class="image cursor-pointer hover-grow" @click="openModal(img.src)">
              <img :src="img.src" :style="img.style" />
            </figure>
          </div>
        </div>
      </div>
    </div>

    <!-- Modal -->
    <div class="modal" :class="{'is-active': isModalOpen}">
      <div class="modal-background" @click="closeModal"></div>
      <div class="modal-content has-text-centered">
        <p class="image">
          <img :src="currentModalImage" style="max-height: 85vh; width: auto; object-fit: contain; margin: 0 auto; display: block;" />
        </p>
      </div>
      <button class="modal-close is-large" aria-label="close" @click="closeModal"></button>
    </div>

  </div>
</template>

<script>
export default {
  data() {
    return {
      isModalOpen: false,
      currentModalImage: '',
      imagensForro: [
        { src: require('~/assets/images/produtos/forroliso/01.jpeg'), style: '' },
        { src: require('~/assets/images/produtos/forroliso/02.jpeg'), style: '' },
        { src: require('~/assets/images/produtos/forroliso/03.jpeg'), style: '' },
        { src: require('~/assets/images/produtos/forroliso/04.jpeg'), style: '' },
        { src: require('~/assets/images/produtos/forroliso/05.jpeg'), style: 'width: 350px;' },
        { src: require('~/assets/images/produtos/forroliso/06.jpeg'), style: 'width: 350px;' },
        { src: require('~/assets/images/produtos/forroliso/07.jpeg'), style: 'width: 350px;' },
        { src: require('~/assets/images/produtos/forroliso/08.jpeg'), style: 'width: 350px;' }
      ]
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
.cursor-pointer {
  cursor: pointer;
}
.hover-grow {
  transition: transform 0.3s ease;
}
.hover-grow:hover {
  transform: scale(1.03);
}
</style>