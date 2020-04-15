<template>
  <div class="jobs col-12">
    <p>here is the jerbs page</p>
    <div class="row">
      <job v-for="job in jobs" :job="job" :key="job._id"></job>
      <!-- job details go here -->
      <create-job></create-job>
    </div>


  </div>

  
</template>


<script>
import Job from "../components/Job";
//import CreateCar from "../components/CreateCar";
import CreateJob from "../components/CreateJob";
export default {
  name: "jobs",
  data() {
    return {};
  },
  computed: {
    jobs() {
      return this.$store.state.jobs
      //.sort((a, b) => a.make.charCodeAt(0) - b.make.charCodeAt(0));
    },
    created() {
      this.$store.dispatch("getJobs");
    }
    
  },
  methods: {},
  components: {
    Job,
    CreateJob
  }
};
</script>


<style scoped>
</style>