<script lang="ts">
export default {
  props: {
    texto: { type: String, required: true },
  },
};
</script>

<template>
  <span class="ingrediente">
    {{ texto }}
  </span>
</template>

<style scoped>
.ingrediente {
  display: inline-block;
  border-radius: 0.5rem;
  min-width: 4.25rem;
  padding: 0.5rem;
  text-align: center;
  transition: 0.2s;
  color: var(--creme, #fffaf3);
  background: var(--coral, #f0633c);
  font-weight: 700;
}
</style>
