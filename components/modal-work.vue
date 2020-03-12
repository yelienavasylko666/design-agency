<template>
  <div v-bind:class="{ 'modal--show': show }" class="modal">
    <div class="modal__window">
      <div class="modal__heading">
        <h5>Art Of Coding</h5>
        <div @click.prevent.stop="onClose()" class="wrapper-btn-close">
          <button><fa icon="times" class="icon" /></button>
        </div>
      </div>
      <div class="modal__desc">
        Clean & Minimalistic Design
      </div>
      <div class="modal__content">
        <div class="modal__left">
          <span class="modal__info">Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.</span>
          <span class="modal__info">Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud.</span>
          <div class="modal__links">
            <a>Design, Coding, Portfolio</a>
          </div>
        </div>
        <div class="modal__right">
          <ul class="modal__list">
            <li>Project Leader: John Doe</li>
            <li>Designer: Alisa Keys</li>
            <li>Developer: Mark Doe</li>
            <li>Customer: Keenthemes</li>
          </ul>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ModalWork',
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
    width: 800px;
    height: auto;
    background-color: white;
  }
  .modal--show {
    display: block;

  }
  h5 {
    cursor: pointer;
    font-weight: 700;
    color: #515769;
    margin-bottom: 15px;
  }
  .modal__heading {
    align-items: center;
    padding: 20px 40px 0;
    display: flex;
    justify-content: space-between;
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
  .modal__desc {
    padding: 0 40px;
    font-size: 14px;
    color: #bfc1c7;
  }
  .modal__content {
    padding: 20px 40px;
    display: block;
    width: 100%;
  }

  .modal__left {
    width: 60%;
    display: inline-block;
    margin-top: 10px;
    border-right: 1px solid #a6a7aa;
    padding: 10px 20px 0 0;
  }
  .modal__info {
    font-size: 15px;
    color: #a6a7aa;
    margin-bottom: 15px;
    font-weight: 300;
  }
  .modal__links {
    font-size: 12px;
    cursor: pointer;
    color: #727a94;
    font-weight: 400;
  }
  .modal__links:hover {
    color: #282828;
  }
  .modal__right {
    margin-top: 10px;
    padding-top: 10px;
    width: 35%;
    display: inline-block;
    vertical-align: top;
  }
  .modal__right li {
    list-style-type: none;
    color: #a6a7aa;
    font-size: 15px;
    padding: 0 10px 10px 0;
    font-weight: 300;
  }
</style>
