<template>
    <div>
        <div>
            <h1 class="fs-2 text-center fw-bold">Calculadora IMC</h1>

            <div class="mt-5 mb-5">
                <h2 class="fs-4 fw-semibold">O que é IMC?</h2>
                <p class="mt-3">O Índice de Massa Corporal, conhecido pela sigla IMC, é um cálculo simples que permite medir se alguém está ou não com o peso ideal. Ele aponta se o peso está adequado ou se está abaixo ou acima do peso.</p>
                <p>Esta técnica é medida por meio da fórmula: IMC = Peso (Kg)/ (Altura(m))². Neste cálculo, leva-se em conta o peso e a altura do indivíduo, dividindo o peso pela altura elevada ao quadrado.</p>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'SobreImc',
}
</script>

<style>

     @media(max-width: 767px){
      th, tr{
        font-size: 14px;
      }
    }
    
</style>