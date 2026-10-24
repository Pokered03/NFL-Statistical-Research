# Sources, permissions and coverage

Primary integrated source: [nflverse / nflverse-data](https://github.com/nflverse/nflverse-data).

CC BY 4.0; modified by this research application

Other source-specific links:

- nflverse data and license: https://github.com/nflverse/nflverse-data
- hoopR NBA data: https://github.com/sportsdataverse/hoopR-nba-data
- hoopR D-I data: https://github.com/sportsdataverse/hoopR-mbb-data
- cfbfastR data publication: https://github.com/sportsdataverse/cfbfastR-cfb-data
- fastRhockey NHL data: https://github.com/sportsdataverse/fastRhockey-nhl-data
- baseballr schedule archive: https://github.com/sportsdataverse/baseballr-data
- Retrosheet permissions and downloads: https://www.retrosheet.org/downloads/csvdownloads.html
- Retrosheet game-log fields: https://www.retrosheet.org/gamelogs/glfields.txt

Only this sport’s adapter runs. No source requires an existing Odds API key. The data worker has an explicit host allowlist and rejects other API hosts. No direct ESPN scraping is enabled. No proprietary logo or premium statistical dataset is distributed. Preserve upstream notices and verify original league/dataset rights before public redistribution; an open-source wrapper license does not by itself license every underlying league asset. College football’s dataset-specific redistribution terms remain a public-release blocker.

## Snapshot coverage at build time

```json
[
  {
    "season": 2023,
    "teams_with_completed_games": 32,
    "registered_teams": 32,
    "schedule_games": 285,
    "latest_final": "2024-02-11"
  },
  {
    "season": 2024,
    "teams_with_completed_games": 32,
    "registered_teams": 32,
    "schedule_games": 285,
    "latest_final": "2025-02-09"
  },
  {
    "season": 2025,
    "teams_with_completed_games": 32,
    "registered_teams": 32,
    "schedule_games": 285,
    "latest_final": "2026-02-08"
  },
  {
    "season": 2026,
    "teams_with_completed_games": 32,
    "registered_teams": 32,
    "schedule_games": 272,
    "latest_final": "2026-10-22"
  }
]
```

These counts describe source observations, not independently certified official membership completeness. The current college-basketball preseason registry uses the latest available standings plus published conference membership; verify new-season changes when an official standings file becomes available. See the live coverage table for later updates.

## Expanded integrations and remaining gaps

Historical nflverse closing spreads and totals are now evaluated separately. The measured baseline fails both probability/category release gates, so spread and total remain PASS for an evidence-based reason rather than an assumed score. See `market_validation` in the backtest report. Original `spread_line` is positive for a home favorite; it is normalized to the manual-entry home-spread convention (negative for favorite).

Official MLB season and probable-pitcher data use a few bounded personal-research summary requests; no game-log/player-history bulk API fetch is enabled. Original MLB terms apply. No paid feed, Odds API key or premium grades are used. See the runtime source/coverage metadata and each per-metric sample count. Injury, weather, future goalie confirmations and proprietary metrics remain incomplete.
