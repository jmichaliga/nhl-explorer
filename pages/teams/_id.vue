<template>
  <div class="container">
    <h2>Team:</h2>
    <pre>{{ team }}</pre>
  </div>
</template>

<script>
import axios from 'axios'
export default {
  async asyncData ({ params, error }) {
    console.log('params:', params)
    try {
      const { data } = await axios.get('https://statsapi.web.nhl.com/api/v1/teams/' + params.id)
      return { team: data.teams[0] }
    } catch (e) {
      console.warn({ message: 'Team no Found', statusCode: 404 })
    }
  }
}
</script>

<style>

</style>