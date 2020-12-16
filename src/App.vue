<template>
  <div id="app">
    <div class="container">
      <div class="cadastro">
        <h2>Novo Cliente</h2>
        <div class="form-group">
          <input type="text" placeholder="Nome" v-model="nomeField" />
        </div>
        <div class="form-group">
          <input type="text" placeholder="E-mail" v-model="emailField" />
        </div>
        <div class="form-group">
          <label>Premium</label>
          <input type="checkbox" v-model="premiumField" />
        </div>
        <button class="btn" @click="addCliente">Cadastrar</button>
      </div>
      <div class="clientes">
        <Cliente
          v-for="cliente in clientes"
          :key="cliente.nome"
          :cliente="cliente"
        />
      </div>
    </div>
  </div>
</template>

<script>
import Cliente from "./components/Cliente";
export default {
  name: "App",
  components: { Cliente },
  data() {
    return {
      nomeField: "",
      emailField: "",
      premiumField: false,
      clientes: [],
    };
  },
  methods: {
    addCliente() {
      let newCliente = {
        nome: this.nomeField,
        email: this.emailField,
        isPremium: this.premiumField,
      };
      this.clientes.push(newCliente);
      this.clearForm();
    },
    clearForm() {
      (this.nomeField = ""),
        (this.emailField = ""),
        (this.premiumField = false);
    },
  },
};
</script>

<style>
html {
  box-sizing: border-box;
}
*,
*:before,
*:after {
  box-sizing: inherit;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}

#app .container {
  display: flex;
}

#app .cadastro {
  flex: 1 1 30%;
  width: 30%;
  padding-left: 15px;
  padding-right: 15px;
}

#app .clientes {
  flex: 1 1 70%;
  width: 70%;
  padding-left: 15px;
  padding-right: 15px;
}

.form-group {
  margin-bottom: 5px;
}

.form-group input[type="checkbox"] {
  margin: 5px;
  padding: 0;
}

.form-group input[type="text"] {
  width: 100%;
  padding: 10px 15px;
  display: block;
}

.btn {
  width: 100%;
  display: inline-block;
  padding: 10px 15px;
  background-color: #000;
  color: #fff;
  border: none !important;
  cursor: pointer;
  border-radius: 3px;
  margin: 10px 0;
}
</style>
