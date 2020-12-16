<template>
  <div id="app">
    <Cliente
      v-for="cliente in clientes"
      :key="cliente.nome"
      :cliente="cliente"
    />
  </div>
</template>

<script>
import Cliente from "./components/Cliente";
export default {
  name: "App",
  components: { Cliente },
  data() {
    return {
      clientes: [
        {
          nome: "Raffael",
          showProdutos: true,
          isPremium: true,
        },
        {
          nome: "Marianna",
          showProdutos: true,
          isPremium: false,
        },
        {
          nome: "Marina",
          showProdutos: false,
          isPremium: true,
        },
      ],
    };
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}
</style>
