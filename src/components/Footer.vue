<template>
  <div>
    <span class="rodape"
      >Desenvolvido por Alura | 2023 - Projeto fictício sem fins
      comerciais.</span
    >
  </div>
</template>

<script lang="ts">
export default {};
</script>

<style>
.rodape {
  background: var(--verde-escuro, #263a29);
  padding: 1.5rem 7.5rem;
  display: flex;
  justify-content: center;
  align-items: center;
}

@media only screen and (max-width: 1300px) {
  .rodape {
    padding: 1.5rem 3.75rem;
  }
}

@media only screen and (max-width: 767px) {
  .rodape {
    padding: 1.5rem;
  }
}
</style>
