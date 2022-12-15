<template>
  <div id="app">
    <div class="card-imc">
      <div class="row">
        <input
          v-model="massa"
          type="number"
          placeholder="Massa"
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

      <p>IMC: {{ imc }}</p>
      <p class=" obs" style="display: none;">OBS: {{ obs }}</p>
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
      massa: "",
      altura: "",
      imc: "",
      obs: "",
    };
  },
  methods: {
    calcImc() {
  
      if(this.massa === "") document.querySelector('.obs').style.display = "block", this.obs = "";

      else if(this.altura === "") this.obs = ""
   

      this.imc = (this.massa / (this.altura * this.altura)).toFixed(2);
      this.showObs(this.imc);
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
