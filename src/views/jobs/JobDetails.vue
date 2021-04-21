<template>
  <div>
    <h1>Job details page</h1>
    <hr />
    <div v-if="job">
      <h2>{{ job.title }}</h2>
      <p>The job is for {{ job.details }}</p>
    </div>
    <div v-else>
      <p>Loading Details</p>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      job: null,
    };
  },
  props: ["id"],
  mounted() {
    fetch(`http://localhost:3000/jobs/${this.id}`)
      .then((result) => result.json())
      .then((data) => (this.job = data))
      .catch((error) => console.log(error));
  },
};
</script>

<style>
</style>