<template>
  <div v-if="jobs">
    <h1>{{ jobs.title }}</h1>
    <p>The job id is: {{ id }}</p>
    <p>details: {{ jobs.details }}</p>
    <!-- <p>Count: {{ count }}</p> -->
  </div>
  <div v-else>Loading Job Details:</div>

  <!-- <button @click="increaseCount">increase count</button>
  <button @click="decreaseCount">decrease count</button>
  <button @click="resetCount">reset count</button> -->
</template>

<script>
export default {
  props: ["id"],

  data() {
    return {
      jobs: null,
    //   count: 0,
    };
  },
//   methods: {
//     increaseCount() {
//       this.count++;
//     },
//     decreaseCount() {
//       this.count--;
//     },
//     resetCount() {
//       this.count = 0;
//     },
//   },
  mounted() {
    fetch("http://localhost:3000/jobs/" + this.id)
      .then((res) => res.json())
      .then((data) => (this.jobs = data))
      .catch((err) => console.log(err.message));
  },
};
</script>

<style></style>
