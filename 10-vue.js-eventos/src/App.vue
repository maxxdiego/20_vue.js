<template>
  <div>
    <h1>Clientes:</h1>
    <!-- <input type="text" v-model="nomeClienteOne"> -->
    <!-- <input type="text" v-model="clienteOne.nome" />
    <input type="text" v-model="clienteOne.email" /> -->
    <!-- <ClienteComp :cliente="clienteOne" :showIdade="true" />
    <ClienteComp :cliente="clienteOne" :showIdade="false" />
    <ClienteComp :cliente="clienteOne" :showIdade="true" /> -->

    <div v-for="(cliente, index) in clientes" :key="cliente.id">
      <!-- <p>TESTANDO V-FOR</p> -->
       <h4>{{ index + 1 }}</h4>
      <ClienteComp :cliente="cliente" :showIdade="true" />
      <hr>
      <h4>Edição: </h4>
      <input type="text" v-model="cliente.nome" />
      <input type="text" v-model="cliente.email" />
    </div>


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
      clientes: [
        {
          id: 1,
          nome: "Diego Max da Silva",
          email: "diego@email.com",
          idade: 18,
        },
        {
          id: 2,
          nome: "João Pereira",
          email: "joao@email.com",
          idade: 34,
        },
        {
          id: 3,
          nome: "Maria Silva",
          email: "maria@email.com",
          idade: 30,
        },
        {
          id: 4,
          nome: "Pedro Henrique",
          email: "pedro@email.com",
          idade: 19,
        },
      ],
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
