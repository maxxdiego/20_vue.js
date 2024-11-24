<template>
  <div :class="{ cliente: !isPremium, 'cliente-premium': isPremium }">
    <h4>Nome: {{ cliente.nome }}</h4>
    <p>E-mail: {{ emailProcessado }}</p>
    <!-- <p v-show="showIdade === true">Idade: {{ cliente.idade }}</p> -->
    <p v-if="showIdade === true">Idade: {{ cliente.idade }}</p>
    <!-- <p v-else-if="condição">...</p> -->
    <p v-else>O usuário escondeu a idade!</p>
    <button @click="mudarCor($event)">Mudar cor</button>
    <button @click="emitirEventoDelete">Deletar</button>
    <h4>ID Especial: {{ idEspecial }}</h4>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isPremium: false,
    };
  },
  props: {
    cliente: Object,
    showIdade: Boolean,
  },
  methods: {
    mudarCor: function ($event) {
      console.log($event);
      this.isPremium = !this.isPremium;
    },
    emitirEventoDelete: function () {
      console.log("Emitindo do filho...");
      this.$emit("meDelete", { idDoCliente: this.cliente.id, component: this });
    },
    testar: function () {
      console.log("Testando para valaer!");
      alert("Isso é um alerta!");
    },
  },
  computed: {
    emailProcessado() {
      return this.cliente.email.toUpperCase();
    },
    idEspecial: function () {
      return (
        this.cliente.email +
        this.cliente.nome +
        this.cliente.id
      ).toUpperCase();
    },
  },
};
</script>

<style scoped>
.cliente {
  background-color: #ececec;
  max-width: 600px;
  padding: 1%;
  margin-top: 2%;
}

.cliente-premium {
  background-color: black;
  color: yellow;
  max-width: 600px;
  padding: 1%;
  margin-top: 2%;
}
</style>
