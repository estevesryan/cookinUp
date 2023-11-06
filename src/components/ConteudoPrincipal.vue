<template>
  <main class="conteudo-principal">
    <Sualista :ingredientes="ingredientes" />

    <SelecionarIngredientes
      v-if="conteudo === 'SelecionarIngredientes'"
      @adicionar-ingrediente="adicionarIngrediente"
      @remover-ingrediente="removerIngrediente"
      @buscar-receitas="buscarReceitas"
    />

    <MostrarReceitas
      @editar-lista="conteudo = 'SelecionarIngredientes'"
      v-else-if="conteudo === 'MostrarReceitas'"
    />
  </main>
  <Footer />
</template>

<script lang="ts">
import BotaoPrincipal from './BotaoPrincipal.vue';
import Footer from './Footer.vue';
import MostrarReceitas from './MostrarReceitas.vue';
import SelecionarIngredientes from './SelecionarIngredientes.vue';
import Sualista from './Sualista.vue';
import Tag from './Tag.vue';

type Pagina = 'SelecionarIngredientes' | 'MostrarReceitas';

export default {
  data() {
    return {
      ingredientes: [] as string[],
      conteudo: 'SelecionarIngredientes' as Pagina,
    };
  },
  components: {
    SelecionarIngredientes,
    Tag,
    Sualista,
    BotaoPrincipal,
    Footer,
    MostrarReceitas,
  },
  methods: {
    adicionarIngrediente(ingrediente: string) {
      if (this.ingredientes.indexOf(ingrediente) === -1) {
        this.ingredientes.push(ingrediente);
      }
    },

    removerIngrediente(ingrediente: string) {
      this.ingredientes = this.ingredientes.filter(
        (Iingrediente) => ingrediente !== Iingrediente
      );
    },

    buscarReceitas() {
      this.conteudo = 'MostrarReceitas';
    },
  },
};
</script>

<style scoped>
.conteudo-principal {
  padding: 6.5rem 7.5rem;
  border-radius: 3.75rem 3.75rem 0rem 0rem;
  background: var(--creme, #fffaf3);
  color: var(--cinza, #444);

  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 5rem;
}

@media only screen and (max-width: 1300px) {
  .conteudo-principal {
    padding: 5rem 3.75rem;
    gap: 3.5rem;
  }
}

@media only screen and (max-width: 767px) {
  .conteudo-principal {
    padding: 4rem 1.5rem;
    gap: 4rem;
  }
}
</style>
