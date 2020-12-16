<template>
  <div id="cliente">
    <h2>{{ nome }}</h2>
    <Produto></Produto>
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
    nome: String,
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
