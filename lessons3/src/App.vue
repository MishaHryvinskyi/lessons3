<template>

 <div class="main-block">
  <label for="modalTitle">
    <input id="modalTitle" type="text" v-model="modalTitle"/>
  </label>
  <label for="modalMessage">
    <input id="modalMessage" type="text" v-model="modalMessage"/>
  </label>
  
  <button @click="showModal">Show modal</button>
 </div>

 <ModalWindow v-if="isModalOpen" :modal-title="modalTitle" :modal-message="modalMessage" @close="closeModal"/>

</template>

<script>

import { defineComponent, ref } from 'vue';
import ModalWindow from '@/components/ModalWindow.vue';


export default defineComponent ({
  components: {ModalWindow},
  setup () {

    const isModalOpen = ref(false);
    const modalTitle = ref('');
    const modalMessage = ref('');
    
    function showModal() {
      isModalOpen.value = true;
      modalTitle.value = "";
      modalMessage.value = "";
    }

    function closeModal() {
      isModalOpen.value = false;
      modalTitle.value = "";
      modalMessage.value = "";
    }
    

    return {
      isModalOpen,
      modalTitle,
      modalMessage,
      showModal,
      closeModal
    }
  }
  
})
</script>

<style>

</style>
