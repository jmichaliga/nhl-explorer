<template>
  <div class="container">
    <h2>Team:</h2>
    <!-- <pre>{{ team.roster }}</pre> -->

    <ul class="roster">
      <li class="player" v-for="player in team.roster">
        {{player.jerseyNumber}}: <a :href="'../players/'+player.person.id">{{player.person.fullName}}</a>, {{player.position.name}}
      </li>
    </ul>
  </div>
</template>

<script>
import axios from 'axios'
export default {
  async asyncData ({ params, error }) {
    console.log('params:', params)
    try {
      const { data } = await axios.get('https://statsapi.web.nhl.com/api/v1/teams/' + params.id + '/roster')
      return { team: data }
    } catch (e) {
      console.warn({ message: 'Team no Found', statusCode: 404 })
    }
  }
}
</script>

<style>

</style>