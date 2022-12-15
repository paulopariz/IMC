<template>
  <div id="app">
    <div class="card-imc">
      <div class="row">
        <input
          v-model="peso"
          type="number"
          placeholder="Peso"
          maxlength="10"
          autofocus
        />
      </div>
      <div class="row">
        <input
          v-model="altura"
          type="number"
          placeholder="Altura"
          maxlength="10"
        />
      </div>
      <button class="calc" @click="calcImc">Calcular</button>

      <p class="imc" style="display: none;">SEU IMC: {{ imc }}</p>
      <p class="obs" style="display: none;">{{ obs }}</p>
    </div>
    <tabela-imc></tabela-imc>
  </div>
</template>

<script>
import TabelaImc from './components/TabelaImc.vue';

export default {
  components: { 
    TabelaImc 
  },
  
  data() {
     return{
      peso: "",
      altura: "",
      imc: "",
      obs: "",
    };
  },
  
  methods: {

    calcImc() {
      this.imc = (this.peso / (this.altura * this.altura)).toFixed(2),
      document.querySelector('.imc').style.display = "block"
      this.showObs(this.imc);


      if((this.peso === "") + (this.altura === ""))  (this.altura === ""),
      document.querySelector('.obs').style.display = "block",
      document.querySelector('.imc').style.display = "none",
      document.querySelector('.magreza').style.background = "transparent",
      document.querySelector('.normal').style.background = "transparent", 
      document.querySelector('.sobrepeso').style.background = "transparent",
      document.querySelector('.obesidade').style.background = "transparent",
      document.querySelector('.obesidadeGrave').style.background = "transparent",
      this.obs = "Todos os campos devem ser preenchidos";


      else (this.peso === "") + (this.altura === ""), 
      document.querySelector('.obs').style.display = "none";

    },
    showObs(imc) {
      if (this.imc < 18.5) document.querySelector('.magreza').style.background = "red",
      document.querySelector('.normal').style.background = "transparent", 
      document.querySelector('.sobrepeso').style.background = "transparent",
      document.querySelector('.obesidade').style.background = "transparent",
      document.querySelector('.obesidadeGrave').style.background = "transparent";


      else if (imc < 25) document.querySelector('.normal').style.background = "red",
      document.querySelector('.magreza').style.background = "transparent",
      document.querySelector('.sobrepeso').style.background = "transparent",
      document.querySelector('.obesidade').style.background = "transparent",
      document.querySelector('.obesidadeGrave').style.background = "transparent";


      else if (imc < 30) document.querySelector('.sobrepeso').style.background = "red",
      document.querySelector('.magreza').style.background = "transparent",
      document.querySelector('.normal').style.background = "transparent", 
      document.querySelector('.obesidade').style.background = "transparent",
      document.querySelector('.obesidadeGrave').style.background = "transparent";


      else if (imc < 40) document.querySelector('.obesidade').style.background = "red",
      document.querySelector('.magreza').style.background = "transparent",
      document.querySelector('.normal').style.background = "transparent", 
      document.querySelector('.sobrepeso').style.background = "transparent",
      document.querySelector('.obesidadeGrave').style.background = "transparent";
      
      else if (imc > 40) document.querySelector('.obesidadeGrave').style.background = "red",
      document.querySelector('.magreza').style.background = "transparent",
      document.querySelector('.normal').style.background = "transparent", 
      document.querySelector('.sobrepeso').style.background = "transparent",
      document.querySelector('.obesidade').style.background = "transparent";
    },
  },
};
</script>

<style>

</style>
