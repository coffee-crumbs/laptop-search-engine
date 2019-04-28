<template>
  <div class='app'>
    <header class='top-container'>
      <img class='logo' src='https://pcpartpicker.com/static/img/logo.svg' alt='Logo'>
      <ul class='nav'>
        <li class='nav-item'>Log In</li>
        <li class='nav-item'>Register</li>
      </ul>
    </header>
    <section class='choose-laptop-banner'>
      <b>Choose a Laptop</b>
    </section>
    <main class='main-container'>
      <section class='filter-container'>
        <section class='filter-group'>
          <b>Filters</b>
        </section>
      </section>
      <section class='laptop-display-container'>
        <section class='laptop-display-group'>
          <b>Products</b>
          <input class='search-laptops' type="text" placeholder="Search Laptops...">
        </section>
        <table class='laptop-table'>
          <thead>
            <tr>
              <th></th>
              <th>Laptop</th>
              <th>Rating</th>
              <th>Price</th>
              <th></th>
            </tr>
          </thead>
          <tbody>
            <Laptop :laptop="this.laptops[0]" />
          </tbody>
        </table>
      </section>
    </main>
  </div>
</template>

<script>
import Laptop from './components/Laptop.vue';
import laptopData from './data/laptops.json';

export default {
  name: 'app',
  components: {
    Laptop
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
      // fetch(laptopData)
      //   .then(res => res.json())
      //   .then(data => {
      //     this.laptops = data;
      //   });
    }
  }
}
</script>

<style>
body, .app{
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
  padding: 1em 4em;
  background-color: #0F111A;
  height: 3.5em;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.top-container .logo {
  height: 80%;
}

.nav {
  width: 15%;
  list-style: none;
  display: flex;
  justify-content: space-around;
}

.nav-item {
  color: white;
}

.nav-item:hover {
  color: #EDA920;
  cursor: pointer;
}

.choose-laptop-banner {
  height: 6em;
  background-color: #505FA1;
  display: flex;
  justify-content: center;
  align-items: center;
}

.choose-laptop-banner b {
  color: white;
  font-size: 2em;
}

.main-container {
  height: 35em;
  display: flex;
}

.filter-container {
  width: 30%;
  padding: 2em;
}

.filter-group {
  padding-bottom: 1em;
  width: 100%;
  border-bottom: 1px solid black;
}

.filter-group b {
  font-size: 1.2em;
}

.laptop-display-container {
  width: 70%;
  padding: 2em;
}

.laptop-display-group {
  padding-bottom: 1em;
  width: 100%;
  border-bottom: 1px solid black;
  display: flex;
  justify-content: space-between;
}

.laptop-display-group b {
  font-size: 1.2em;
}

.search-laptops {
  font-size:18px;
  width:250px;
  border:none;
  border-bottom:1px solid #757575;
}

.search-laptops:focus {
  outline: none;
}

.laptop-table {
  width: 100%;
  border-collapse: collapse;
}

.laptop-table tr {
  border-bottom: 1px solid #999999;
}

.laptop-table tbody tr {
  height: 5em;
}

.laptop-table th {
  font-size: .75em;
  padding: 1em .5em;
  color: #555555;
}
</style>
