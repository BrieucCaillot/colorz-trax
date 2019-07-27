<template>
  <main>
    <section class="section__first">
      <div class="container full-h">
        <h1 class="tt-u has-text-centered">Agenda</h1>
      </div>
    </section>
    <SecondSection/>
    <ThirdSection/>
    <FourthSection/>
    <Footer/>
  </main>
</template>

<script>

  import SecondSection from '../components/SecondSection';
  import ThirdSection from '../components/ThirdSection';
  import FourthSection from '../components/FourthSection';
  import Footer from '../components/Footer';

  export default {
    name: "Home",
    components: {
      FourthSection,
      SecondSection,
      ThirdSection,
      Footer
    }
  }
</script>
