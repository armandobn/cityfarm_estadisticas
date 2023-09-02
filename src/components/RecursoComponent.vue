<template>
  <label for=""> <img  :srcset="props.src"  v-bind:style="{
        // 'background-color':'#ccc' //kebab-case
        'width': props.width+'%'
    }" alt="" >: <label :style="{ color: props.cantidad < 0 ? 'red' : '',
              'fontWeight': 'bold'}">{{ props.cantidad.toFixed(1) }}</label>  </label><br>
</template>
<script setup>
import { defineProps } from 'vue';

const props = defineProps({
  src : String ,
  cantidad : Number,
  width: Number
})


</script>

<style>

</style>