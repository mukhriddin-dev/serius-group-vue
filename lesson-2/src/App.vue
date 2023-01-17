<template>
  <Header />
  <main>
    <Counter
      :number="num"
      @add="dicrement"
      @minus="increment"
      @zero="resetCount"
    />

    <div class="container">
      <div class="card p-4 mx-auto mt-5 shadow">
        <form action="#">
          <label for="title" class="w-75 mx-auto d-block mb-3">
            <p>Enter task title</p>
            <input
              type="text"
              class="form-control p-3"
              id="title"
              placeholder="Enter task title"
              @input="title=$event.target.value"
              v-bind:value="title"
            />
          </label>

          <label for="title" class="w-75 mx-auto d-block">
            <p>Enter task deadline</p>
            <input
              type="date"
              class="form-control p-3"
              id="title"
              placeholder="Enter task title"
              @input="date=$event.target.value"
              v-bind:value="date"
            />
          </label>

          <button class="btn btn-success mx-auto mt-3 d-block w-75" @click="addtask">
            add task
          </button>
        </form>
      </div>

      <div class="card p-4 mx-auto mt-5 shadow">
        <ul class="list-group">
          <li class="list-group-item" v-for="item in task">
            {{ item.id }} . {{ item.title }} {{ item.date }}
          </li>
        </ul>
      </div>
    </div>
  </main>
  <Footer />
</template>

<script>
import Header from "./components/Header/Header.vue";
import Counter from "./components/Counter/Counter.vue";
import Footer from "./components/Footer/Footer.vue";

export default {
  components: {
    Header,
    Counter,
    Footer,
  },

  data() {
    return {
      num: 0,
      str: "Vue.js",
      task: [
        { id: 1, title: "lorem ipsum dolor set amet ", date: "2023-01-30" },
        { id: 2, title: "lorem ipsum dolor set amet ", date: "2023-01-31" },
      ],
      title: "",
      date: "",
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
    addtask() {

      const newTask = {
        id: Date.now(),
        title: this.title,
        date: this.date,
      };

      this.task.push(newTask);

      this.title=""
      this.date=""
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
