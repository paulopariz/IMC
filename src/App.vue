<template>
  <div id="app">
    <div class="container p-4">
      <sobre-imc></sobre-imc>

      <div class=" calcular">
        <div class="d-grid">

          <input @keyup.enter="calcImc" v-model="peso" type="number" placeholder="Peso" maxlength="10" autofocus />

          <input @keyup.enter="calcImc" v-model="altura" type="number" placeholder="Altura" maxlength="10" />

          <button @click="calcImc" class="calc btn text-white mt-3" >Calcular</button>

          <div>
            <p class="obs">{{ obs }}</p>
          </div>

        </div>
        <p class="imc text-center">SEU IMC: <span>{{ imc }}</span></p>


      </div>


      <tabela-imc></tabela-imc>
    </div>

  </div>
</template>

<script>
  import TabelaImc from './components/TabelaImc.vue';
  import SobreImc from './components/SobreImc.vue'

  export default {
    components: {
      TabelaImc,
      SobreImc
    },

    data() {
      return {
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


        if ((this.peso === "") + (this.altura === ""))(this.altura === ""),
          document.querySelector('.obs').style.display = "block",
          document.querySelector('.imc').style.display = "none",
          document.querySelector('.magreza').style.background = "transparent",
          document.querySelector('.normal').style.background = "transparent",
          document.querySelector('.sobrepeso').style.background = "transparent",
          document.querySelector('.obesidade').style.background = "transparent",
          document.querySelector('.obesidadeGrave').style.background = "transparent",
          this.obs = "Todos os campos devem ser preenchidos";


        else(this.peso === "") + (this.altura === ""),
          document.querySelector('.obs').style.display = "none";

      },
      showObs(imc) {
        if (this.imc < 18.5) document.querySelector('.magreza').style.background = "#4D0FF3",
          document.querySelector('.normal').style.background = "transparent",
          document.querySelector('.sobrepeso').style.background = "transparent",
          document.querySelector('.obesidade').style.background = "transparent",
          document.querySelector('.obesidadeGrave').style.background = "transparent";


        else if (imc < 25) document.querySelector('.normal').style.background = "#4D0FF3",
          document.querySelector('.magreza').style.background = "transparent",
          document.querySelector('.sobrepeso').style.background = "transparent",
          document.querySelector('.obesidade').style.background = "transparent",
          document.querySelector('.obesidadeGrave').style.background = "transparent";


        else if (imc < 30) document.querySelector('.sobrepeso').style.background = "#4D0FF3",
          document.querySelector('.magreza').style.background = "transparent",
          document.querySelector('.normal').style.background = "transparent",
          document.querySelector('.obesidade').style.background = "transparent",
          document.querySelector('.obesidadeGrave').style.background = "transparent";


        else if (imc < 40) document.querySelector('.obesidade').style.background = "#4D0FF3",
          document.querySelector('.magreza').style.background = "transparent",
          document.querySelector('.normal').style.background = "transparent",
          document.querySelector('.sobrepeso').style.background = "transparent",
          document.querySelector('.obesidadeGrave').style.background = "transparent";

        else if (imc > 40) document.querySelector('.obesidadeGrave').style.background = "#4D0FF3",
          document.querySelector('.magreza').style.background = "transparent",
          document.querySelector('.normal').style.background = "transparent",
          document.querySelector('.sobrepeso').style.background = "transparent",
          document.querySelector('.obesidade').style.background = "transparent";
      },
    },
  };
</script>

<style>
  @import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@300;400;600;700;800&display=swap');

  * {
    margin: 0;
    padding: 0;
    font-family: 'Montserrat', sans-serif;
  }

  body {
    background: #1E0153;
    color: #ffffffff;

  }

  h1,
  h2 {
    color: #4FEE9E;
  }

  p {
    font-size: 15px;
    line-height: 27px;
    letter-spacing: 0.6px;
  }

  .calcular {
    display: flex;
    align-items: center;
    margin-top: 6rem;
  }

  input {
    width: 300px;
    padding: 8px 19px;
    border-radius: 5px;
    margin-bottom: 10px;
    border: none;
    outline: 0;
    font-weight: 600;
    font-size: 14px;
  }

  .btn {
    background-color: #4D0FF3;
    font-weight: 600;
    font-size: 14px;
    letter-spacing: 1px;
    width: 300px;
  }

  .btn:hover {
    background-color: #4b16dd;
  }

  .obs,
  .imc {
    display: none;
  }

  .obs {
    font-size: 13px;
    color: red;
    margin-top: 9px;
  }

  .imc {
    margin-left: 100px;
    font-size: 28px;
    font-weight: 700;
  }

  span {
    color: #4FEE9E;
  }

  @media(max-width: 767px) {
    .calcular {
      display: grid;
      justify-content: center;
    }

    .imc {
      margin-left: 0;
      margin-top: 35px;
    }
  }

  @media(max-width: 575px) {

    p,
    tr,
    th {
      font-size: 9.4px;
    }
  }
</style>