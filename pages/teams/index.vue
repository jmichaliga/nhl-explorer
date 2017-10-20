<template>
  <div class="container">
    <!-- <pre>{{ teams }}</pre> -->
    <h2>Teams</h2>
    <ul class="teams">
      <li v-for="team in teams">
        <nuxt-link :to="'/teams/'+team.id">{{ team.name }}</nuxt-link>
      </li>
    </ul>
  </div>
</template>

<script>
import axios from 'axios'
export default {
  async asyncData () {
    const { data } = await axios.get('https://statsapi.web.nhl.com/api/v1/teams')
    console.log('>', data)
    return { teams: data.teams }
  }
}
</script>

<style>

</style>