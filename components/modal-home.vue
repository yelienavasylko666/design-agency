<template>
  <div v-if="show" @click.prevent.stop="onClose()" class="modal">
    <div class="modal__window">
      <iframe
        width="966"
        height="605"
        src="https://www.youtube.com/embed/bmixiVwtDso"
        frameborder="0"
        allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture"
        allowfullscreen
      />
    </div>
  </div>
</template>

<script>
export default {
  name: 'ModalHome',
  props: {
    show: Boolean
  },
  methods: {
    onClose () {
      this.$emit('close')
    }
  }

}
</script>

<style scoped>
.modal {
  display: block;
  position: fixed;
  width: 100vw;
  height: 100vh;
  background-color: rgba(78, 85, 91, 0.71);
}

.modal__window {
  position: fixed;
  left: 50%;
  top: 50%;
  transform: translate(-50%, -50%);
}

</style>
