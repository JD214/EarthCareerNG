<!-- Logo: export the "Primary logo (dark)" artboard as a PNG, add it to the repo as logo.png, and keep this line -->
<p align="center"><img src="logo.png" alt="EarthCareerNG logo" width="720"></p>

# EarthCareerNG

**Drive the real world, in career mode.**

EarthCareerNG is a career mod for BeamNG.drive built on [BeamNG.Earth](https://github.com/TecnaGamer/BeamNG.Earth), the mod that streams the real world into the game at 1:1 scale. You pick a real US town as your home base, start with $500 and a beat-up car, and work your way up: hauling freight, moving cars between dealers, running bus routes and taking HotShot loads between real towns, hundreds of miles apart on real roads.

Everything runs in **Freeroam**. There's no vanilla career mode involved: the whole career is a HUD app plus a few Lua extensions, so it works anywhere BeamNG.Earth does.

**Current version:** v1.1.5 · tested on BeamNG.drive 0.40

---

## Requirements

- **BeamNG.drive** 0.39 or newer (tested on 0.40.4)
- **[BeamNG.Earth](https://github.com/TecnaGamer/BeamNG.Earth)**, installed and working, with its companion server running (it supplies the map tiles, GPS routing and online search)

## Install

1. Download `earth_career.zip` from the [Releases](../../releases) page.
2. Put the zip in your BeamNG mods folder **without unzipping it**:
   `%LOCALAPPDATA%\BeamNG\BeamNG.drive\current\mods\`
3. Start BeamNG.drive and load the **BeamNG.Earth** map in **Freeroam**.
4. Press **Esc** → **UI Apps** → **Add app** → **Earth Career**. Place and resize the panel wherever you like.
5. Pick or create a profile, teleport to your home town with Earth's map (**M**), and hit **Start my career here**.

**Updating:** replace the old zip with the new one. Your saves live in `settings/earthCareer/profiles/` and carry over.

---

## Features

### Career & profiles
- Several profiles, each its own career (money, cars, home town, progress), chosen every time the mod loads
- Start with $500 and a beat-up Soliad Wendover, then earn XP and money to level up and unlock bigger jobs
- Pick any real US town as your home base, and move it later
- A first-start tip walks you through your first upgrade

### Jobs: the Freight Market
- A job board on a US map, with every job drawn from pickup to destination between real towns
- Three tiers: **Local** (0–75 mi), **Regional** (75–250 mi, Lv 5) and **Long Haul** (250+ mi, coast to coast, Lv 12)
- **Cars:** courier runs, rideshare (tips for smooth driving), dealer-to-dealer car transfers (car provided) and long-haul car jobs
- **HotShot Trucking:** a pickup bed carries a partial load, and any vehicle with a trailer carries a full one
- **Freight:** semi and trailer, owned or rented
- **Bus:** city routes with real stops, commuter express, intercity coach and dealer bus transfers (pick the bus)
- **🔥 Hot jobs:** demand surges in random towns that boost pay and XP
- **Custom dispatch (Lv 15):** book your own load with a live price quote
- **Rentals (Lv 5):** rent the exact semi, bus or trailer for a job
- Cargo damage, urgent deadlines and fragile loads, with a pay report on every delivery (cargo damage can be switched off)

### Map & GPS
- A Google Maps-style map of the real world: street, satellite or dark view
- Search towns (works offline) and addresses, or drop a pin anywhere and navigate there
- Real-road routing through BeamNG.Earth, with turn-by-turn directions ("Continue on I-69 · 23 mi"), arrival time and off-route warnings
- Add stops for rest areas, gas, food and truck stops
- A speedometer with the road's speed limit
- "Welcome to [State]" signs when you cross a state line

### Garage & dealers
- **New car dealer** through the game's vehicle selector: spawn it, then pay the bill or put it back
- **Used lot** with marked-up prices that restocks as you deliver
- **Trailers:** buy, spawn behind your truck and hitch up
- **Parts:** change parts in the game's parts menu and pay for them
- **Fuel:** refuel from the Garage, or pull into one of BeamNG.Earth's real gas stations and pay pump price
- **Rental cars**, billed by the day
- A **vehicle lock** keeps you in cars you own (you can still get out and walk), with a setting to turn it off

### Crashes & insurance
- Crash damage goes on a repair bill: pay it, file an insurance claim for the deductible, or scrap the car
- Insurance can fix even a totaled car
- A **Map bug** button resets the car for free when BeamNG.Earth glitches (falling through the ground, invisible walls)
- An optional **cheap insurance** setting caps every claim at $25

### Bank
- Loans with daily or weekly payment plans and real interest
- Missed payments run overdue fees, and part of your job pay goes to the debt

### Progress & stats
- **25 achievements** with cash and XP rewards (some hidden)
- **States visited** map: +150 XP for each new state
- **Town discovery:** drive into a town for 5–10 XP, shown as dots on the map
- Career stats with a breakdown by job type

### Teleport lock
- Teleporting with Earth's map asks what you want to do: go back home (free), stay for a visit, or move your home base (paid)
- Return to your last saved spot when you resume, and the career remembers the rental or dealer car you were driving

### Quality of life
- **Hide / show** the panel: it shrinks to a small pill with your money and level, and pop-ups still show
- Settings for the vehicle lock, crash pop-ups, cheap insurance, cargo damage, the teleport lock, return to last save and mod vehicles in rentals

---

## Console commands

Open the console with `~`:

| Command | What it does |
|---|---|
| `earthCareer_main.debugAddMoney(5000)` | Add money |
| `earthCareer_main.debugAddXp(500)` | Add XP |
| `earthCareer_main.resetCareer()` | Reset the current profile |
| `earthCareer_main.switchProfile()` | Save and go back to the profile picker |
| `earthCareer_jobs.refreshMarket()` | Refresh the job board |
| `earthCareer_jobs.iAmTheDispatcher()` | Unlock Custom dispatch at any level (normally Lv 15) |

---

## Known issues

- **Map search for addresses and businesses** depends on BeamNG.Earth's online search. If that service is down, town search still works offline and the Gas button falls back to stations loaded near you.
- **Crashes at highway speed** (`0x00000001`) have been traced to BeamNG.Earth loading terrain, not to this mod. Lots of mods loaded at once can make it worse.

## Credits

- Created by **THEDTWFLYER**
- Co-developed with **Claude** (Anthropic), which helped design and write the code
- Built on **[BeamNG.Earth](https://github.com/TecnaGamer/BeamNG.Earth)**. The adapter approach follows [Earth Enduro](https://github.com/MadMerick01/BeamNG-Earth-Enduro).
- Map tiles through BeamNG.Earth's companion server: EOX IT Services (maps.eox.at), data © OpenStreetMap contributors
- Search: Photon by komoot; routing: OSRM on OpenStreetMap (both through BeamNG.Earth)
- US towns: [kelvins/US-Cities-Database](https://github.com/kelvins/US-Cities-Database) (MIT); city populations: [plotly/datasets](https://github.com/plotly/datasets)
- State outlines: US Census (public domain), via [PublicaMundi/MappingAPI](https://github.com/PublicaMundi/MappingAPI) and BeamNG.Earth

EarthCareerNG is a fan-made mod and isn't affiliated with or endorsed by BeamNG GmbH.
