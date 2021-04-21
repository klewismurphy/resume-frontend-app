<template>
  <div class="resumeShow">
    <h1>{{ student.first_name }} {{ student.last_name }}</h1>
    <h3> {{student.email }} | {{student.phone_number }} | {{ student.linkedin_url }} </h3>
    <hr style="width:70%">
    <p> {{ student.short_bio }} </p>
    <hr style="width:70%">
    <h2> Experience </h2>
    <div v-for="experience in student.experiences"> 
      <hr style="width:10%">
     <b> {{ experience.job_title }} </b> 
     <p> {{experience.company_name }} </p>
     <p> {{ experience.start_date }} - {{ experience.end_date }} </p> 
     <p> {{ experience. details}} </p>
      </div>
    <hr style="width:70%">
    <h2> Education </h2>
    <div v-for="education in student.education"> 
      <hr style="width:10%">
      <b>{{ education.university_name }}</b>
      <p>{{ education.degree }}</p>
      <p>{{ education.start_date }} - {{ education.end_date }}</p>
       <p>{{ education.details }}</p>
      </div>
    <hr style="width:70%">
    <h2> Skills </h2>
      <div v-for="skill in student.skills"> 
      <hr style="width:10%">
      <p> {{ skill.skill_name_1 }}, {{ skill.skill_name_2 }}, {{ skill.skill_name_3 }}, {{ skill.skill_name_4 }} </p>
      </div>
    <hr style="width:70%">
    <h2> Capstone </h2>
    <div v-for="capstone in student.capstone"> 
      <hr style="width:10%">
      <b>{{ capstone.name }}</b>
      <p>Url: {{ capstone.url }}</p>
      <p> {{ capstone.description }}</p>
      </div>
      <hr>
      <br>
      <button> Update Resume </button>
      <br><br><br>
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
      student: {},
    };
  },
  created: function () {
    axios.get("/api/students/2").then((response) => {
      console.log(response.data);
      this.student = response.data;
    });
  },
  methods: {},
};
</script>