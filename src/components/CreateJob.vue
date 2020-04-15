<template>
  <div class="create-job border col-12">
    <form @submit.prevent="createJob()">
      <div class="form-group">
        <label for="jobTitle">Title</label>
        <input type="text" name="jobTitle" id="" class="form-control" placeholder="enter Title..." aria-describedby="helpId"
          v-model="newJob.jobTitle" required>
      </div>
      <div class="form-group">
        <label for="company">company</label>
        <input type="text" name="company" id="" class="form-control" placeholder="enter company..."
          aria-describedby="helpId" v-model="newJob.company" required>
      </div>
      <div class="form-group">
        <label for="hours">hours</label>
        <input type="number" name="hours" id="" class="form-control" placeholder="enter hours..."
          aria-describedby="helpId" v-model="newJob.hours" required>
      </div>
      <div class="form-group">
        <label for="rate">rate</label>
        <input type="number" name="rate" id="" class="form-control" placeholder="enter rate..."
          aria-describedby="helpId" v-model="newJob.rate" required>
      </div>
      <div class="form-group">
        <label for="description">description</label>
        <input type="text" name="description" id="" class="form-control" placeholder="enter description..."
          aria-describedby="helpId" v-model="newJob.description" required>
      </div>
      <button type="submit" class="btn btn-success"> Add Job</button>
    </form>
  </div>
</template>

<script>
  export default {
    name: 'create-job',
    data() {
      return {
        newJob: {}
      }
    },
    methods: {
      createJob() {
        this.$store.dispatch('createJob', this.newJob)
        this.newJob = {}
      }
    }
  }
</script>

<style>
  .jobs {
    outline: 1px solid black;
  }
</style>