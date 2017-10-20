<template>
  <div class="container">
    <h2>Player:</h2>
    <pre>{{ player.people }}</pre>
  </div>
</template>

<script>
import axios from 'axios'
export default {
  async asyncData ({ params, error }) {
    console.log('params:', params)
    try {
      const { data } = await axios.get('https://statsapi.web.nhl.com/api/v1/people/' + params.id)
      return { player: data }
    } catch (e) {
      console.warn({ message: 'Player not Found', statusCode: 404 })
    }
  }
}
</script>

<style>

</style>