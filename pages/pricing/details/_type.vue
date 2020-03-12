<template>
  <div class="wrapper">
    <div v-if="type === 'kit'" class="kit">
      <div class="shop__item">
        <fa icon="dice-one" class="icon" />
        <h3>Starter Kit <br> $19 per mo.</h3>
        <div class="item__desc">
          This package will be useful for beginning designers.
        </div>
        <ul>
          <li><fa icon="minus" class="icon-small" /> Basic Features</li>
          <li><fa icon="minus" class="icon-small" /> Up to 5 products</li>
          <li><fa icon="minus" class="icon-small" /> 50 Users Panels</li>
          <li><fa icon="minus" class="icon-small" /> 1 User</li>
        </ul>
      </div>
      <div class="text-center">
        OR
      </div>
      <div class="options">
        <h3>You can choose more :</h3>
        <label><input v-model="sum" type="radio" name="kit-option" class="option" value="99">Unlock for 6 mo. - $99<br></label>
        <label><input v-model="sum" type="radio" name="kit-option" class="option" value="189">Unlock for 1 yr. - $189<br></label>
        <label><input v-model="sum" type="radio" name="kit-option" class="option" value="999">Unlock forever - $999<br></label>
        <label><input v-model="sum" type="radio" name="kit-option" class="option" value="19">I don`t want more<br></label>
      </div>
    </div>
    <div v-if="type === 'profi'" class="profi">
      <div class="shop__item">
        <fa icon="dice-two" class="icon" />
        <h3>Professional <br> $49 per mo.</h3>
        <div class="item__desc">
          If you want to grow up in this direction you have to try this proposition.
        </div>
        <ul>
          <li><fa icon="minus" class="icon-small" /> Basic Features</li>
          <li><fa icon="minus" class="icon-small" /> Up to 20 products</li>
          <li><fa icon="minus" class="icon-small" /> 20 on-line lessons and participation in weekly conferences</li>
          <li><fa icon="minus" class="icon-small" /> 3 Users</li>
        </ul>
      </div>
      <div class="text-center">
        OR
      </div>
      <div class="options">
        <h3>You can choose more : </h3>
        <label><input v-model="sum" type="radio" name="profi-option" class="option" value="199">Unlock for 6 mo. - $199<br></label>
        <label><input v-model="sum" type="radio" name="profi-option" class="option" value="449">Unlock for 1 yr. - $449<br></label>
        <label><input v-model="sum" type="radio" name="profi-option" class="option" value="1499">Unlock forever - $1499<br></label>
        <label><input v-model="sum" type="radio" name="profi-option" class="option" value="49">I don`t want more<br></label>
      </div>
    </div>
    <div v-if="type === 'advanced'" class="advanced">
      <div class="shop__item">
        <fa icon="dice-three" class="icon" />
        <h3>Advanced <br> $99 per mo.</h3>
        <div class="item__desc">
          It`s a good offer for companies or professional designers.
        </div>
        <ul>
          <li><fa icon="minus" class="icon-small" /> Extended Features</li>
          <li><fa icon="minus" class="icon-small" /> Unlimited projects</li>
          <li><fa icon="minus" class="icon-small" /> Access to all on-line lessons, conferences and support for companies</li>
          <li><fa icon="minus" class="icon-small" /> Unlimited users</li>
        </ul>
      </div>
      <div class="text-center">
        OR
      </div>
      <div class="options">
        <h3>You can choose more : </h3>
        <label><input v-model="sum" type="radio" name="adv-option" class="option" value="599">Unlock for 6 mo. - $599<br></label>
        <label><input v-model="sum" type="radio" name="adv-option" class="option" value="849">Unlock for 1 yr. - $849<br></label>
        <label><input v-model="sum" type="radio" name="adv-option" class="option" value="2999">Unlock forever - $2999<br></label>
        <label><input v-model="sum" type="radio" name="adv-option" class="option" value="99">I don`t want more<br></label>
      </div>
    </div>
    <div class="total">
      To Pay : {{ "$" + sum }}
    </div>
    <button @click.prevent.stop="onClick()" class="modal-open btn">
      BUY!
    </button>
    <ModalClearenceOrder v-bind:show="showModal" @close="onModalClose()" />
  </div>
</template>
<script>
import ModalClearenceOrder from '../../../components/modal-clearence-order'
export default {
  name: 'Details',
  components: { ModalClearenceOrder },
  props: {
    showModal: {
      type: Boolean,
      default: () => false
    }
  },
  data: () => ({
    type: '',
    sum: 99
  }),

  mounted () {
    this.type = this.$route.params.type
    if (this.type === 'profi') {
      this.sum = 199
    } else if (this.type === 'advanced') {
      this.sum = 599
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

<style scoped>
  .wrapper {
    margin: 30px 100px;
  }
  .shop__item {
    cursor: pointer;
    display: inline-block;
    width: 32%;
    background-color: white;
    transition: 0.3s ease-out;
    padding: 70px 45px;
  }
  .icon {
    font-size: 35px;
    color: #a6a7aa;
    margin-bottom: 30px;
  }
  h3 {
    font-weight: 700;
    color: #515769;
    margin-bottom: 15px;
  }
  .item__desc {
    font-size: 20px;
    font-weight: 300;
    color: #97989a;
    margin-bottom: 30px;
  }
  ul {
    margin: 0;
    padding: 0;
  }
  li {
    list-style-type: none;
    font-size: 18px;
    color: #81848f;
    margin-bottom: 15px;
  }
  li .icon-small {
    font-size: 12px;
    font-weight: 200;
    color: rgba(217, 133, 42, 0.99);
    margin-right: 5px;
  }
  .text-center,
  .options{
    display: inline-block;
    width: 30%;
  }
  .text-center {
    font-size: 40px;
    color: #515769;
    font-weight: 600;
    vertical-align: top;
    padding-top: 200px;
  }
  .options {
    vertical-align: top;
    padding-top: 136px;
    text-align: right;
  }
  label {
    display: block;
    font-size: 18px;
    color: #81848f;
    margin: 30px 0;
    transition: 0.5s ease-out;
  }
  label:hover {
    color: rgba(217, 133, 42, 0.99);
    transform: scale(1.05);
    cursor: pointer;
  }
  input {
    margin-right: 10px;
    font-size: 20px;
  }
  .total {
    text-align: center;
    font-size: 26px;
    color: #515769;
    margin: 20px 50px 20px;
  }
  .btn {
    border: 1px solid #5a6268;
    color: #5a6268;
    width: 250px;
    height: 50px;
    font-size: 20px;
    outline: none;
    background-color: #d1d2d6;
    transition: 0.5s ease-out;
    display: block;
    margin: 0 auto;
  }
  .btn:hover {

    border: none;
    background-color: rgba(217, 133, 42, 0.99);
    color: white;
  }
  @media screen and (max-width: 1024px) {
    .wrapper {
      margin: 30px;
    }
    .shop__item {
      padding: 136px 0 0;
    }
    .options {
      padding-top: 150px;
    }
  }
  @media screen and (max-width: 768px) {
    .wrapper {
      margin: 30px;
    }
    .shop__item {
      padding: 136px 0 0;
    }
  }
</style>
