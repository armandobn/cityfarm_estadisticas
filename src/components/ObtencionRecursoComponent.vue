<template>
  <label for=""><h5> {{props.titulo}} </h5></label><br>
  {{props.tituloProduccion}}
  <label for=""> <img :srcset="props.srcProduccion" style="width: 10%" alt="">: {{ props.produccion.toFixed(1) }} </label>
  {{props.tituloConsumo}}
  <label for=""> <img :srcset="props.srcConsume" style="width: 10%" alt="">: {{ props.consume.toFixed(1) }}</label>
  <div v-show="otroRercuso"> <img  :srcset="props.srcConsume2" style="width: 10%" alt="">: {{props.consume2.toFixed(1) }}</div>

</template>
<script setup>
import {defineProps,watch} from 'vue';

const props = defineProps({
  titulo: String,
  tituloProduccion: String,
  tituloConsumo: String,
  srcProduccion: String,
  srcConsume: String,
  produccion: Number,
  consume: Number,
  otroRercuso: Boolean,
  consume2: Number,
  srcConsume2: String,
})



</script>

<style>

</style>