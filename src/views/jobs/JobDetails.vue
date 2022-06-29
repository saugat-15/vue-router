<template>
  <h1>Job Details Page</h1>
  <p>The job id is: {{id}}</p>
  <p>The title of job: {{title}}</p>
</template>

<script>
export default {
    props: ['id', 'title'],
    // data() {
    //     return {
    //         id: this.$route.params.id
    //     }
    // }
}
</script>

<style>

</style>