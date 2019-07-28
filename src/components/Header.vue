<template>
  <header class="header full-w"
          :class="{ 'header-sticky': scrolled }">
    <div class="container full-h">
      <nav class="navbar d-flex ai-c tt-u jc-sb"
           role="navigation" aria-label="main navigation">
        <div class="navbar__left">
          <div class="navbar-item">
            <div @click="toggleBurger()" class="icon icon__burger"></div>
          </div>
        </div>
        <div class="navbar__center d-flex jc-c ai-c"
             :class="{'navbar__center-opened': burgerOpened}">
          <ul class="menu__list">
            <li class="menu__item"><a href="javascript:void(0)" class="menu__link menu__link__text">Lire</a></li>
            <li class="menu__item"><a href="javascript:void(0)" class="menu__link menu__link__text">Écouter</a>
            </li>
            <li class="menu__item is-hidden-touch">
              <a class="menu__link logo" href="/">
                <img src="../assets/img/logo-white.png" alt="logo-trax" width="180" height="34">
              </a>
            </li>
            <li class="menu__item"><a href="javascript:void(0)" class="menu__link menu__link__text">Regarder</a></li>
            <li class="menu__item"><a href="javascript:void(0)" class="menu__link menu__link__text">Sortir</a></li>
          </ul>
        </div>
        <div class="navbar__center-mobile is-hidden-desktop">
          <a class="navbar-item logo" href="/">
            <img src="../assets/img/logo-white.png" alt="logo-trax" width="112" height="28">
          </a>
        </div>
        <div class="navbar__right">
          <div class="navbar-item">
            <div class="icon icon__search"></div>
          </div>
        </div>
      </nav>
    </div>
  </header>
</template>

<script>
  export default {
    name: "Header",
    data() {
      return {
        scrolled: false,
        burgerOpened: false
      }
    },
    mounted() {
      window.addEventListener('scroll', () => this.onScroll())
    },
    methods: {
      onScroll() {
        const currentScrollPosition = window.pageYOffset || document.documentElement.scrollTop
        this.scrolled = currentScrollPosition > 50;
      },
      toggleBurger() {
        const currentWindowWidth = window.innerWidth;
        if (currentWindowWidth < 1024) {
          this.burgerOpened = !this.burgerOpened;
        }
      }
    }
  }
</script>
