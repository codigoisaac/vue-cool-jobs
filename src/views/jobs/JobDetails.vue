<template>
  <h1>Job Details</h1>

  <p>Job id: {{ id }}</p>
  <p>Jod title: {{ job.title }}</p>
  <p>Jod details: {{ job.details }}</p>
</template>

<script>
export default {
  props: ["id"],
  data() {
    return {
      job: null,
    };
  },
  created() {
    fetch("http://localhost:3000/jobs/" + this.id)
      .then((res) => res.json())
      .then((data) => (this.job = data))
      .catch((error) => console.log(error.message));
  },
};
</script>

<style></style>
