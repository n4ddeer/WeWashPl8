# WEWASHPl8

A dishwashing arcade game written in C on top of CProcessing.

Scrub dirt off plates with the sponge, rinse them at the faucet, and keep pace as the daily quota climbs. Earnings feed a shop where upgrades buy you a chance at surviving the later days.

## Gameplay

- **Day loop** — each day sets a plate quota against a timer; clear it to advance
- **Economy** — washing earns money, money buys upgrades
- **Progression** — shop, upgrades, leaderboard, tutorial, settings and credits screens

## Layout

```
src/
  core/        game states: splash, main menu, game, settings, leaderboard, credits, game over
  entities/    plate, sponge, dirt, faucet, bubblegun, roomba
  systems/     day, money, shop, upgrades, soap, timer, tutorial, sounds, settings
  utils/       debug overlay, image and font loading
  vfx/         bubbles, confetti, discoball
Extern/
  CProcessing/ vendored framework
```

Screens are driven through CProcessing's `CP_Engine_SetNextGameState`, each exposing Init / Update / Exit.

## My contribution

I'm n4ddeer, one of the five team members. I worked on:

- `src/entities/faucet.c`: the faucet and stream ability. Press W and the faucet rotates and fires a stream of droplets. Each droplet hit lowers the target's opacity (area-of-effect), with a cooldown timer and upgrades that can shorten it.
- `src/systems/tutorial.c`: a step-by-step tutorial that walks you up to the start of day 1.
- Game UI for the main menu, settings and game screens: fonts, layout, colour names and small touches like the leaderboard back button tooltip.
- Cleanup: renamed functions across the solution, added `#pragma once`, and commented my files.

My commits: https://github.com/n4ddeer/WeWashPl8/commits/master/?author=n4ddeer

## Build

Open `Game_Project.sln` in Visual Studio and build. CProcessing is vendored under `Extern/`, so there is nothing else to fetch.

## Team

Built by a five-person team: limlz, junwxn, n4ddeer, mightbedan, choonzs.

---

Coursework project at DigiPen Institute of Technology Singapore. Source files carry DigiPen copyright headers.
