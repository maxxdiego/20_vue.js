<template>
  <div id="cliente">
    <!-- Data binding (One-Way Binding) -->
     <input type="text" :value="nome">
     <hr>
     <input type="text" :value="descricao">

    <h2 id="clienteNome">{{ nome }}</h2>
    <p>Descrição do cliente: {{ descricao }}</p>
    <!-- Expressões Javascript -->
    {{ 6 }}
    {{ 2 + 2 * 2 + 2 }}
  </div>
</template>

<script>
export default {
  data() {
    return {
      nome: "Diego Max",
      numero: "",
      email: "",
      idade: 0,
      descricao: "Lorem ipsum dolor sit amet",
    };
  },
};
</script>

<style scoped>
/* #cliente {
  color: green;
  background-color: black;
  max-width: 600px;
  height: 120px;
} */

/* #clienteNome {
  color: white;
} */
</style>