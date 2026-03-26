<template>
  <div>
    <!-- Por que nos escolher Section -->
    <section class="section has-background-white">
      <div class="container">
        <div class="has-text-centered mb-6">
          <h2 class="title is-3 has-text-weight-bold has-text-dark">Por que escolher a VH Gesso?</h2>
          <p class="subtitle is-6 mt-2">Compromisso com o estilo e a qualidade do seu projeto.</p>
        </div>
        
        <div class="columns is-multiline is-centered">
          <div class="column is-4 has-text-centered p-5 feature-block">
            <span class="icon is-large has-text-primary mb-4">
              <i class="fas fa-medal fa-3x"></i>
            </span>
            <h3 class="title is-5 has-text-weight-bold">Alta Qualidade</h3>
            <p>Trabalhamos apenas com materiais de primeira linha e técnicas modernas para garantir um acabamento perfeito e duradouro.</p>
          </div>
          <div class="column is-4 has-text-centered p-5 feature-block">
            <span class="icon is-large mb-4 animate__animated animate__pulse animate__infinite" style="color: var(--bulma-primary);">
              <i class="fas fa-clock fa-3x"></i>
            </span>
            <h3 class="title is-5 has-text-weight-bold">Agilidade na Entrega</h3>
            <p>Cumprimos nossos prazos à risca, entregando sua obra reformada ou decorada no tempo estipulado, sem surpresas.</p>
          </div>
          <div class="column is-4 has-text-centered p-5 feature-block">
            <span class="icon is-large mb-4 animate__animated animate__pulse animate__infinite" style="color: var(--bulma-primary);">
              <i class="fas fa-hard-hat fa-3x"></i>
            </span>
            <h3 class="title is-5 has-text-weight-bold">Mão de Obra Especializada</h3>
            <p>Nossa equipe conta com profissionais experientes e altamente qualificados no ramo de gesso e dry-wall.</p>
          </div>
        </div>
      </div>
    </section>

    <!-- Nossos Produtos Section -->
    <section class="section py-6" style="background-color: var(--bulma-scheme-main);">
      <div class="container">
        <div class="has-text-centered mb-6">
          <h2 class="title is-3 has-text-weight-bold has-text-dark">Nossos Serviços e Produtos</h2>
          <div class="divider"></div>
          <p class="subtitle is-5 mt-4">Soluções inovadoras para transformar qualquer ambiente.</p>
        </div>

        <div class="fixed-grid has-3-cols has-1-cols-mobile">
          <div class="grid">
            <div class="cell" v-for="(produto, index) in produtos" :key="index">
              <NuxtLink :to="produto.link" class="card product-card is-flex is-flex-direction-column">
                <div class="card-image">
                  <figure class="image is-4by3">
                    <img :src="produto.imagem" :alt="produto.titulo" style="object-fit: cover;">
                  </figure>
                </div>
                <div class="card-content is-flex-grow-1 is-flex is-flex-direction-column">
                  <h2 class="title" :class="produto.tituloClass || 'is-4'">{{ produto.titulo }}</h2>
                  <p class="is-size-6 mt-2 mb-4 has-text-grey" style="flex-grow: 1;">
                    {{ produto.descricao | truncate(95) }}
                  </p>
                  
                  <div class="mt-auto pt-3 border-top-light" style="border-top: 1px solid #eaeaea; display: flex; align-items: center;">
                    <span class="has-text-primary has-text-weight-bold operates-link">
                      Saiba mais <i class="fas fa-arrow-right ml-1"></i>
                    </span>
                  </div>
                </div>
              </NuxtLink>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Depoimentos Section -->
    <section class="section has-background-white">
      <div class="container">
        <div class="has-text-centered mb-6">
          <h2 class="title is-3 has-text-weight-bold has-text-dark">O que nossos clientes dizem</h2>
          <div class="divider"></div>
        </div>

        <div class="columns is-multiline is-centered">
          <div class="column is-4" v-for="(depoimento, index) in depoimentos" :key="'dep-'+index">
            <div class="card testimonial-card is-flex is-flex-direction-column p-5">
              <div class="mb-4 has-text-primary">
                <i class="fas fa-star" v-for="n in 5" :key="'star-'+n"></i>
              </div>
              <p class="is-italic mb-4 has-text-grey" style="flex-grow: 1;">
                "{{ depoimento.texto }}"
              </p>
              <div class="is-flex is-align-items-center mt-auto pt-4" style="border-top: 1px solid #f1f1f1;">
                <figure class="image is-48x48 mr-3">
                  <img class="is-rounded" :src="depoimento.foto" :alt="depoimento.nome">
                </figure>
                <div>
                  <h4 class="title is-6 mb-0">{{ depoimento.nome }}</h4>
                  <p class="is-size-7 has-text-grey">{{ depoimento.local }}</p>
                </div>
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
  name: 'IndexPage',
  head() {
    return {
      title: 'Produtos e Serviços em Gesso',
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: 'Conheça nossos produtos: Forro Liso, Molduras, Gesso Acartonado, Sancas, Colunas Decorativas e Gesso Decorado.'
        }
      ]
    }
  },
  filters: {
    truncate(value, length) {
      if (!value) return '';
      if (value.length <= length) return value;
      return value.substring(0, length) + '...';
    }
  },
  data() {
    return {
      produtos: [
        {
          titulo: 'Forro Liso',
          tituloClass: 'is-4',
          descricao: 'É a tendência do momento usado para revestir paredes e teto pela sua versatilidade, plasticidade e acabamento. Ele traz um toque sutil e fino, paredes com bom acabamento de Gesso Liso e uma boa tinta é notória sua diferença e classe.',
          imagem: require('~/assets/images/inicio/01.jpg'),
          link: '/produtos/forroliso'
        },
        {
          titulo: 'Molduras',
          tituloClass: 'is-4',
          descricao: 'Molduras de Gesso há tempos é o toque final de acabamento colocando requinte nos perímetros dos ambientes, nós da VH Gesso utilizamos molduras fabricadas com materiais de qualidade e disponibilizamos mão de obra qualificada para a aplicação da mesma, além de ter opções à pronta entrega e modelos atuais com estilos contemporâneos de arquitetura moderna.',
          imagem: require('~/assets/images/inicio/02.jpg'),
          link: '/produtos/molduras'
        },
        {
          titulo: 'Gesso Acartonado',
          tituloClass: 'is-4',
          descricao: 'Esse sistema é popularmente chamado de parede ou forro de drywall, por isso, muitas pessoas confundem forro drywall e gesso acartonado, achando que são produtos diferentes, quando na verdade o drywall é o sistema de construção utilizado para a instalação do gesso acartonado.',
          imagem: require('~/assets/images/inicio/03.jpg'),
          link: '/produtos/gesso-acartonado'
        },
        {
          titulo: 'Sancas',
          tituloClass: 'is-5',
          descricao: 'Sanca ou rebaixamento de teto realmente fazem a diferença nos mais diferentes ambientes trazendo estilo, requinte e beleza. A VH Gesso tem sempre o melhor projeto de sanca e iluminação com as melhores soluções. Sempre atendendo o Perfil e necessidade de nossos Clientes com projetos únicos e exclusivos.',
          imagem: require('~/assets/images/inicio/04.jpg'),
          link: '/produtos/sancas'
        },
        {
          titulo: 'Colunas Decorativas',
          tituloClass: 'is-5',
          descricao: 'As colunas são utilizadas na decoração do ambiente e são, também, muito utilizadas para a limitação (divisão) do ambiente. Elas podem ser lisas ou caneladas "tipo grego". Tanto a coluna lisa como a coluna decorada têm acompanhamento da base, para acabamento no pé da coluna, e do capitel, para acompanhamento em cima da coluna. As Colunas em gesso são muito úteis na decoração externa.',
          imagem: require('~/assets/images/inicio/05.jpg'),
          link: '/produtos/colunas-decorativas'
        },
        {
          titulo: 'Gesso Decorado',
          tituloClass: 'is-5',
          descricao: 'Esse revestimento é feito através de placas de gesso com desenhos em auto relevo em uma das faces, que cria um efeito sensacional e maravilhoso de luz e sombra nas paredes que são aplicados. As texturas e composições que esse revestimento agrega no ambiente valoriza e aumenta muito a sensação de requinte e conforto do espaço.',
          imagem: require('~/assets/images/inicio/06.jpg'),
          link: '/produtos/gesso-decorado'
        }
      ],
      depoimentos: [
        {
          nome: 'Carlos Mendes',
          local: 'Sorocaba - SP',
          texto: 'Trabalho impecável e atendimento de primeira. Fizeram todo o rebaixamento de gesso da minha sala e o resultado superou as expectativas. Altamente recomendável!',
          foto: 'https://ui-avatars.com/api/?name=Carlos+Mendes&background=a89473&color=fff'
        },
        {
          nome: 'Mariana Silva',
          local: 'Votorantim - SP',
          texto: 'Super recomendo! Precisávamos de uma divisória de drywall rápida e a equipe da VH Gesso nos atendeu com muita agilidade, profissionalismo e limpeza no local da obra.',
          foto: 'https://ui-avatars.com/api/?name=Mariana+Silva&background=1e293b&color=fff'
        },
        {
          nome: 'Roberto Antunes',
          local: 'Sorocaba - SP',
          texto: 'A sanca instalada no meu quarto ficou lindíssima. Profissionais pontuais, e o preço cobrado foi bastante justo pela extrema qualidade entregue.',
          foto: 'https://ui-avatars.com/api/?name=Roberto+Antunes&background=a89473&color=fff'
        }
      ]
    }
  }
}
</script>

