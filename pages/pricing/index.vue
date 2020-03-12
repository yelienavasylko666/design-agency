<template>
  <div class="shop">
    <h2 class="text-center">Here you can choose proposition for you :)</h2>
    <div class="shop__items align-items-center">
      <div class="shop__item">
        <fa icon="dice-one" class="icon" />
        <h5>Starter Kit <br> $19 per mo.</h5>
        <div class="item__desc">
          This package will be useful for beginning designers.
        </div>
        <ul>
          <li><fa icon="minus" class="icon-small" /> Basic Features</li>
          <li><fa icon="minus" class="icon-small" /> Up to 5 projects</li>
          <li><fa icon="minus" class="icon-small" /> 5 on-line lessons and support from professional designer during 1st project</li>
          <li><fa icon="minus" class="icon-small" /> 1 User</li>
        </ul>
        <nuxt-link to="pricing/details/kit">
          <button>
            CHOOSE
          </button>
        </nuxt-link>
      </div>

      <div class="shop__item">
        <fa icon="dice-two" class="icon" />
        <h5>Professional <br> $49 per mo.</h5>
        <div class="item__desc">
          If you want to grow up in this direction you have to try this proposition.
        </div>
        <ul>
          <li><fa icon="minus" class="icon-small" /> Basic Features</li>
          <li><fa icon="minus" class="icon-small" /> Up to 20 projects</li>
          <li><fa icon="minus" class="icon-small" /> 20 on-line lessons and participation in weekly conferences</li>
          <li><fa icon="minus" class="icon-small" /> 3 Users</li>
        </ul>
        <nuxt-link to="pricing/details/profi">
          <button>
            CHOOSE
          </button>
        </nuxt-link>
      </div>

      <div class="shop__item">
        <fa icon="dice-three" class="icon" />
        <h5>Advanced <br> $99 per mo.</h5>
        <div class="item__desc">
          It`s a good offer for companies or professional designers.
        </div>
        <ul>
          <li><fa icon="minus" class="icon-small" /> Extended Features</li>
          <li><fa icon="minus" class="icon-small" /> Unlimited projects</li>
          <li><fa icon="minus" class="icon-small" /> Access to all on-line lessons, conferences and support for companies</li>
          <li><fa icon="minus" class="icon-small" /> Unlimited users</li>
        </ul>
        <nuxt-link to="pricing/details/advanced">
          <button>
            CHOOSE
          </button>
        </nuxt-link>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Pricing'
}
</script>

<style scoped>
.shop {
  margin: 0;
  padding: 0;
}
h2 {
  margin: 150px 0 40px;
  color: #7F828B;
}
.shop__items {
  padding: 100px;
  width: 100%;
  background-color: #fafafa;
}
.shop__item {
  cursor: pointer;
  display: inline-block;
  width: 32%;
  background-color: white;
  transition: 0.3s ease-out;
  padding: 70px 45px;
}
.shop__item:hover {
  transform: scale(1.05);
  background-color: rgba(240, 147, 46, 0.28);
}
.shop__item:nth-child(1),
.shop__item:nth-child(2) {
  margin-right: 1%;
}
  .icon {
    font-size: 35px;
    color: #a6a7aa;
    margin-bottom: 30px;
  }
h3,
h5 {
  font-weight: 700;
  color: #515769;
  margin-bottom: 15px;
}
.item__desc {
  font-family: 'Indie Flower';
font-size: 18px;
font-weight: 300;
color: #97989a;
margin-bottom: 30px;
}
ul {
  margin: 0;
  padding: 0;
}
ul li:last-child {
  margin-bottom: 40px;
}
li {
  list-style-type: none;
  font-size: 16px;
  color: #81848f;
  margin-bottom: 15px;
}
li .icon-small {
  font-size: 12px;
  font-weight: 200;
  color: rgba(217, 133, 42, 0.99);
  margin-right: 5px;
}

button {
  font-family: 'Indie Flower';
  outline: none;
  border: none;
  background-color: #d1d2d6;
  font-size: 13px;
  font-weight: 300;
  padding: 15px 35px;
}
a {
  color: #515769;
  text-decoration: none;
}
button:hover {
  background-color: rgba(217, 133, 42, 0.99);
  transition: 0.5s ease-out;
  color: white;
}
@media screen and (max-width: 1024px){
  .shop__items {
    padding: 40px;
  }
  .shop__item {
    width: 80%;
    padding: 40px;
    display: block;
    margin-bottom: 20px;
  }
}
</style>
