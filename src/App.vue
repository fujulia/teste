<script setup>
import { ref } from 'vue';
const dados = ref({
  cons_medio_m: 291, //kWh mes
  eficiencia: 0.75, //
  p_placa: 0.355, //Wh 
  irradiacao: 3.64,
})

const cons_medio_d = ref(dados.value.cons_medio_m / 30) // kWh dia
const p_sistema = ref( cons_medio_d.value / (dados.value.eficiencia * dados.value.irradiacao)) // kWp
console.log(p_sistema.value.toFixed(2)) // mostrar potencia sistema
const qt_placa = ref( p_sistema.value/dados.value.p_placa ) // placas
console.log(Math.ceil(qt_placa.value)) // mostrar quantidade de placas
const valor_energia = dados.value.cons_medio_m * 0.5
console.log(Math.ceil(valor_energia)) // mostrar quantidade de placas
const energia_gerada = (dados.value.p_placa * 0.75)* dados.value.irradiacao
console.log(Math.ceil(energia_gerada * 30)) // mostrar quantidade de placas
const valor_desconto = (energia_gerada *30)*0.5
console.log(Math.ceil(valor_desconto))

</script>

<template>

</template>

<style scoped>

</style>
