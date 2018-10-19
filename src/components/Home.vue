<template>
  <div class="home">
    <header class="header">
      <nav v-on:click="displayMe = !displayMe" class="hamburger">
        <button class="hamburger__button">
          <span class="hamburger__button--bar"></span>
          <span class="hamburger__button--bar"></span>
          <span class="hamburger__button--bar"></span>
        </button>
      </nav>
      <nav class="desktop">
        <div class="desktop__navigation">
          <div>Recipes</div>
          <div>More</div>
        </div>
      </nav>
    </header>
    <transition name="slide-fade">
      <nav v-if="displayMe" class="mobile">
        <ul class="mobile__items">
          <li class="mobile__item">Recipes</li>
          <li class="mobile__item">more</li>
        </ul>
      </nav>
    </transition>
    <main class="background">
      <div class="background__image"></div>
    </main>
    <footer>
      <div>Yummy!</div>
    </footer>

  </div>
</template>

<script>
  export default {
    name: 'Home',
    data() {
      return {
        displayMe: false
      }
    },
    methods: {

    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  @import url('https://fonts.googleapis.com/css?family=Hind|Indie+Flower');

  body {
    margin: 0;
    font-family: 'Hind', sans-serif;
  }

  .header {
    background: rgb(24, 109, 24);
    color: white;
    display: flex;
    align-items: center;
    justify-content: space-between;
    height: 50px;
    padding: 5px 20px;
  }

  /*hamburger icon*/
  .hamburger {
    display: flex;
    align-items: center;
    z-index: 1;
  }

  .hamburger__button {
    width: 3rem;
    background: transparent;
    border: none;
    cursor: pointer;
    padding-top: 0;
    padding-bottom: 0;
  }

  .hamburger__button:focus {
    outline: none;
  }

  .hamburger__button--bar {
    width: 100%;
    height: 0.2rem;
    background: white;
    display: block;
    margin: 0.6rem 0;
  }

  /*desktop*/
  .desktop__navigation {
    display: flex;
    justify-content: flex-end;
  }

  .desktop__navigation div {
    padding-left: 20px;
    display: none;
  }

  /*background*/
  .background__image {
    background: url("https://res.cloudinary.com/dmglopmul/image/upload/v1539799606/projectPhotos/side-nav/background.jpg");
    width: 100vw;
    height: 40vh;
    background-size: cover;
    background-position: center;
  }

  /*footer*/
  footer div {
    color: gray;
    font-family: 'Indie Flower', sans-serif;
    font-size: 60px;
    width: 80vw;
    margin: auto;
    text-align: center;
    padding: 100px 0;
  }

  .mobile {
    position: fixed;
    top: 0;
    background: rgba(90, 90, 90, 0.9);
    width: 80vw;
    height: 100vh;
    color: white;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    text-align: center;
  }

  .mobile__items {
    list-style: none;
    padding: 0;
    margin: 0;
    font-size: 2rem;
  }

  .slide-fade-enter-active {
    transition: all .6s ease;
  }

  .slide-fade-leave-active {
    transition: all .8s cubic-bezier(1.0, 0.5, 0.8, 1.0);
  }

  .slide-fade-enter,
  .slide-fade-leave-to

  /* .slide-fade-leave-active below version 2.1.8 */
    {
    transform: translateX(10px);
    opacity: 0;
  }

  /*media queries*/
  @media (min-width: 40rem) {
    .hamburger__button {
      display: none;
    }

    .desktop__navigation div {
      display: block;
    }
  }
</style>