<template>
  <div class="container">
    <h2>Standings</h2>
    <div class="divisions">
      <div class="division" v-for="division in divisions">
        <h5>{{division.division.name}}</h5>
        <div v-for="tR in division.teamRecords">
           {{tR.divisionRank}}: {{tR.team.name}}, ( {{tR.leagueRecord.wins}}-{{tR.leagueRecord.losses}}-{{tR.leagueRecord.ot}} )
        </div>
        <!-- <pre>{{division}}</pre> -->
      </div>
    </div>
  </div>
</template>

<script>
import axios from 'axios'
export default {
  async asyncData () {
    const { data } = await axios.get('https://statsapi.web.nhl.com/api/v1/standings')
    console.log('>', data)
    return { divisions: data.records }
  },
  data () {
    return {
      // nhl_data: 'https://statsapi.web.nhl.com/api/v1/schedule?startDate=2017-01-01&endDate=2017-02-01&expand=schedule.teams,schedule.linescore,schedule.broadcasts,schedule.ticket,schedule.game.content.media.epg&leaderCategories=&site=en_nhl&teamId=5'
    }
  }
}
</script>

<style>
  .divisions{

  }

  .division{
    padding: 20px;
    float: left;
    width: 50%;
    background: #CCC;
  }
</style>