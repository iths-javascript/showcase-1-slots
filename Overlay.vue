<template>
  <div class="overlay" :class="{show}">
    <div class="fade-layer" @click="$emit('close')"></div>
    <div class="content">
      <slot>This is the default content</slot>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    show: Boolean
  }
}
</script>

<style>
.overlay{
  opacity: 0;
  pointer-events: none;
  transition: opacity 0.25s;
}
.overlay.show{
  opacity: 1;
  pointer-events: all;
}

.fade-layer{
  position: fixed;
  left: 0; bottom: 0; right: 0; top: 0;
  background-color: grey;
}

.content{
  position: fixed;
  left: 50%;
  top: 50%;
  transform:  translate(-50%,-50%) scale(0);
  transition: transform 0.25s;
}

.overlay.show .content{
  transform:  translate(-50%,-50%) scale(1);
}


</style>