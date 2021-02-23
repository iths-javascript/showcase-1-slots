<template>
  <div class="wrapper">
    <button @click="showConfirmDialog = !showConfirmDialog">Show Confirm</button>
    <button @click="showDialog = !showDialog">Show Dialog</button>    
    
    <Overlay @close="showConfirmDialog = false" :show="showConfirmDialog">
      <ConfirmDialog @close="showConfirmDialog = false"/>
    </Overlay>
    
    <Overlay @close="showDialog = false" :show="showDialog">
      <Dialog />
    </Overlay>
    
  </div>
</template>

<script>
import ConfirmDialog from './ConfirmDialog'
import Overlay from './Overlay'
import Dialog from './Dialog'
export default {
  components: {Overlay, Dialog, ConfirmDialog},

  data(){return {
    showConfirmDialog: false,
    showDialog: false
  }}
}
</script>

<style>

</style>