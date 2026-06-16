# **💫 About Me**
🧰 **Building tools for clarity.**  
**Under Development***

**[drivarc/landing](https://github.com/drivarc/landing)**

**[drivarc.com](https://drivarc.com)**

# Visit https://github.com/lowlighter/metrics#-documentation for full reference
name: Metrics
on:
  # Schedule updates (each hour)
  schedule: [{cron: "0 * * * *"}]
  # Lines below let you run workflow manually and on each commit
  workflow_dispatch:
  push: {branches: ["master", "main"]}
jobs:
  github-metrics:
    runs-on: ubuntu-latest
    permissions:
      contents: write
    steps:
      - uses: lowlighter/metrics@latest
        with:
          # Your GitHub token
          # The following scopes are required:
          #  - public_access (default scope)
          # The following additional scopes may be required:
          #  - read:org      (for organization related metrics)
          #  - read:user     (for user related data)
          #  - read:packages (for some packages related data)
          #  - repo          (optional, if you want to include private repositories)
          token: ${{ secrets.METRICS_TOKEN }}

          # Options
          user: Erogz
          template: classic
          base: ""
          config_octicon: yes
          config_timezone: Europe/Bursa
          config_twemoji: yes
          plugin_achievements: yes
          plugin_achievements_display: detailed
          plugin_achievements_secrets: yes
          plugin_achievements_threshold: B
          plugin_introduction: yes
          plugin_introduction_title: yes
          plugin_isocalendar: yes
          plugin_isocalendar_duration: full-year
          plugin_lines: yes
          plugin_lines_history_limit: 10
          plugin_lines_repositories_limit: 4
          plugin_lines_sections: base
          plugin_pagespeed: yes
          plugin_pagespeed_pwa: yes
          plugin_pagespeed_screenshot: yes
          plugin_pagespeed_url: drivarc.com
          plugin_repositories: yes
          plugin_repositories_order: featured, pinned, starred, random
          plugin_steam: yes
          plugin_steam_achievements_limit: 2
          plugin_steam_games_limit: 1
          plugin_steam_playtime_threshold: 2
          plugin_steam_recent_games_limit: 1
          plugin_steam_sections: player, most-played, recently-played
          plugin_steam_user: STEAM_0:1:455860232
