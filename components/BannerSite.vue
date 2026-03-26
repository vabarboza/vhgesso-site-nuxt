<template>
    <div>
        <section class="hero is-large hero-background">
            <div class="hero-overlay"></div>
            <div class="hero-body is-flex is-align-items-center is-justify-content-center" style="position: relative; z-index: 2;">
                <div class="container has-text-centered">
                    <img class="title responsive-image animate__animated animate__fadeInDown" src="~/assets/images/MainLogo.svg" alt="VH Gesso Logo" />
                    
                    <h2 class="subtitle has-text-dark is-4 has-text-weight-light mt-5 animate__animated animate__fadeInUp animate__delay-1s" style="line-height: 1.6; max-width: 800px; margin: 0 auto;">
                        Excelência em <strong style="color: var(--bulma-primary);">Forros</strong>, <strong style="color: var(--bulma-primary);">Molduras</strong> e <strong style="color: var(--bulma-primary);">Gesso Acartonado</strong>. <br class="is-hidden-mobile">
                        Soluções completas para Divisórias, Sancas, Colunas e Arte em Gesso.
                    </h2>
                    
                    <div class="mt-6 animate__animated animate__fadeInUp animate__delay-2s">
                        <NuxtLink to="/contato" class="button is-primary is-medium is-rounded has-text-weight-bold" style="box-shadow: 0 4px 14px 0 rgba(168, 148, 115, 0.39);">
                            Solicite um Orçamento
                        </NuxtLink>
                    </div>
                </div>
            </div>
        </section>
    </div>
</template>

<script>
export default {
    name: 'BannerSite'
}
</script>

<style scoped>
.hero-background {
    background-image: url('~/assets/images/banner_desktop.jpg');
    background-size: cover;
    background-position: center center;
    background-repeat: no-repeat;
    position: relative;
    background-attachment: fixed; /* Efeito Parallax suave */
}

.hero-overlay {
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background: linear-gradient(135deg, rgba(255, 255, 255, 0.92) 0%, rgba(240, 240, 240, 0.8) 100%);
    z-index: 1;
}

@media (max-width: 768px) {
    .hero-background {
        background-image: url('~/assets/images/banner_novo.png');
        background-attachment: scroll; /* Desabilitar parallax em mobile por performance */
    }
}

.responsive-image {
    height: auto;
    max-height: 250px;
    filter: drop-shadow(0px 4px 6px rgba(0,0,0,0.3));
}

@media (max-width: 768px) {
    .responsive-image {
        max-height: 160px;
    }
    
    .subtitle {
        font-size: 1.1rem !important;
        padding: 0 15px;
    }
}

.button.is-primary {
    transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.button.is-primary:hover {
    transform: translateY(-2px);
    box-shadow: 0 6px 20px rgba(168, 148, 115, 0.5) !important;
}
</style>