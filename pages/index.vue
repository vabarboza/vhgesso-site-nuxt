<template>
  <div>
    <div class="container p-5">
      <section class="bordered has-text-centered">
        <p class="subtitle is-6 has-text-weight-semibold m-5">NOSSOS PRODUTOS</p>
      </section>

      <section class="section has-text-centered">
        <p>Estes são alguns exemplos de nossos serviços e produtos nas quais temos para oferecer.</p>
      </section>
    </div>

    <div class="container pl-5 pr-5 pb-6">
      <div class="fixed-grid has-3-cols has-1-cols-mobile">
        <div class="grid">
          <div class="cell" v-for="(produto, index) in produtos" :key="index">
            <div class="card">
              <div class="card-image">
                <NuxtLink :to="produto.link">
                  <figure class="image">
                    <img :src="produto.imagem" :alt="produto.titulo">
                  </figure>
                </NuxtLink>
              </div>
              <div class="card-content">
                <h2 class="title" :class="produto.tituloClass || 'is-4'">{{ produto.titulo }}</h2>
                <p class="is-size-7">{{ produto.descricao }}</p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
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
      ]
    }
  }
}
</script>

<style scoped>
.card {
  transition: transform 0.3s ease, box-shadow 0.3s ease;
  height: 100%;
}

.card:hover {
  transform: scale(1.03);
  box-shadow: 0 10px 20px rgba(0, 0, 0, 0.15);
  cursor: pointer;
}
</style>