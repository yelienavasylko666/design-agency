<template>
  <div v-bind:class="{ 'modal--show': show }" class="modal">
    <div class="modal__window">
      <div class=" modal__heading">
        <span class="modal__text">Please leave your details. <br> We will contact you soon.</span>
        <div @click.prevent.stop="onClose()" class="modal__wrapper-btn-close">
          <button><fa icon="times" class="icon" /></button>
        </div>
      </div>
      <label><input v-bind:class="{ 'error' : !contacts.name.length }" v-model="contacts.name" type="text" placeholder="Enter Your Name"></label>
      <label><input v-bind:class="{ 'error' : !contacts.mail.length }" v-model="contacts.mail" type="text" placeholder="Enter Your E-mail"></label>
      <button @click.prevent.stop="onSubmit()" class="btn">
        Send!
      </button>
    </div>
  </div>
</template>
<script>
export default {
  name: 'ModalClearenceOrder',
  props: {
    show: Boolean
  },
  data: () => ({
    contacts: {
      name: '',
      mail: ''
    }
  }),
  methods: {
    onSubmit () {
      if (this.contacts.phone.length && this.contacts.mail.length) {
        this.onClose()
      }
    },
    onClose () {
      this.$emit('close')
      this.contacts.mail = ''
      this.contacts.name = ''
    }
  }
}
</script>

<style scoped>
  .modal {
    position: fixed;
    width: 100vw;
    height: 100vh;
    background-color: rgba(78, 85, 91, 0.71);
  }
  .modal--show {
    display: block;
  }
  .error {
    border: 1px solid red;
  }
  .modal__window {
    background-color: white;
    position: fixed;
    width: 500px;
    height: auto;
    left: 50%;
    top: 50%;
    transform: translate(-50%, -50%);
  }
  .modal__heading {
    display: flex;
    justify-content: space-between;
    padding: 15px 30px 0;
  }
  .modal__text {
    font-size: 16px;
    font-weight: 300;
    color: #81848f;
  }
  .modal button {
    border: none;
    outline: none;
  }
  .icon {
    font-size: 15px;
    color: #c5c6cb;
    transition: 0.3s ease-out;
  }
  .icon:hover {
    color: rgba(27,200,217,0.99);
    transform: scale(1.3);
  }
  label {
    margin: 10px 30px;
  }
  input {
    display: block;
    width: 100%;
    padding: 5px;
    outline: none;
  }
  input:focus {
    border: 2px solid rgba(27,200,217,0.99);
  }
  input::placeholder {
    color: rgba(110, 120, 127, 0.5);
    font-size: 14px;
  }
  .btn {
    border: none;
    color: white;
    width: 100px;
    font-size: 16px;
    outline: none;
    background-color: rgba(27,200,217,0.99);
    display: block;
    margin: 30px auto;
    text-align: center;
  }
</style>
