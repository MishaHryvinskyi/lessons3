<template>
  
  <div class="modal">
    <div class="content">
      <h3>{{ modalTitle }}</h3>
      <p>{{ modalMessage }}</p>
      <button @click="closeModal">Close</button>
    </div>
  </div>

</template>

<script>
import {defineComponent} from 'vue';

export default defineComponent({
  props: {
    modalMessage: String,
    modalTitle: String
  },

  emits: ['close'],

  setup (props, {emit}) {

    function closeModal() {
      emit('close')
    }

    return {
      closeModal
    }
  }
})
</script>

<style scoped>

</style>
