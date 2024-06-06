<template>

  <input type="number" v-model="counter">
  <CounterVue :counter="counter"/>

</template>

<script>

import { defineComponent, ref } from 'vue';
import  CounterVue  from '@/components/CounterVue.vue';


export default defineComponent ({
  components: { CounterVue },
  setup () {

    const counter = ref(0);


    return {
      counter,
    }
  }
  
})
</script>

<style>

</style>
