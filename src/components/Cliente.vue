<template>
  <div id="cliente" :class="{ isPremium: cliente.isPremium }">
    <h2>{{ cliente.nome }}</h2>
    <h4>{{ cliente.email }}</h4>
  </div>
</template>
<script>
export default {
  name: "Cliente",
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
  background-color: #f5f5f5;
  margin-bottom: 15px;
}
#cliente.isPremium {
  background-color: #fbec3b;
}
#cliente.isPremium h2 {
  color: #b79413;
}
</style>
