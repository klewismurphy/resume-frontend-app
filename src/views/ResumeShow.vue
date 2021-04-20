<template>
  <div class="resumeShow">
    <h1>{{ message }}</h1>
    <h2>Experience</h2>
    <p> {{ experience.job_title }} </p>
  </div>
</template>

<style>
</style>

<script>
import axios from "axios";
export default {
  data: function () {
    return {
      message: "Resume",
      experience: {},
    };
  },
  created: function () {
    axios.get("/api/experiences/1").then((response) => {
      console.log(response.data);
      this.experience = response.data;
    });
  },
  methods: {},
};
</script>