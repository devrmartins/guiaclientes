<template>
  <div id="cliente" :class="{ isPremium: cliente.isPremium }">
    <h2>{{ cliente.nome }}</h2>
    <Produto v-if="cliente.showProdutos"></Produto>
    <button @click="changeColor(cliente)" class="action">Action</button>
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
  methods: {
    changeColor(cliente) {
      cliente.isPremium = !cliente.isPremium;
    },
  },
};
</script>
<style scoped>
#cliente {
  border-radius: 10px;
  padding: 15px;
  max-width: 380px;
  background-color: #f5f5f5;
  margin-bottom: 15px;
}
#cliente.isPremium {
  background-color: #fbec3b;
}
#cliente.isPremium h2 {
  color: #b79413;
}
.action {
  padding: 5px;
  background-color: #000;
  color: #fff;
  border: none !important;
  cursor: pointer;
  border-radius: 3px;
  margin: 10px 0;
}
</style>
