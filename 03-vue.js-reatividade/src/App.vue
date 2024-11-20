<template>
  <div>
    <h1>Clientes:</h1>
    <ClienteComp/>
    <hr>
      <h2>Lista de produtos:</h2>
    <hr>
    <ProdutoComp/>
    <ProdutoComp/>
  </div>
</template>

<script>
import ClienteComp from "./components/ClienteComp.vue";
import ProdutoComp from "./components/ProdutoComp.vue";

export default {
  name: "App",
  components: {
    ClienteComp,
    ProdutoComp
  },
};
</script>

<style>
</style>
