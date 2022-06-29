<template>
  <h1>Jobs</h1>
  <div v-for="job in jobs" :key="job.id">
    <router-link :to="{name: 'JobDetails', params: {id: job.id}}" class="job">
        <h2><a>{{job.title}}</a></h2>
    </router-link>
  </div>  
</template>

<script>

export default {
    data() {
        return {
            jobs: []
        }
    },
    mounted() {
        fetch('http://localhost:3000/jobs')
            .then(res => res.json())
            .then(data => this.jobs = data)
            .catch((err) => {
                console.log('Error has occured');
                console.log(err.message);
            } )
    }

}
</script>

<style>
.job h2{
    background: #f4f4f4;
    padding: 20px;
    border-radius: 10px;
    margin: 10px auto;
    max-width: 600px;
    cursor: pointer;
    color: #444;
  }
  .job h2:hover {
    background: #ddd;
    
  }
  .job a{
    text-decoration: none;
    
  }

</style>