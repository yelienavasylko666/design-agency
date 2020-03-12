<template>
  <header class="Header">
    <div class="logo">
      <nuxt-link to="/" class="logo-link">
        <div class="logo">
          Helloy <fa icon="hand-peace" class="icon-colorized" />
        </div>
      </nuxt-link>
      <div>
        <fa v-if="!menuOpen" @click.prevent.stop="menuOpen = true" class="icon-menu" icon="bars" />
        <fa v-if="menuOpen" @click.prevent.stop="menuOpen = false" class="icon-close-menu" icon="times" />
      </div>
    </div>
    <div v-bind:class="{ 'menu--active': menuOpen}" class="menu">
      <ul class="nav">
        <li class="nav__item">
          <nuxt-link to="/" class="nav__link">
            HOME
          </nuxt-link>
        </li>
        <li class="nav__item">
          <nuxt-link to="/products" class="nav__link">
            PRODUCTS
          </nuxt-link>
        </li>
        <li class="nav__item">
          <nuxt-link to="/service" class="nav__link">
            SERVICE
          </nuxt-link>
        </li>
        <li class="nav__item">
          <nuxt-link to="/pricing" class="nav__link">
            PRICING
          </nuxt-link>
        </li>
        <li class="nav__item">
          <nuxt-link to="/contacts" class="nav__link">
            CONTACTS
          </nuxt-link>
        </li>
      </ul>
    </div>
  </header>
</template>

<script>
export default {
  name: 'Header',
  props: {
    menuOpen: Boolean,
    menuClose: Boolean
  }
}

</script>

<style scoped>
header {
  width: 100%;
  border-bottom: 1px solid rgba(96, 96, 98, 0.85);
  padding: 30px 100px;
  display: flex;
  justify-content: space-between;
  position: fixed;
  z-index: 10;
  top: 0;
  background-color: white;
}
  .logo {
    font-weight: 800;
    font-size: 36px;
    color: rgba(217, 133, 42, 0.99);
  }
  .icon-menu {
    display: none;
  }
.nav {
list-style-type: none;
  padding-top: 10px;
}
.nav__item {
  float: right;
  font-size: 16px;
  font-weight: 500;
}
.nav__link,
.logo-link {
  text-decoration: none;
}
  .nav__link {
    position: relative;
    display: block;
    padding: 8px 16px;
    color: rgba(96, 96, 98, 0.91);
    font-weight: bolder;
  }
.nav__link:hover {
  color: rgba(217, 133, 42, 0.99);
  transition: 0.5s ease-out;
}
.nav__link:before {
  content: "";
  display: block;
  opacity: 0;
  position: absolute;
  transition: opacity 0.5s ease-out;
  right: calc(100% - 12px);
  top: calc(50% - 2px);
  width: 10px;
  height: 2px;
  background-color: rgba(217, 133, 42, 0.99);
}
.nav__link.nuxt-link-exact-active:before {
  opacity: 1;
}
  @media screen and (max-width: 1024px){
    header {
      padding: 30px;
    }
  }
  @media screen and (max-width: 768px){
    .logo {
      font-size: 20px;
      width: 100%;
      display: flex;
      justify-content: space-between;
    }
    .icon-menu,
    .icon-close-menu {
      display: block;
      font-size: 30px;
      color: rgba(217, 133, 42, 0.99)
    }
    .menu {
      display: none;
      justify-content: flex-end;
    }
    .nav {
      margin-top: 20px;
      width: 94px;
      display: flex;
      flex-direction: column;
      height: 100vh;
    }
    .nav__item {
      text-align: right;
    }
    .menu--active {
      display: flex;
    }
    header {
      padding: 30px 60px;
      flex-direction: column;
    }
}
</style>
