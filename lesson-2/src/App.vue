<template>
  <header class="bg-success">
    <div class="container">
      <nav class="nav bg-success text-white d-flex justify-content-between">
        <h3 class="nav__logo">VUE.JS</h3>
        <ul class="nav__list d-flex justify-content-between w-25 list-unstyled">
          <li class="nav__list--item">
            <a href="#" class="nav__ul--list-link">Home</a>
          </li>
          <li class="nav__list--item">
            <a href="#" class="nav__ul--list-link">About</a>
          </li>
          <li class="nav__list--item">
            <a href="#" class="nav__ul--list-link">Contact</a>
          </li>
          <li class="nav__list--item">
            <a href="#" class="nav__ul--list-link">Service</a>
          </li>
        </ul>
      </nav>
    </div>
  </header>
  <!-- header end -->

  <main>
    <div class="container">
      <!-- main content -->

      <div class="card w-75 mx-auto p-5 shadow mt-5">
        <h1 class="text-center">{{ num }}</h1>
        <div class="btn-group" role="group" aria-label="Basic mixed styles example">
          <button type="button" class="btn btn-danger" v-on:click="dicrement">
            DICREMENT
          </button>
          <button type="button" class="btn btn-success" v-on:click="increment">
            INCREMENT
          </button>
          <button type="button" class="btn btn-warning" v-on:click="resetCount">
            RESET
          </button>
        </div>
      </div>
    </div>
  </main>

  <footer class="p-3 text-center text-white bg-success">
    <div class="container">
      <p>{{ new Date().getFullYear() }} Vue.js</p>
    </div>
  </footer>
</template>

<script>
export default {
  data() {
    return {
      num: 0,
      str: "Vue.js",
    };
  },

  methods: {
    dicrement() {
      console.log((this.num -= 1));
    },
    increment() {
      console.log((this.num += 1));
    },
    resetCount() {
      this.num = 0;
    },
  },
};
</script>

<style>
main {
  height: calc(100vh - 70px - 65px);
}
.nav {
  height: 75px;
  align-items: center;
  display: flex;
}

.nav__ul--list-link {
  text-decoration: none;
  color: white;
}
</style>
