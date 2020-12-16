<template>
  <div id="cliente">
    <h2>{{ cliente.nome }}</h2>
    <Produto v-if="cliente.showProdutos"></Produto>
  </div>
</template>
<script>
import Produto from "./Produto";
export default {
  name: "Cliente",
  components: {
    Produto,
  },
  props: {
    cliente: Object,
  },
};
</script>
<style scoped>
#cliente {
  border-radius: 10px;
  padding: 15px;
  max-width: 380px;
  background: #f5f5f5;
  margin-bottom: 15px;
}
</style>
