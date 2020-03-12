<template>
  <section class="products">
    <h3 class="products__heading text-center">
      Latest Products
    </h3>
    <span class="products__desc text-center">Here you can see products which our users have done during the past week.</span>
    <div class="products__wrapper">
      <div class="products__item">
        <div class="work-wrapper">
          <img src="../../components/img/products/w-1.png" alt="product-image" class="product__img">
        </div>
        <h5 class="product__name">
          Alice,
          <br>
          experience 4 month,
          <br>
          freelancer.
        </h5>
        <div class="product__desc">
          This is the 8th product of this girl.
          <br>
          She is our user during 2 mo. already.
        </div>
      </div>
      <div class="products__item">
        <div class="work-wrapper">
          <img src="../../components/img/products/w-2.png" alt="product-image" class="product__img">
        </div>
        <h5 class="product__name">
          Company 'IDEA Net Work',
          <br>
          over 50 web-designers.
        </h5>
        <div class="product__desc">
          This company works with us since our foundation.
          <br>
          Their workers realised over 200 project with us.
          <br>
          Our employees graduated more than 20 beginners web-designers for IDEA Net Work.
          <br>
          They update our weekly "Latest Products" as usual.
        </div>
      </div>
      <div class="products__item">
        <div class="work-wrapper">
          <img src="../../components/img/products/w-3.png" alt="product-image" class="product__img">
        </div>
        <h5 class="product__name">
          Start-up project 'Hot designers'
        </h5>
        <div class="product__desc">
          This guys joined us 2 weeks ago and already send us their 1st work.
        </div>
      </div>
    </div>
    <div class="wrapper-clients">
      <h3 class="text-center">
        Our clients :
      </h3>
      <div class="clients">
        <div class="client">
          <a href="https://discordapp.com/" class="client__link" target="_blank"><img src="../../components/img/clients/01.png" alt="CLIENT" class="client__logo"></a>
        </div>
        <div class="client">
          <a href="https://www.netflix.com/" class="client__link" target="_blank"><img src="../../components/img/clients/02.png" alt="CLIENT" class="client__logo"></a>
        </div>
        <div class="client">
          <a href="https://www.marriott.com/" class="client__link" target="_blank"><img src="../../components/img/clients/03.png" alt="CLIENT" class="client__logo"></a>
        </div>
        <div class="client">
          <a href="https://www.dyson.com/" class="client__link" target="_blank"><img src="../../components/img/clients/04.png" alt="CLIENT" class="client__logo"></a>
        </div>
        <div class="client">
          <a href="https://www.airbnb.com" class="client__link" target="_blank"><img src="../../components/img/clients/05.png" alt="CLIENT" class="client__logo"></a>
        </div>
        <div class="client">
          <a href="https://www.theheinekencompany.com/" class="client__link" target="_blank"><img src="../../components/img/clients/06.png" alt="CLIENT" class="client__logo"></a>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'Products'
}
</script>

<style scoped>

.products__heading {
  margin: 250px 100px 30px;
  font-weight: 700;
  color: #515769;
}
  .products__desc {
    width: 35%;
    color: #a6a7aa;
    margin: 0 auto;
    text-align: center;
    font-size: 18px;
    font-weight: bold;
  }
.products__wrapper {
  display: flex;
  margin: 60px 100px 0;
}
.products__item {
  display: inline-block;
  width: 30%;
  justify-content: space-between;
}
.products__item:nth-child(1),
.products__item:nth-child(2) {
  margin-right: 5%;
}
.work-wrapper {
  width: 350px;
  height: auto;
}
.product__img {
  width: 100%;
  height: auto;
  margin-bottom: 25px;
}
h5 {
  font-weight: 500;
  color: #515769;
  }
h5:first-child {
  margin-top: 19px;
}
h5:last-child {
  margin-top: 35px;
}
.product__desc {
  color:  #a6a7aa;
  font-weight: 200;
  font-size: 18px;
  margin-bottom: 25px;

}
h3 {
  margin-top: 150px;
  font-weight: 600;
  color: #515769;
}
.clients {
  display: flex;
  justify-content: space-between;
  margin: 40px 100px;
}
.client__logo {
  width: 150px;
}

@media screen and (max-width: 1024px){
  .products__wrapper {
    margin: 60px ;
  }
.work-wrapper {
  width: 100%;
}
.client {
  width: 15%;
}
.client__logo {
  width: 50%;
  display: block;
  margin: 0 auto;
}
}
</style>
