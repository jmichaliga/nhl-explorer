<template>
  <code>{{ nhl_data }}</code>
</template>

<script>
export default {
  components: {
    Logo
  },
  data () {
    return {
      nhl_data: 'https://statsapi.web.nhl.com/api/v1/schedule?startDate=2017-01-01&endDate=2017-02-01&expand=schedule.teams,schedule.linescore,schedule.broadcasts,schedule.ticket,schedule.game.content.media.epg&leaderCategories=&site=en_nhl&teamId=5'
    }
  }
}
</script>

<style>

</style>