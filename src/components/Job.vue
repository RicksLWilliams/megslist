<template>
  <div class="job border col-3" @click="selectJob()">
    <p>{{job.jobTitle}}</p>
    <p>{{job.company}}</p>
    <p>Hours: {{job.hours}}</p>
    <p>Rate:{{job.rate}}</p>
    <p>{{job.description}}</p>
  </div>
</template>

<script>
export default {
  name: "job",
  props: ["job"],
  data() {
    return {};
  },
  methods: {
    selectJob() {
      this.$store.commit("setActiveJob", {});
      this.$router.push({
        name: "JobDetails",
        params: { jobId: this.job._id }
      });
    }
  }
};
</script>

<style>
.jobs {
  outline: 1px solid black;
}
</style>