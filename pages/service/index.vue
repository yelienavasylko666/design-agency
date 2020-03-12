<template>
  <div class="service-wrapper">
    <div v-for="item in data" class="service__item">
      <fa :icon="item.icon" class="service__icon" />
      <h5>{{ item.heading }}</h5>
      <span>{{ item.text }}</span>
    </div>
  </div>
</template>

<script>
import axios from 'axios'
export default {
  name: 'Service',
  async asyncData ({ req, params, store }) {
    const data = await axios.get('http://localhost:3000/data/data.json').then(res => res.data)
    return { data }
  }
}
</script>

<style scoped>
.service-wrapper {
  background-color: #fafafa;
  padding: 55px 15%;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
}

.service__item {
  background-color: white;
  height: 300px;
  flex-basis: 33%;
  padding: 50px;
  margin-bottom: 5px;
}

.service__icon {
  font-size: 20px;
  color: #a6a7aa;
  margin-bottom: 15px;
  transition: height 0.2s ease-out;
}
h5 {
  cursor: pointer;
  font-weight: 700;
  color: #515769;
  margin-bottom: 15px;
}
span {
  font-size: 18px;
  font-weight: 200;
  color: #a6a7aa;
}
.service__item:hover {
  background-color: rgba(217, 133, 42, 0.99);
}
.service__item:hover .service__icon {
  height: 0;
  overflow: hidden;
}
.service__item:hover h5,
.service__item:hover span {
  color: #fff;
}
.service__item--img {
  background-image: url("../../components/img/1920x1080/02.jpg");
  width: 100%;
  height: 400px;
}
@media screen and (max-width: 1024px){
  .service__item {
    flex-basis: 49.5%;
    height: 280px;
  }
}
@media screen and (max-width: 768px) {
  .service-wrapper {
    justify-content: center;
  }
  .service__item {
    flex-basis: 60%;
    height: 300px;
  }
}
</style>
