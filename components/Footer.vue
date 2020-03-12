<template>
  <footer class="footer">
    <div class="footer__left">
      <ul>
        <li>
          <nuxt-link to="/" class="footer__link">
            Home
          </nuxt-link>
        </li>
        <li>
          <nuxt-link to="/service" class="footer__link">
            About
          </nuxt-link>
        </li>
        <li>
          <nuxt-link to="/products" class="footer__link">
            Products
          </nuxt-link>
        </li>
        <li>
          <nuxt-link to="/contacts" class="footer__link">
            Contact
          </nuxt-link>
        </li>
      </ul>
    </div>
    <div class="footer__center">
      <ul>
        <li>
          <a href="https://twitter.com/DesignerDepot" class="footer__link">
            Twitter
          </a>
        </li>
        <li><a href="https://www.facebook.com/Webd2d/" class="footer__link">Facebook</a></li>
        <li><a href="https://www.instagram.com/welovewebdesign/?hl=ru" class="footer__link">Instagram</a></li>
        <li><a href="https://www.youtube.com/user/agragregra" class="footer__link">YouTube</a></li>
      </ul>
    </div>
    <div class="footer__right">
      <ul>
        <li @click.prevent.stop="onClickSubscribe()" class="footer__link">
          Subscribe to Our Newsletter
        </li>
        <li @click.prevent.stop="onClickPolicy()" class="footer__link">
          Privacy Policy
        </li>
        <li @click.prevent.stop="onClickTerms()" class="footer__link">
          Terms & Conditions
        </li>
      </ul>
    </div>
    <div class="footer__copyright">
      <div class="footer__copyright--left">
        <p class="logo">
          Helloy
        </p>
      </div>
      <div class="footer__copyright--right">
        <p>&copy;   2020 helloy-web.com</p>
      </div>
    </div>
    <ModalFooter v-bind:show="showModal" :type="type" @close="onModalClose()" />
  </footer>
</template>

<script>

import ModalFooter from './modal-footer'
export default {
  name: 'Footer',
  components: { ModalFooter },
  data () {
    return {
      showModal: this.showModal,
      type: this.type
    }
  },
  methods: {
    onClickPolicy () {
      this.showModal = true
      this.type = 'policy'
    },
    onClickTerms () {
      this.showModal = true
      this.type = 'terms'
    },
    onClickSubscribe () {
      this.showModal = true
      this.type = 'subscribe'
    },
    onModalClose () {
      this.showModal = false
    }
  }
}
</script>

<style scoped>
footer {
  padding: 40px 30px;
  width: 100%;
  border-top: 1px solid #49464B;
  color: #49464B;
}

.footer__left,
.footer__center,
.footer__right {
  display: inline-block;
  width: 200px;
  vertical-align: top;
}
footer li {
  list-style-type: none;
  padding-bottom: 10px;
}
.footer__link {
  font-size: 18px;
  color: #49464B;
  font-weight: 500;
  text-decoration: none;
}
.footer__link:hover {
  color: rgba(217, 133, 42, 0.99);
}
.logo {
  font-family: 'Indie Flower';
  font-weight: 800;
  font-size: 26px;
  color: rgba(217, 133, 42, 0.99);
}

.footer__copyright {
  padding: 30px 40px 0;
  display: flex;
  justify-content: space-between;
}
.footer__copyright--left img {
  width: 100px;
}
.footer__copyright--right {
  padding-top: 12px;
  font-size: 16px;
}

</style>
