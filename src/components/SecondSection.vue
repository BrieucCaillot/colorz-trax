<template>
  <section class="section__second">
    <div class="swiper-container">
      <div class="swiper-wrapper">
        <a href="javascript:void(0)" v-for="event in event_list"
           class="swiper-slide section__second__elem">
          <div class="section__second__elem__top">
            <div class="border-top"></div>
            <div class="columns">
              <div class="column">
                <div class="level">
                  <h2 class="section__second__elem__top__title">{{ event.name }}</h2>
                </div>
                <div class="level is-mobile">
                  <div class="level-left">
                    <div class="section__second__elem__top__location">
                      <span>{{ event.location  }}</span>
                    </div>
                    <div class="section__second__elem__top__time">
                      <div class="icon icon__time icon__time__white"></div>
                      <span>{{ event.time }}</span>
                    </div>
                  </div>
                </div>
              </div>
            </div>
            <div class="columns">
              <div class="column">
                <div class="section__second__elem__bottom"
                     :style="{ 'background-image': `url(${require('@/assets/img/'+ event.image +'')})` }">
                </div>
              </div>
            </div>
          </div>
        </a>
      </div>
    </div>
  </section>
</template>

<script>

  import Swiper from 'swiper';
  import 'swiper/dist/css/swiper.min.css';

  export default {
    name: "SecondSection",
    mounted() {
      new Swiper('.swiper-container', {
        direction: 'horizontal',
        loop: true,
        keyboard: true,
        freeMode: true,
        grabCursor: true,
        spaceBetween: 60,
        slidesOffsetBefore: 60,
        slidesPerView: 4.5,
        // Responsive breakpoints
        breakpoints: {
          500: {
            slidesOffsetBefore: 35,
            slidesPerView: 1.4,
            spaceBetween: 35,
          },
          1024: {
            slidesPerView: 2.6,
          },
          1216: {
            slidesPerView: 3.6,
          },
          1480: {
            slidesPerView: 3.5,
          },
        }
      });
    },
    computed: {
      event_list() {
        return [
          {
            "name": "Madben Fréquence(s) live",
            "location": "Debonair - Paris",
            "time": "23h30",
            "image": "swiper-1.png"
          },
          {
            "name": "JJ & Chosen Family",
            "location": "Debonair - Paris",
            "time": "23h30",
            "image": "swiper-2.png"
          },
          {
            "name": "Garosnow 7ème Edition",
            "location": "La Java - Paris",
            "time": "23h30",
            "image": "swiper-3.png"
          },
          {
            "name": "Garosnow 8ème Edition",
            "location": "La Java - Paris",
            "time": "23h30",
            "image": "swiper-4.png"
          },
        ]
      }
    }
  }
</script>
