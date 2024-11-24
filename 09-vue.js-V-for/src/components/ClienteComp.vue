<template>
  <div :class="{'cliente' : !isPremium, 'cliente-premium' : isPremium}">
    <h4>Nome: {{ cliente.nome }}</h4>
    <p>E-mail: {{ cliente.email }}</p>
    <!-- <p v-show="showIdade === true">Idade: {{ cliente.idade }}</p> -->
    <p v-if="showIdade === true">Idade: {{ cliente.idade }}</p>
    <!-- <p v-else-if="condição">...</p> -->
    <p v-else>O usuário escondeu a idade!</p>
    
  </div>
</template>

<script>
export default {
  data() {
    return {
      isPremium: false
    };
  },
  props: {
    cliente: Object,
    showIdade: Boolean
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

/* #clienteNome {
  color: white;
} */

 .cliente-premium {
  background-color: black;
  color: yellow;
  max-width: 600px;
  padding: 1%;
  margin-top: 2%;
 }
</style>