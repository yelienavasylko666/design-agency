<template>
  <div class="text-center contacts">
    <h2>
      If You have questions - you can ask them anytime :)
    </h2>
    <div class="contacts__us">
      <div><span class="colorized">Our Telephone :</span>  +38(099)999-99-09</div>
      <div><span class="colorized">Our Skype :</span>  helloy_web_20</div>
      <div><span class="colorized">Our E-mail:</span>  helloy-web.agency@gmail.com</div>
    </div>
    <div class="map">
      <h3>
        Our offices you can find on the map.
      </h3>
      <iframe
        src="https://www.google.com/maps/embed?pb=!1m12!1m8!1m3!1d328306.47126241546!2d36.28582500000001!3d49.994591!3m2!1i1024!2i768!4f13.1!2m1!1z0J3QsNC30LLQsNC90LjQtQ!5e0!3m2!1sen!2sus!4v1581532902080!5m2!1sen!2sus"
        frameborder="0"
        style="border:0;"
        allowfullscreen=""
      />
    </div>
  </div>
</template>

<script>
// import Details from '../pricing/details/_type'
export default {
  name: 'Contacts'
  // components: { Details }
}
</script>

<style scoped>
  h2 {
    margin-top: 160px;
    color: #515769;

  }
  .contacts__us {
    margin-bottom: 20px;
    font-size: 16px;
    font-weight: 400;
    color: #727a94;
  }
  .colorized {
    color: rgba(217, 133, 42, 0.99);
  }
  .map {
    width: 100%;
    height: 500px;
    position: relative;
    overflow:hidden;
  }

  .map iframe {
    width: 100%;
    height: 100%;
  }
</style>
