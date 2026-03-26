<template>
  <div class="contact-page has-background-white">
    <!-- Header Section -->
    <section class="hero is-small" style="background-color: var(--bulma-scheme-main);">
      <div class="hero-body">
        <div class="container has-text-centered">
          <h1 class="title is-2 has-text-weight-bold has-text-dark">Fale Conosco</h1>
          <p class="subtitle is-5 mt-3 has-text-grey">
            Estamos prontos para atender você. Envie sua mensagem ou utilize nossos canais diretos.
          </p>
        </div>
      </div>
    </section>

    <!-- Main Content -->
    <section class="section">
      <div class="container">
        <div class="columns is-variable is-8 is-centered">
          
          <!-- Contact Details (Left Side) -->
          <div class="column is-5">
            <h2 class="title is-4 has-text-dark mb-5">Informações de Contato</h2>
            <div class="divider mb-6"></div>
            
            <div class="contact-info-block mb-5">
              <span class="icon is-large has-text-primary mr-3">
                <i class="fas fa-map-marker-alt fa-2x"></i>
              </span>
              <div>
                <h3 class="has-text-weight-bold is-size-5 mb-1">Endereço</h3>
                <p class="has-text-grey">Maringa - PR<br>Atendimento presencial sujeito a agendamento.</p>
              </div>
            </div>

            <div class="contact-info-block mb-5">
              <span class="icon is-large has-text-primary mr-3">
                <i class="fab fa-whatsapp fa-2x"></i>
              </span>
              <div>
                <h3 class="has-text-weight-bold is-size-5 mb-1">Telefone / WhatsApp</h3>
                <p class="has-text-grey">(44) 99999-9999</p>
              </div>
            </div>

            <div class="contact-info-block mb-6">
              <span class="icon is-large has-text-primary mr-3">
                <i class="fas fa-envelope fa-2x"></i>
              </span>
              <div>
                <h3 class="has-text-weight-bold is-size-5 mb-1">E-mail</h3>
                <p class="has-text-grey">[EMAIL_ADDRESS]</p>
              </div>
            </div>
            
            <!-- Social Box -->
            <div class="box has-background-dark has-text-white social-box">
              <h4 class="title is-5 has-text-white mb-3">Siga nossas redes sociais</h4>
              <p class="is-size-7 mb-4 has-text-grey-light">Acompanhe nossas obras e novidades diárias.</p>
              <div class="is-flex">
                <a href="#" class="social-icon mr-3"><i class="fab fa-instagram"></i></a>
                <a href="#" class="social-icon mr-3"><i class="fab fa-facebook-f"></i></a>
              </div>
            </div>
          </div>

          <!-- Contact Form (Right Side) -->
          <div class="column is-6">
            <div class="card form-card">
              <div class="card-content p-6">
                <h2 class="title is-4 has-text-dark mb-5">Envie uma Mensagem</h2>
                
                <form @submit.prevent="submitForm">
                  <div class="field mb-4">
                    <label class="label">Nome Completo</label>
                    <div class="control has-icons-left">
                      <input class="input" type="text" placeholder="Ex: João Silva" required>
                      <span class="icon is-small is-left">
                        <i class="fas fa-user"></i>
                      </span>
                    </div>
                  </div>

                  <div class="columns mb-0">
                    <div class="column is-6 pb-0">
                      <div class="field mb-4">
                        <label class="label">E-mail</label>
                        <div class="control has-icons-left">
                          <input class="input" type="email" placeholder="seu@email.com" required>
                          <span class="icon is-small is-left">
                            <i class="fas fa-envelope"></i>
                          </span>
                        </div>
                      </div>
                    </div>
                    <div class="column is-6 pb-0">
                      <div class="field mb-4">
                        <label class="label">Telefone / WhatsApp</label>
                        <div class="control has-icons-left">
                          <input class="input" type="tel" placeholder="(00) 00000-0000" required>
                          <span class="icon is-small is-left">
                            <i class="fas fa-phone"></i>
                          </span>
                        </div>
                      </div>
                    </div>
                  </div>

                  <div class="field mb-4">
                    <label class="label">Assunto</label>
                    <div class="control">
                      <div class="select is-fullwidth">
                        <select>
                          <option>Orçamento para Gesso Acartonado</option>
                          <option>Orçamento para Sanca / Molduras</option>
                          <option>Orçamento para Forro Liso</option>
                          <option>Dúvidas em Geral</option>
                        </select>
                      </div>
                    </div>
                  </div>

                  <div class="field mb-5">
                    <label class="label">Mensagem</label>
                    <div class="control">
                      <textarea class="textarea" rows="4" placeholder="Descreva brevemente o que você precisa..." required></textarea>
                    </div>
                  </div>

                  <div class="control mt-5">
                    <button type="submit" class="button is-primary is-medium is-fullwidth has-text-weight-bold submit-btn">
                      Enviar Mensagem <i class="fas fa-paper-plane ml-2"></i>
                    </button>
                  </div>
                </form>
              </div>
            </div>
          </div>
          
        </div>
      </div>
    </section>
  </div>
</template>

<script>
export default {
  name: 'ContatoPage',
  head() {
    return {
      title: 'Fale Conosco',
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: 'Entre em contato com a VH Gesso para solicitar um orçamento. Atendimento rápido via WhatsApp, telefone ou e-mail.'
        }
      ]
    }
  },
  methods: {
    submitForm() {
      // Logic for form submission
      alert('Sua mensagem foi enviada com sucesso! (Isso é uma simulação)');
    }
  }
}
</script>

<style scoped>
.divider {
  height: 4px;
  width: 50px;
  background-color: var(--bulma-primary); /* bronze color */
  border-radius: 2px;
}

.contact-info-block {
  display: flex;
  align-items: flex-start;
}

.contact-info-block .icon {
  margin-top: -2px;
}

.social-box {
  border-radius: 12px;
  border: none;
  background-color: var(--bulma-dark) !important;
}

.social-icon {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 40px;
  height: 40px;
  border-radius: 50%;
  background-color: rgba(255, 255, 255, 0.1);
  color: #fff;
  transition: all 0.3s ease;
}

.social-icon:hover {
  background-color: var(--bulma-primary);
  transform: translateY(-3px);
}

.form-card {
  border-radius: 16px;
  box-shadow: 0 10px 40px rgba(0, 0, 0, 0.08);
  border: none;
  background-color: #fff;
}

.input, .textarea, .select select {
  box-shadow: none;
  border-color: #e2e8f0;
  border-radius: 8px;
  transition: all 0.3s ease;
}

.input:focus, .textarea:focus, .select select:focus {
  border-color: var(--bulma-primary);
  box-shadow: 0 0 0 3px rgba(168, 148, 115, 0.2);
}

.submit-btn {
  border-radius: 8px;
  transition: transform 0.2s ease, box-shadow 0.2s ease;
}

.submit-btn:hover {
  transform: translateY(-2px);
  box-shadow: 0 6px 15px rgba(168, 148, 115, 0.4) !important;
}
</style>
