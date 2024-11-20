<template>
  <div>
    <h1>Clientes:</h1>
    <!-- <input type="text" v-model="nomeClienteOne"> -->
    <input type="text" v-model="clienteOne.nome" />
    <input type="text" v-model="clienteOne.email" />
    <ClienteComp :cliente="clienteOne" />
    <ClienteComp :cliente="clienteOne" />
    <ClienteComp :cliente="clienteOne" />
    <hr />
    <h2>Lista de produtos:</h2>
    <hr />
    <ProdutoComp />
    <ProdutoComp />
  </div>
</template>

<script>
import ClienteComp from "./components/ClienteComp.vue";
import ProdutoComp from "./components/ProdutoComp.vue";

export default {
  name: "App",
  data() {
    return {
      nomeClienteOne: "Diego Max da Silva",
      clienteOne: {
        nome: "Diego Max da Silva",
        email: "diego@email.com",
        idade: 18,
      },
    };
  },
  components: {
    ClienteComp,
    ProdutoComp,
  },
};
</script>

<style>
</style>
