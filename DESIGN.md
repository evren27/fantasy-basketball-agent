# Design Decisions

How I designed a team of Claude agents to manage my Yahoo Fantasy Basketball team, and why.

## Goal
- Build something genuinely useful while learning Python, GitHub and AI agents. Winning my league is a bonus.
- Measure success by fantasy points gained compared with doing nothing, reported every Monday.

## League context
- 10-team, head-to-head points league with custom scoring: steals 3, blocks 2, offensive rebounds and assists 1.5, missed free throws -0.5.
- No waivers (first to add a free agent gets him), 3 adds per week, 10 starters a day.

## Strategy decisions
1. **Rank players by my league's real scoring**, not Yahoo's default rankings.
2. **Set the lineup one day at a time.** Yahoo's weekly projection only counts lineups already set, so this keeps my real strength hidden from opponents.
3. **Calculate my opponent's true weekly projection** instead of trusting Yahoo's number, and detect whether they set their lineup for the whole week.
4. **Score every free agent twice:** points this week, and long-term upside. In a close week, this week wins; when I'm well ahead or the week is lost, upside wins.
5. **Upside combines stats with trusted experts:** Josh Lloyd, Dan Titus and Dan Besbris. Python calculates the trends; the agents interpret them.

## Architecture
- Five agents: a Chief of Staff I talk to, plus Research, Schedule, Waiver Wire and Trade Analyst specialists.
- Build order: daily lineup and injury moves first, then Waiver Wire, then the trend finder, then Trade Analyst.

## Safety and trust
- Lineup and injury moves get a one-week suggest-only trial, then run on their own.
- Every add, drop and trade always needs my approval.
- Passwords and API keys are never stored in this repository.

## How it was built
- I designed the system and wrote the agent instructions; Claude helped write the Python, credited as co-author on its commits.
- I review and merge every change myself.
