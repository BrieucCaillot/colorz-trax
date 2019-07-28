<template>
    <section class="section__third">
        <div v-for="(event, index) in event_list">

            <div v-if="event.type == 'big'" class="section__third__elem elem-big">
                <span class="section__third__elem__number elem-big">{{ event_number(index) }}</span>
                <div class="section__third__elem__content elem-big"
                     :style="{ 'background-image': `url(${require('@/assets/img/'+ event.image +'')})` }">
                    <div class="columns">
                        <div class="column">
                            <span class="has-text-white">{{ event.title }}</span>
                            <h2 class="section__third__elem__content__title elem-big">
                                <a href="javascript:void(0)">{{ event.name }}</a>
                            </h2>
                            <div class="section__third__elem__content__date-time elem-big">
                                <div class="level">
                                    <div class="level-left">
                                        <span class="section__third__elem__content__date elem-big">{{ event.date }}</span>
                                        <span class="section__third__elem__content__time elem-big">{{ event.time }}</span>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>

            <div v-else class="section__third__elem">
                <span class="section__third__elem__number">{{ event_number(index) }}</span>
                <div class="section__third__elem__image">
                    <a href="javascript:void(0)"
                       :style="{ 'background-image': `url(${require('@/assets/img/'+ event.image +'')})` }"></a>
                </div>
                <div class="section__third__elem__content">
                    <div class="columns">
                        <div class="column">
                            <h2 class="section__third__elem__content__title">
                                <a href="javascript:void(0)">{{ event.name }}</a>
                            </h2>
                            <span class="section__third__elem__content__location">{{ event.location }}</span>
                            <div class="section__third__elem__content__date-time">
                                <div class="level">
                                    <div class="level-left">
                                        <span class="section__third__elem__content__date">{{ event.date }}</span>
                                        <span class="section__third__elem__content__time">{{ event.time }}</span>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>

        </div>
    </section>
</template>

<script>

  import ScrollReveal from 'scrollreveal';

  export default {
    name: "ThirdSection",
    mounted() {
      let sr = ScrollReveal({
        origin: 'left',
        distance: '40px',
        reset: false,
        duration: 1200,
        viewOffset: {
          bottom: 100
        }
      })
      sr.reveal('.section__third__elem__number', {
        mobile: false,
        distance: '60px',
        delay: 500,
        viewOffset: {
          bottom: 200
        }
      }),
        sr.reveal('.section__third__elem__content__title', {
          delay: 700,
        }),
        sr.reveal('.section__third__elem__content__location', {
          delay: 900,
        }),
        sr.reveal('.section__third__elem__content__date, .section__third__elem__content__time', {
          delay: 1200,
        })
    },
    computed: {
      event_list() {
        return [
          {
            "type": "default",
            "name": "House Of Underground 2 years anniversary w/ Deejay Astral",
            "location": "Debonair - Paris",
            "date": "Ven. 18 janv.",
            "time": "23h00 à 6h00",
            "image": "third-section-1.png"
          },
          {
            "type": "default",
            "name": "SKURT w/ Black Tiger Sex Machine & more",
            "location": "Le Bikini - Ramonville-Saint-Agne",
            "date": "Ven. 18 janv.",
            "time": "23h00 à 6h00",
            "image": "third-section-2.png"
          },
          {
            "type": "default",
            "name": "Boussole 6 Anniversary Party feat. LONE (R&S)",
            "location": "Le Bikini - Ramonville-Saint-Agne",
            "date": "Sam. 19 janv.",
            "time": "23h00 à 6h00",
            "image": "third-section-3.png"
          },
          {
            "type": "default",
            "name": "Belleville Boogie: Volcov Theo Mamie's Jan Decent & Martin Malin",
            "location": "La Java - Paris",
            "date": "Sam. 19 janv.",
            "time": "23h00 à 6h00",
            "image": "third-section-4.png"
          },
          {
            "type": "big",
            "title": "Don't miss",
            "name": "La Machine: L'anniversaire 10-1",
            "location": "La Java - Paris",
            "date": "vendredi 25 janv.",
            "time": "23h00 à 6h00",
            "image": "third-section-5.png"
          },
        ]
      },
    },
    methods: {
      event_number(index) {
        switch (index) {
          case 0:
            return 18;
          case 2:
            return 19;
          case 4:
            return 25;
        }
      }
    }
  }
</script>

<style scoped>

</style>
