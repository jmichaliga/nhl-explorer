# nhl-explorer

> NHL API Explorer

## Build Setup

``` bash
# install dependencies
$ npm install # Or yarn install

# serve with hot reload at localhost:3000
$ npm run dev

# build for production and launch server
$ npm run build
$ npm start

# generate static project
$ npm run generate
```

For detailed explanation on how things work, checkout the [Nuxt.js docs](https://github.com/nuxt/nuxt.js).

## More API Resources

- https://statsapi.web.nhl.com/api/v1/schedule?startDate=2018-02-27&endDate=2018-02-27&expand=schedule.teams,schedule.linescore,schedule.broadcasts.all,schedule.ticket,schedule.game.content.media.epg,schedule.radioBroadcasts,schedule.metadata,schedule.game.seriesSummary,seriesSummary.series&leaderCategories=&leaderGameTypes=R&site=en_nhl&teamId=15&gameType=&timecode=

- https://statsapi.web.nhl.com/api/v1/teams/15?hydrate=franchise(roster(season=20172018,person(name,stats(splits=[yearByYear]))))

- https://statsapi.web.nhl.com/api/v1/teams/15?expand=team.leaders,leaders.person&leaderGameTypes=R&leaderCategories=goals,assists,points,wins&season=20172018

- https://statsapi.web.nhl.com/api/v1/people/8475744?hydrate=currentTeam(name,stats(splits=[yearByYear]))

- https://statsapi.web.nhl.com/api/v1/statTypes

- https://statsapi.web.nhl.com/api/v1/schedule?expand=schedule.teams,schedule.scoringplays

-> https://nhl-score-api.herokuapp.com/
—> https://nhl-score-api.herokuapp.com/api/scores/latest
