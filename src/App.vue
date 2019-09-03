<template>
  <div id="app">
    <h1 class="titulo">Conversor de moedas</h1>
    <div class="div-conversor">
      <Conversor moedaA="USD" moedaB="BRL" />
      <Conversor moedaA="BRL" moedaB="USD" />
    </div>
    <div class="div-conversor">
      <Conversor moedaA="CAD" moedaB="BRL" />
      <Conversor moedaA="BRL" moedaB="CAD" />
    </div>
    <div class="div-conversor">
      <Conversor moedaA="EUR" moedaB="BRL" />
      <Conversor moedaA="BRL" moedaB="EUR" />
    </div>
  </div>
</template>

<script>
import Conversor from "./components/Conversor";

export default {
  name: "app",
  components: {
    Conversor
  }
};
</script>

<style>
#app {
  max-width: 900px;
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /*  text-align: center; */
  color: #2c3e50;
  margin-top: 60px;
}
.div-conversor {
  display: flex;
  justify-content: space-around;
}
.titulo{
  text-align: center;
}
</style>
