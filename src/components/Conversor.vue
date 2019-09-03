<template>
  <div class="conversor">
    <h2>{{moedaA}} to {{moedaB}}</h2>
    <input type="text" v-model="moedaA_value" v-bind:placeholder="moedaA" />
    <input type="button" value="Converter" v-on:click="converter" />
    <h2 class="h2-result">{{moedaB_value}}</h2>
  </div>
</template>

<script>
export default {
  name: "Conversor",
  props: ["moedaA", "moedaB"],
  data() {
    return {
      moedaA_value: "",
      moedaB_value: 0
    };
  },
  methods: {
    converter() {
      const de_para = `${this.moedaA}_${this.moedaB}`;
      const uri = `https://free.currconv.com/api/v7/convert?q=${de_para}&compact=ultra&apiKey=8760e82836b16b39ea54`;
      fetch(uri)
      .then(res =>{
          return res.json();
      })
      .then(json =>{
          const cotacao = json[de_para]
          this.moedaB_value = (cotacao * parseFloat(this.moedaA_value)).toFixed(2)
      });
    }
  }
};
</script>

<style scoped>
.conversor{
    margin-top: 10px;
    padding: 15px;
    max-width: 300px;
    max-height: 120px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
}
.h2-result{
    margin-top: 10px;
}
</style>