<style scoped>
.feature-block {
  transition: transform 0.3s ease;
}
.feature-block:hover {
  transform: translateY(-5px);
}

.divider {
  height: 4px;
  width: 60px;
  background-color: var(--bulma-primary); /* Uses the new sand/bronze */
  margin: 0 auto;
  border-radius: 2px;
}

.product-card {
  transition: all 0.3s cubic-bezier(0.25, 0.8, 0.25, 1);
  height: 100%;
  border-radius: 12px;
  overflow: hidden;
  border: none;
  box-shadow: 0 4px 10px rgba(0,0,0,0.06);
  background: white;
  text-decoration: none;
}

.product-card:hover {
  transform: translateY(-8px);
  box-shadow: 0 15px 30px rgba(0, 0, 0, 0.12);
}

.product-card .card-image {
  overflow: hidden;
}

.product-card .image img {
  transition: transform 0.5s ease;
}

.product-card:hover .image img {
  transform: scale(1.06);
}

.operates-link {
  transition: padding-left 0.3s ease;
}

.product-card:hover .operates-link {
  padding-left: 6px;
}

.testimonial-card {
  border-radius: 12px;
  box-shadow: 0 4px 15px rgba(0,0,0,0.04);
  background-color: #fafaf9;
  border: 1px solid rgba(0,0,0,0.02);
  height: 100%;
}
</style>