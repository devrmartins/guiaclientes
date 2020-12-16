<template>
  <div id="app">
    <Cliente
      v-for="cliente in clientes"
      :key="cliente.nome"
      :nome="cliente.nome"
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
        },
        {
          nome: "Marianna",
        },
        {
          nome: "Marina",
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
  margin-top: 60px;
}
</style>
