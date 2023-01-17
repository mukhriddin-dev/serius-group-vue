<template>
  <div class="container">
    <!-- main content -->

    <div class="card w-75 mx-auto p-5 shadow mt-5">
      <h1 class="text-center">{{ number }}</h1>
      <div class="btn-group" role="group" aria-label="Basic mixed styles example">
        <button type="button" class="btn btn-danger" @click="decr">DICREMENT</button>
        <button type="button" class="btn btn-success" @click="incr">INCREMENT</button>
        <button type="button" class="btn btn-warning" @click="reset">RESET</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    number: {
      type: Number,
      required: true,
    },
  },

  methods: {
    decr() {
      this.$emit("add");
    },
    incr() {
      this.$emit("minus");
    },
    reset() {
      this.$emit("zero");
    },
  },
};
</script>

<style></style>
