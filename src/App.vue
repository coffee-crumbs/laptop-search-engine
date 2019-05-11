<template>
  <div class='app'>
    <header class='top-container'>
      <img class='logo' src='https://pcpartpicker.com/static/img/logo.svg' alt='Logo'>
      <ul class='navigation'>
        <li class='navigation-item'>Log In</li>
        <li class='navigation-item'>Register</li>
      </ul>
    </header>
    <section class='choose-laptop-banner'>
      <b>Choose a Laptop</b>
    </section>
    <Laptops :laptops="this.laptops" />
  </div>
</template>

<script>
import Laptops from './components/Laptops.vue';
import laptopData from './data/laptops.json';

export default {
  name: 'app',
  components: {
    Laptops
  },
  data: function () {
    return {
      laptops: []
    }
  },
  mounted: function () {
    this.getLaptops();
  },
  methods: {
    getLaptops: function () {
      this.laptops = laptopData;
    }
  }
}
</script>

<style>
html, body, .app{
  margin: 0;
  padding: 0;
  width: 100%;
  height: 100%;
}

.app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

.top-container {
  padding: 0em 4em;
  background-color: #0F111A;
  height: 7.5%;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.top-container .logo {
  height: 70%;
}

.navigation {
  width: 20%;
  list-style: none;
  display: flex;
  justify-content: space-around;
  margin: 0;
}

.navigation-item {
  color: white;
}

.navigation-item:hover {
  color: #EDA920;
  cursor: pointer;
}

.choose-laptop-banner {
  height: 10%;
  background-color: #505FA1;
  display: flex;
  justify-content: center;
  align-items: center;
}

.choose-laptop-banner b {
  color: white;
  font-size: 2em;
}
</style>
