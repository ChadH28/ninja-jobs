<template>
  <div>
    <h1>Jobs</h1>
    <hr />
    <div v-if="jobs.length">
      <div v-for="job in jobs" :key="job.id" class="job">
        <router-link :to="{ name: 'JobDetails', params: { id: job.id } }">
          <h2>{{ job.title }}</h2>
        </router-link>
      </div>
    </div>
    <div v-else>
      Loading... Patience....
    </div>
  </div>
</template>



<script>
export default {
  data() {
    return {
      jobs: [],
    };
  },
  mounted() {
    fetch("http://localhost:3000/jobs")
      .then((result) => result.json())
      .then((data) => (this.jobs = data))
      .catch((error) => console.log(error));
  },
};
</script>

<style>
.job h2 {
  background: grey;
  padding: 20px;
  border-radius: 10px;
  margin: 10px auto;
  max-width: 600px;
  cursor: pointer;
  color: maroon;
  border: solid white 2px;
}

.job h2:hover {
  background: maroon;
  border: solid grey 2px;
  color: grey;
}

.job a {
  text-decoration: none;
}
</style>