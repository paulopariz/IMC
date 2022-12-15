<template>
    <div>
      <table class="table text-white">
        <thead>
          <tr>
            <th scope="col">IMC</th>
            <th scope="col">CLASSIFICAÇÃO</th>
            <th scope="col">GRAU DE OBESIDADE</th>
          </tr>
        </thead>
        <tbody>
          <tr class="magreza">
            <td>MENOR QUE 18,5</td>
            <td>MAGREZA</td>
            <td>0</td>
          </tr>
          <tr class="normal">
            <td>ENTRE 18,5 E 24,9</td>
            <td>NORMAL</td>
            <td>0</td>
          </tr>
          <tr class="sobrepeso">
            <td>ENTRE 25,0 E 29,9</td>
            <td>SOBREPESO</td>
            <td>I</td>
          </tr>
          <tr class="obesidade">
            <td>ENTRE 30,0 E 39,9</td>
            <td>OBESIDADE</td>
            <td>II</td>
          </tr>
          <tr class="obesidadeGrave">
            <td>MAIOR QUE 40,0</td>
            <td>OBESIDADE GRAVE</td>
            <td>III</td>
          </tr>
        </tbody>
      </table>
    </div>
</template>

<script>
  export default {
    name: 'TabelaImc',
  }
</script>

<style>
  .table{
    margin-top: 6rem ;
    margin-bottom: 6rem ;
  }
  th {
    color: #4FEE9E;
  }
  table>:not(caption)>*>* {
    padding: 1rem 0.5rem !important;
    border-color: #300c72;
  }
  @media(max-width: 767px){
      p, tr, th{
        font-size: 13px;
      }
    }
</style>