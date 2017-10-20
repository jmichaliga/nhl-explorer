<template>
  <div>
    <h3>Schedule</h3>
    <pre>{{schedule.date}}</pre>

    <div class="games">
      <div class="game" v-for="game in schedule.games">
        <pre>
          <strong>{{game.teams.away.score}}</strong>
          {{game.teams.away.team.name}} 
          ( {{game.teams.away.leagueRecord.wins}}-{{game.teams.away.leagueRecord.losses}}-{{game.teams.away.leagueRecord.ot}} )
          v. 
          <strong>{{game.teams.home.score}}</strong>
          {{game.teams.home.team.name}}
          ( {{game.teams.home.leagueRecord.wins}}-{{game.teams.home.leagueRecord.losses}}-{{game.teams.home.leagueRecord.ot}} )
        </pre>
        <pre>{{game.gameDate}}</pre>
        <pre>{{game.status.detailedState}}</pre>
      </div>
    </div>
  </div>
</template>

<script>
import axios from 'axios'
// import moment from 'moment'

export default {
  async asyncData () {
    const { data } = await axios.get('https://statsapi.web.nhl.com/api/v1/schedule')
    console.log('>', data)
    return { schedule: data.dates[0] }
  }
}
</script>

<style scoped>
  .games{ padding: 10px; width: 100%; }
  .game{ padding: 10px; float: left; width: 100%; border: 1px solid #CCC; background: #DDD; text-align: center; }
</style>
