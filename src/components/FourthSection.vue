<template>
  <section class="section__fourth">
    <div class="container">
      <div class="columns is-vcentered">
        <div class="column">
          <div class="section__fourth__content">
            <span class="section__fourth__content__number">N°216</span>
            <p class="section__fourth__content__subtitle">
              Intelligences Artificielles : comment elles réinventent la musique
            </p>
          </div>
        </div>
        <div class="column section__fourth__image has-text-centered">
          <img src="../assets/img/before-footer.png">
        </div>
      </div>
    </div>
  </section>
</template>

<script>

  import ScrollReveal from 'scrollreveal';

  export default {
    name: "FourthSection",
    mounted() {

      let sr = ScrollReveal({
        interval: 600,
        viewOffset: {
          bottom: 250
        }
      })
      sr.reveal('.section__fourth__image', {
        origin: 'left',
        scale: 0.85
      });
      sr.reveal('.section__fourth__content__number', {
      })
      sr.reveal('.section__fourth__content__subtitle', {
        origin: 'right',
      })
    },
  }
</script>
