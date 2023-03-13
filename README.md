# Sports Betting Bot ChatGPT

This is a chatbot that uses the [ChatGPT API](https://platform.openai.com/account/api-keys)

## Parameters

- **sport**   The sport key obtained from calling the /sports endpoint. upcoming is always valid, returning any live games as well as the next 8 upcoming games across all sports

- **apiKey**   An API key is emailed when you sign up to a plan. See here for usage plans

- **regions**   Determines the bookmakers to be returned. Valid regions are us (United States), uk (United Kingdom), au (Australia) and eu (Europe). Multiple regions can be specified if comma delimited. See here for a list of bookmakers by region.

- **markets**   Optional - Determines which odds market is returned. Defaults to `h2h` (head to head / moneyline). Valid markets are `h2h` (moneyline), spreads (points handicaps), totals (over/under) and outrights (futures). Multiple markets can be specified if comma delimited. `spreads` and `totals` markets are mainly available for US sports and bookmakers at this time. Each specified market costs 1 against the usage quota, for each region.

- **Lay odds** are automatically included with `h2h` results for relevant betting exchanges (Betfair, Matchbook etc). These have a `h2h_lay` market key.

For sports with outright markets (such as Golf), the market will default to `outrights` if not specified. Lay odds for outrights (`outrights_lay`) will automatically be available for relevant exchanges.

For more info, see descriptions of betting markets.

- **dateFormat**   Optional - Determines the format of timestamps in the response. Valid values are unix and iso (ISO 8601). Defaults to iso.

- **oddsFormat**   Optional - Determines the format of odds in the response. Valid values are decimal and american. Defaults to decimal. When set to american, small discrepancies might exist for some bookmakers due to rounding errors.

- **eventIds**   Optional - Comma-separated game ids. Filters the response to only return games for the specified game ids.

- **bookmakers**   Optional - Comma-separated list of bookmakers to be returned. If both bookmakers and regions are specified, bookmakers takes priority. Bookmakers can be from any region. Every group of 10 bookmakers counts as 1 request. For example for a single market, specifying up to 10 bookmakers counts as 1 request. Specifying between 11 and 20 bookmakers counts as 2 requests.

