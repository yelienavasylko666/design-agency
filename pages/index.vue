<template>
  <div class="home-page">
    <img src="../components/img/home.jpg" class="home-image" alt="Main Image">
    <div class="home-content">
      <h1 class="text-center">
        Products Agency For Designers.
      </h1>
      <span class="text-center main-text">It`s Easier Than You Think.
      </span>
      <button @click.prevent.stop="onClick()" class="media-video modal-open">
        WATCH INTRO VIDEO ABOUT US
      </button>
    </div>
    <ModalHome v-bind:show="showModal" @close="onModalClose()" />
  </div>
</template>

<script>

import ModalHome from '../components/modal-home'
export default {
  name: 'Default',
  components: { ModalHome },
  props: {
    showModal: {
      type: Boolean,
      default: () => false
    }
  },
  methods: {
    onClick () {
      this.showModal = true
    },
    onModalClose () {
      this.showModal = false
    }
  }
}
</script>

<style>
.home-page {
  position: relative;
}
.home-image {
  height: 100%;
  width: 100%;
  margin-top: -96px;
}
.mask {
  position: absolute;
  width: 100%;
  height: 100%;
  background-color: rgba(81,87,105, 0.4);
  left: 0;
  top: 0;
}
.home-content {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}
h1 {
  font-family: 'Indie Flower';
  font-size: 55px;
  font-weight: bold;
  color: rgba(245, 150, 48, 0.99);
}
span {
  font-family: 'Indie Flower';
  display: block;
  font-size: 25px;
  font-weight: 500;
  color: white;
  margin-bottom: 20px;
}
.media-video {
  text-decoration: none;
  border: none;
  outline: none !important;
  padding: 10px;
  font-size: 14px;
  color: #515769;
  display: block;
  margin: 0 auto;
}
.media-video:hover {
  transition: all 0.5s ease-out;
  background-color: rgba(217, 133, 42, 0.99);
  color: white;
}
@media screen and (max-width: 1024px) {
  .home-image {
  margin-top: -50px;
  }
  h1 {
    font-size: 45px;
  }
  .main-text {
    font-size: 22px;
    margin-bottom: 40px;
  }
  .media-video {
margin-bottom: 10px;
  }
}
@media screen and (max-width: 768px) {
  h1 {
    font-size: 40px;
  }
  .main-text {
    font-size: 18px;
  }
}
</style>
