<template>
  <label for=""> <img  :srcset="props.src"  style="width: 10%" alt="" >: {{ props.cantidad }} </label><br>
</template>
<script setup>
import { defineProps } from 'vue';

const props = defineProps({
  src : String ,
  cantidad : Number
})


</script>

<style>

</style>