<template>
  <div id="cliente">
    <h4>Nome: {{ cliente.nome }}</h4>
    <p>E-mail: {{ cliente.email }}</p>
    <p>Idade: {{ cliente.idade }}</p>
  </div>
</template>

<script>
export default {
  data() {
    return {};
  },
  props: {
    nome: String,
    email: String,
    idade: Number,
    cliente: Object,
  },
};
</script>

<style scoped>
#cliente {
  background-color: #ececec;
  max-width: 600px;
  padding: 1%;
  margin-top: 2%;
}

/* #clienteNome {
  color: white;
} */
</style>