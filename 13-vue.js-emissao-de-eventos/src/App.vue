<template>
  <div>
    <h3>Cadastro</h3>
    <small id="nomeErro" v-show="deuErro"
      >O nome é inválido, tente novamente!</small
    ><br />
    <input type="text" placeholder="Nome" v-model="nomeField" /><br />
    <input type="email" placeholder="E-mail" v-model="emailField" /><br />
    <input type="number" placeholder="Idade" v-model="idadeField" /><br />
    <button @click="cadastrarUsuario">Cadastrar</button>
    <hr />

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
      <ClienteComp
        :cliente="cliente"
        :showIdade="true"
        @meDelete="deletarUsuario"
      />
      <hr />
      <!-- <h4>Edição: </h4>
      <input type="text" v-model="cliente.nome" />
      <input type="text" v-model="cliente.email" /> -->
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
      deuErro: false,
      nomeField: "",
      emailField: "",
      idadeField: 0,
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
  methods: {
    cadastrarUsuario: function () {
      if (
        this.nomeField == "" ||
        this.nomeField == " " ||
        this.nomeField.length < 3
      ) {
        console.log("Erro de validação");
        this.deuErro = true;
      } else {
        this.clientes.push({
          nome: this.nomeField,
          email: this.emailField,
          idade: this.idadeField,
          id: Date.now(),
        });
        this.nomeField = "";
        this.emailField = "";
        this.idadeField = "";
        this.deuErro = false;
      }
    },
    deletarUsuario: function ($event) {
      console.log("Recebendo evento!");
      console.log($event.idDoCliente);
      $event.component.testar();
      const id = $event.idDoCliente;
      const novoArray = this.clientes.filter((cliente) => cliente.id != id);
      this.clientes = novoArray;
    },
  },
};
</script>

<style>
#nomeErro {
  color: red;
}
</style>
