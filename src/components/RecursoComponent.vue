<template>
  <label for=""> <img  :srcset="props.src"  v-bind:style="{
        // 'background-color':'#ccc' //kebab-case
        'width': props.width+'%'
    }" alt="" >: {{ props.cantidad }} </label><br>
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