# Fantasy Basketball Agent

A team of five Claude agents that manages my Yahoo Fantasy Basketball team: setting daily lineups, handling injuries, and proposing pickups and trades for my approval.

> 🚧 **Status:** In progress. Version 1 (daily lineup and injury moves)

## How it works
- **Chief of Staff:** my single point of contact. Reads the specialists' reports, decides, and asks me before any add, drop or trade.
- **Research:** injuries, rest days and role changes.
- **Schedule:** games per day and the best daily lineup.
- **Waiver Wire:** free agents worth adding, scored on this week and long-term upside.
- **Trade Analyst:** buy-low and sell-high ideas.

Python handles the data and math; the agents handle judgment.

## Why it's different
My league uses custom scoring, so Yahoo's rankings misjudge players. The bot ranks everyone by my league's real scoring, sets lineups one day at a time to keep my weekly projection hidden, and checks opponents' true projections. See [DESIGN.md](DESIGN.md) for every decision and why.

## Built with
Python · Yahoo Fantasy API · Claude agents and skills · GitHub Codespaces
