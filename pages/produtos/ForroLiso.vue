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
              <figure class="image">
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

    <div class="container pl-5 pr-5">

      <div class="fixed-grid has-4-cols has-1-cols-mobile">
        <div class="grid">

          <div class="cell">
            <figure class="image js-modal-trigger" data-target="modal-js-example">
              <img id="modal-trigger" src="~/assets/images/produtos/forroliso/01.jpeg" />
            </figure>
          </div>

          <div class="cell">
            <figure class="image js-modal-trigger" data-target="modal-js-example">
              <img src="~/assets/images/produtos/forroliso/02.jpeg" />
            </figure>
          </div>

          <div class="cell">
            <figure class="image js-modal-trigger" data-target="modal-js-example">
              <img src="~/assets/images/produtos/forroliso/03.jpeg" />
            </figure>
          </div>

          <div class="cell">
            <figure class="image js-modal-trigger" data-target="modal-js-example">
              <img src="~/assets/images/produtos/forroliso/04.jpeg" />
            </figure>
          </div>

        </div>
      </div>

      <div class="fixed-grid has-4-cols has-1-cols-mobile">
        <div class="grid">

          <div class="cell">
            <figure class="image js-modal-trigger" data-target="modal-js-example">
              <img src="~/assets/images/produtos/forroliso/05.jpeg" style="width: 350px;" />
            </figure>
          </div>

          <div class="cell">
            <figure class="image js-modal-trigger" data-target="modal-js-example">
              <img src="~/assets/images/produtos/forroliso/06.jpeg" style="width: 350px;" />
            </figure>
          </div>

          <div class="cell">
            <figure class="image js-modal-trigger" data-target="modal-js-example">
              <img src="~/assets/images/produtos/forroliso/07.jpeg" style="width: 350px;" />
            </figure>
          </div>

          <div class="cell">
            <figure class="image js-modal-trigger" data-target="modal-js-example">
              <img src="~/assets/images/produtos/forroliso/08.jpeg" style="width: 350px;" />
            </figure>
          </div>

        </div>
      </div>

    </div>

    <!-- Modal -->
    <div id="modal-js-example" class="modal">
      <div class="modal-background"></div>

      <div class="modal-content has-text-centered">
        <figure class="image">
          <img id="modal-image" src="" />
        </figure>
      </div>

      <button class="modal-close is-large" aria-label="close"></button>
    </div>

  </div>
</template>

<script>
export default {
  mounted() {
    document.addEventListener('DOMContentLoaded', () => {
      // Functions to open and close a modal
      function openModal($el, imageSrc) {
        const modalImage = $el.querySelector('#modal-image');
        modalImage.src = imageSrc;
        $el.classList.add('is-active');
      }

      function closeModal($el) {
        $el.classList.remove('is-active');
      }

      function closeAllModals() {
        (document.querySelectorAll('.modal') || []).forEach(($modal) => {
          closeModal($modal);
        });
      }

      // Add a click event on figures to open a specific modal with the clicked image
      (document.querySelectorAll('.js-modal-trigger') || []).forEach(($trigger) => {
        const modalId = $trigger.dataset.target;
        const $target = document.getElementById(modalId);

        $trigger.addEventListener('click', () => {
          const img = $trigger.querySelector('img');
          const imageSrc = img.src;
          openModal($target, imageSrc);
        });
      });

      // Add a click event on various child elements to close the parent modal
      (document.querySelectorAll('.modal-background, .modal-close, .modal-card-head .delete, .modal-card-foot .button') || []).forEach(($close) => {
        const $target = $close.closest('.modal');

        $close.addEventListener('click', () => {
          closeModal($target);
        });
      });

      // Add a keyboard event to close all modals
      document.addEventListener('keydown', (event) => {
        if (event.key === "Escape") {
          closeAllModals();
        }
      });
    });
  }
}
</script>

<style></style>