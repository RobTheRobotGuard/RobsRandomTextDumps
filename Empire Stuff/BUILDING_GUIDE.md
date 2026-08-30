# Empire Progressive Buildings: Building Guide

A reference for all 143 buildings currently implemented in the mod, grouped by upgrade chain and listed in tier order. This reflects the *actual implemented* defs (real defNames, current label/desc text) rather than the original design targets in `BuildingConcepts.MD`; the two can drift as implementation progresses.

All names/descriptions live in `Empire Progressive Buildings/Languages/English/DefInjected/FactionColonies.BuildingFCDef/` (one file per chain) so they can be edited without touching the mechanical defs in `Defs/Chains/`. Regenerate this guide and the DefInjected files together with `Tools/build_docs.py` after adding or editing buildings.

Legend: **Tier** = position in the chain's upgrade path (I = base building). **Cost** = silver to build. **Upkeep** = silver/day at `postRework` scale. ⚔️ = military-classified building (uses military cost/upkeep multipliers).

**DLC-gated chains:** a chain header tagged (Odyssey), (Anomaly), or (Royalty) means every building in that chain has `MayRequire` set to that DLC's package ID. Without the DLC active, those buildings will not appear in the settlement build menu at all, this is intentional, not a bug. Currently: Chain 11 (Gravtech Ascendancy) needs Odyssey, Chain 21 (Reliquary) needs Anomaly, Chain 22 (Psychic Conclave) needs Royalty.

**Mod-gated chains:** Chain 8 (Route Spur) is tagged (Routes & Resources only) and needs the optional Empire Refactored: Routes & Resources mod active. Unlike the DLC chains above, this isn't done with `MayRequire` on the individual defs, the whole `Compat/RoutesAndResources/Defs/` folder is only loaded in the first place via `LoadFolders.xml`'s `IfModActive="Matathias.Empire.SupplyChain"` conditional mount, so without that mod active Chain 8's defs are never parsed at all. Same practical effect, gated at the folder level instead of the def level.

Every other chain works with just the base game plus Empire Refactored.

**Cities & Fields settlement types:** each chain below has a note on where its buildings can be built if the optional Empire Refactored: Cities & Fields mod is active. Without Cities & Fields, every building in this mod is buildable in any settlement type regardless of what's noted here; the restriction only exists in `Compat/CitiesAndFields/Patches/SettlementTypeRestrictions.xml`, which only loads when that mod is active. A chain with no note is unrestricted even with Cities & Fields installed.

---

## Chain 1: Watch & Warning

| Tier | Name | Tech Level | Cost | Upkeep | Description |
|---|---|---|---|---|---|
| 1 | **Watchfire Pyre** ⚔️ | Neolithic | 300 | 8 | A simple Pyre which is ignited the moment danger is spotted on the horizon. |
| 2 | **Signal Tower** ⚔️ | Medieval | 1000 | 30 | A manned watchtower with a rotating crew for 24/7 coverage whom are able to relay warning of an approaching force well before it arrives. |
| 3 | **Beacon Network** ⚔️ | Industrial | 2400 | 95 | A chain of linked signal beacons ringing the settlement, giving the garrison time to man the walls before any raid arrives. |
| 3 | **Informants' Ring** ⚔️ | Industrial | 2600 | 105 | A quiet network of paid informants and turned scouts among the local threats, who tip off the settlement long before trouble starts. |
| 4 | **Counterintelligence Bureau** ⚔️ | Spacer | 5800 | 230 | A dedicated bureau that roots out hostile scouts and saboteurs before they can report back, starving enemies of the intelligence they need to strike. |
| 4 | **Integrated Sensor Grid** ⚔️ | Spacer | 5500 | 210 | An automated perimeter of motion and thermal sensors feeding a central war room, watching every approach at once. |
| 5 | **Precognition Array** ⚔️ | Archotech | 16000 | 520 | An archotech array that reads the faintest ripples of coming violence, warning the settlement of threats before they've even been decided upon. |

**Branch points:**
- **Signal Tower** upgrades into: Beacon Network, Informants' Ring

---

## Chain 2: Public Works

| Tier | Name | Tech Level | Cost | Upkeep | Description |
|---|---|---|---|---|---|
| 1 | **Carpenter's Yard** | Undefined | 400 | 10 | A modest timber yard where a handful of carpenters keep the settlement's tools and scaffolding in working order. |
| 2 | **Masons' Lodge** | Medieval | 1100 | 35 | A guild lodge of trained masons and surveyors who plan projects properly before the first stone is laid. |
| 3 | **Engineering Corps** | Industrial | 2600 | 115 | A standing corps of engineers and heavy equipment operators, able to throw up sound structures at remarkable speed. |
| 3 | **Quartermaster's Depot** | Industrial | 2600 | 100 | A depot run by a shrewd quartermaster who wastes nothing, stretching every load of lumber and stone further and keeping upkeep lean. |
| 4 | **Prefabrication Plant** | Spacer | 6000 | 250 | A modular plant churning out prefabricated wall and floor sections, ready to be assembled on site in a fraction of the time. |
| 5 | **Self-Assembling Foundry** | Ultra | 14000 | 460 | A foundry of construction drones that raise and maintain structures with almost no waste and almost no idle hands. |

**Branch points:**
- **Masons' Lodge** upgrades into: Engineering Corps, Quartermaster's Depot

---

## Chain 3: Civic Sanitation

| Tier | Name | Tech Level | Cost | Upkeep | Description |
|---|---|---|---|---|---|
| 1 | **Village Wellhouse** | Neolithic | 350 | 8 | A covered well and washhouse that keeps drinking water clean and gives workers somewhere decent to gather. |
| 2 | **Public Bathhouse** | Medieval | 1000 | 40 | A proper public bathhouse, keeping the workforce clean, rested, and considerably less prone to grumbling. |
| 3 | **Sewer Network** | Industrial | 2400 | 100 | A proper sewer network beneath the settlement, letting it pack in far more workers without the place turning into a health hazard. |
| 3 | **Public Welfare Board** | Industrial | 2400 | 115 | A welfare board that looks after overworked labourers, softening the toll of long shifts even if it costs a bit more to keep them on. |
| 4 | **Integrated Utility Grid** | Spacer | 5800 | 240 | A unified grid of water, waste, and climate systems, letting the settlement house and support many more workers in comfort. |
| 5 | **Homeostasis Core** | Ultra | 13000 | 430 | A self-balancing life-support core that keeps every habitat block at a perfect equilibrium of air, water, and comfort. |

**With Cities & Fields active:** buildable only in City or any rural settlement (Farming Hamlet, Mining Camp, Lumber Camp, Ranch, Chemfuel Refinery, Herbalist Camp, or Power Plant).

**Branch points:**
- **Public Bathhouse** upgrades into: Sewer Network, Public Welfare Board

---

## Chain 4: Faith & Culture

| Tier | Name | Tech Level | Cost | Upkeep | Description |
|---|---|---|---|---|---|
| 1 | **Ancestor Shrine** | Neolithic | 300 | 6 | A small shrine of carved totems where the settlement honours those who came before. |
| 2 | **Temple** | Medieval | 1000 | 35 | A proper temple with a resident clergy, giving the settlement's faith a permanent home. |
| 3 | **Grand Cathedral** | Medieval | 2800 | 120 | A soaring cathedral built by generations of devoted hands, its presence alone lifting the mood of the whole settlement. |
| 3 | **Inquisitorial Seat** | Industrial | 2600 | 110 | A seat of strict doctrine and discipline, binding the faithful to the settlement through order rather than comfort. |
| 3 | **Philosophers' Portico** | Industrial | 2600 | 105 | A colonnaded portico where scholars debate the nature of things, turning devotion into disciplined inquiry. |
| 4 | **Transcendence Spire** | Ultra | 15000 | 490 | A spire that fuses devotion, discipline, and inquiry into a single towering institution, guiding the settlement's spirit and mind alike. |

**Branch points:**
- **Temple** upgrades into: Grand Cathedral, Inquisitorial Seat, Philosophers' Portico

---

## Chain 5: Levy & Muster

| Tier | Name | Tech Level | Cost | Upkeep | Description |
|---|---|---|---|---|---|
| 1 | **Muster Field** ⚔️ | Undefined | 400 | 10 | An open field where local levies gather and drill before marching out. |
| 2 | **Levy Hall** ⚔️ | Medieval | 1200 | 45 | A hall where the settlement's able-bodied register for service, letting mobilization happen far faster than an open field ever could. |
| 3 | **Conscription Bureau** ⚔️ | Industrial | 2800 | 125 | A bureau with the authority to conscript en masse, swelling the ranks at the cost of settlement morale and free labour. |
| 3 | **Officer Academy** ⚔️ | Industrial | 3000 | 135 | An academy that trains proper officers, turning raw levies into a force that fights, and reorganizes, far more effectively. |
| 4 | **War Ministry** ⚔️ | Spacer | 6500 | 285 | A full ministry of war, coordinating recruitment, training, and deployment as one unified machine. |
| 5 | **Total Mobilization Command** ⚔️ | Ultra | 16000 | 560 | A command centre that puts the entire settlement on a war footing, ready to field armies at a scale nothing else can match. |

**Branch points:**
- **Levy Hall** upgrades into: Conscription Bureau, Officer Academy

---

## Chain 6: Mercenary Compact

| Tier | Name | Tech Level | Cost | Upkeep | Description |
|---|---|---|---|---|---|
| 1 | **Sellsword Post** ⚔️ | Undefined | 500 | 15 | A rough post where wandering sellswords can be hired on short notice. |
| 2 | **Free Company Barracks** ⚔️ | Medieval | 1300 | 50 | A standing barracks for a free company, keeping hired blades fed, equipped, and considerably harder to kill. |
| 3 | **Contract Brokerage** ⚔️ | Industrial | 2800 | 110 | A brokerage that negotiates every contract down to the letter, turning mercenary work into a reliable revenue stream. |
| 3 | **Condottieri Field Hospital** ⚔️ | Industrial | 2800 | 125 | A dedicated field hospital for hired guns, drastically cutting down on how many come back in a body bag. |
| 4 | **PMC Headquarters** ⚔️ | Spacer | 6500 | 280 | A proper private military corporation headquarters, running mercenary contracts as a disciplined, profitable business. |
| 5 | **Corporate War Machine** ⚔️ | Ultra | 17000 | 600 | A sprawling military-industrial complex that fields, arms, and heals mercenary forces on an industrial scale. |

**With Cities & Fields active:** buildable only in City.

**Branch points:**
- **Free Company Barracks** upgrades into: Condottieri Field Hospital, Contract Brokerage

---

## Chain 7: Tithe & Treasury

| Tier | Name | Tech Level | Cost | Upkeep | Description |
|---|---|---|---|---|---|
| 1 | **Tally House** | Undefined | 400 | 12 | A small counting house where a single clerk keeps track of what's owed. |
| 2 | **Exchequer** | Medieval | 1200 | 45 | A formal exchequer with trained clerks, turning tax collection into a proper administrative process. |
| 3 | **Revenue Service** | Industrial | 2800 | 125 | An aggressive revenue service that squeezes every last coin owed, at the cost of some public goodwill. |
| 3 | **Royal Mint** | Industrial | 3000 | 120 | A royal mint that strikes coin of exceptional purity, making every tithe paid worth that much more. |
| 4 | **Central Bank** | Spacer | 6500 | 270 | A central bank overseeing the settlement's entire fiscal apparatus, from taxation to tithe to reserves. |
| 5 | **Algorithmic Treasury** | Ultra | 15000 | 490 | A treasury run by predictive algorithms, optimizing tax policy and tithe collection down to the last decimal. |

**With Cities & Fields active:** buildable only in City.

**Branch points:**
- **Exchequer** upgrades into: Revenue Service, Royal Mint

---

## Chain 8: Route Spur (Routes & Resources only)

| Tier | Name | Tech Level | Cost | Upkeep | Description |
|---|---|---|---|---|---|
| 1 | **Pack Trail** | Neolithic | 350 | 8 | A worn pack trail linking the settlement to its neighbours, walked by mule trains and messengers alike. |
| 2 | **Cobbled Road** | Medieval | 1000 | 35 | A proper cobbled road, letting carts move goods between settlements far faster than any dirt trail. |
| 3 | **Fortified Caravanserai** ⚔️ | Industrial | 2400 | 100 | A fortified caravanserai giving merchant trains somewhere safe to rest and resupply along the route. |
| 3 | **Rail Spur** | Industrial | 2600 | 115 | A rail spur carrying bulk freight at a scale no cart could match. |
| 4 | **Maglev Line** | Spacer | 6200 | 260 | A maglev line moving freight between settlements at speeds no wheeled convoy could ever reach. |
| 5 | **Matter Relay** | Ultra | 15000 | 510 | A matter relay that transmits cargo between settlements almost instantly, rendering distance nearly irrelevant to trade. |

**Branch points:**
- **Cobbled Road** upgrades into: Rail Spur, Fortified Caravanserai

---

## Chain 9: Colonial Office

| Tier | Name | Tech Level | Cost | Upkeep | Description |
|---|---|---|---|---|---|
| 1 | **Surveyor's Post** | Undefined | 500 | 15 | A small post from which surveyors chart the surrounding land for future settlement. |
| 2 | **Land Office** | Medieval | 1300 | 45 | A formal land office handling claims and grants, smoothing the process of both founding and upgrading settlements. |
| 3 | **Colonial Office** | Industrial | 3000 | 135 | A colonial office dedicated to expansion, cutting the cost and friction of founding new settlements across the Empire. |
| 3 | **Urban Planning Bureau** | Industrial | 3200 | 140 | A planning bureau that packs every settlement level with as much infrastructure as it can possibly hold. |
| 4 | **Ministry of Expansion** | Spacer | 7000 | 290 | A ministry uniting settlement founding and settlement growth under one roof, expanding the Empire both outward and upward. |
| 5 | **Terraforming Authority** | Archotech | 18000 | 610 | An authority with the power to reshape whole tiles for settlement, making expansion nearly frictionless. |

**Branch points:**
- **Land Office** upgrades into: Colonial Office, Urban Planning Bureau

---

## Chain 10: Apprenticeship

| Tier | Name | Tech Level | Cost | Upkeep | Description |
|---|---|---|---|---|---|
| 1 | **Apprentice Hall** | Undefined | 400 | 10 | A modest hall where apprentices learn a trade under a single overworked master. |
| 2 | **Journeyman's Guild** | Medieval | 1200 | 40 | A guild hall for journeymen tradesfolk, sharing techniques and tools across the whole workforce. |
| 3 | **Labour Exchange** | Industrial | 2500 | 100 | A bustling exchange matching willing hands to open jobs quickly and cheaply, favouring volume over polish. |
| 3 | **Vocational Institute** | Industrial | 2800 | 125 | A rigorous vocational institute that trains fewer workers, but far more capable ones. |
| 4 | **Efficiency Directorate** | Spacer | 6000 | 255 | A directorate that studies and optimizes labour across the settlement, squeezing more out of every shift without burning workers out. |
| 5 | **Neural Skill-Loom** | Ultra | 15000 | 510 | A neural skill-loom that weaves expertise directly into workers' minds, turning novices into masters overnight. |

**Branch points:**
- **Journeyman's Guild** upgrades into: Labour Exchange, Vocational Institute

---

## Chain 11: Gravtech Ascendancy (Odyssey)

| Tier | Name | Tech Level | Cost | Upkeep | Description |
|---|---|---|---|---|---|
| 1 | **Gravitic Survey Post** | Industrial | 2000 | 85 | A survey post studying the local gravtech deposits, mapping out how best to exploit them. |
| 2 | **Gravitic Foundry** | Spacer | 5000 | 225 | A foundry harnessing gravitic fields directly in its refining process, boosting yield well beyond conventional extraction. |
| 3 | **Mass Fabricator** | Spacer | 6500 | 275 | A fabricator that uses gravitic compression to condense raw ore into refined material at a startling rate. |
| 3 | **Resonance Laboratory** | Spacer | 6000 | 255 | A laboratory studying gravitic resonance patterns, unlocking both greater yield and genuine scientific insight. |
| 4 | **Singularity Yard** | Ultra | 16000 | 560 | A yard built around a stabilized gravitic singularity, turning raw ore and insight alike into resources at an industrial scale. |

**With Cities & Fields active:** buildable only in Mining Camp or Chemfuel Refinery.

**Branch points:**
- **Gravitic Foundry** upgrades into: Resonance Laboratory, Mass Fabricator

---

## Chain 12: Memorial & Triumph

| Tier | Name | Tech Level | Cost | Upkeep | Description |
|---|---|---|---|---|---|
| 1 | **Cairn of the Fallen** | Neolithic | 300 | 6 | A simple cairn of stones raised for those lost in battle, easing the settlement's grief. |
| 2 | **Hall of Heroes** | Medieval | 1000 | 35 | A hall lined with the names and deeds of fallen soldiers, honouring loss and celebrating victory alike. |
| 3 | **Triumphal Arch** | Medieval | 2600 | 100 | A grand arch raised to commemorate victories, turning every hard-won battle into a lasting boost to morale. |
| 3 | **Veterans' Bureau** | Industrial | 2500 | 110 | A bureau dedicated to supporting veterans and grieving families, softening the settlement's every loss. |
| 4 | **Pantheon of Service** | Spacer | 6000 | 240 | A pantheon honouring every soul who has served, blunting the sting of loss and magnifying the joy of triumph. |
| 5 | **Eternal Flame** | Ultra | 14000 | 460 | An eternal flame that never gutters, a permanent symbol binding the settlement together through every defeat and victory. |

**Branch points:**
- **Hall of Heroes** upgrades into: Veterans' Bureau, Triumphal Arch

---

## Chain 13: Arena & Spectacle

| Tier | Name | Tech Level | Cost | Upkeep | Description |
|---|---|---|---|---|---|
| 1 | **Wrestling Pit** | Neolithic | 350 | 8 | A dirt pit where locals test their strength against one another for the crowd's amusement. |
| 2 | **Fighting Pits** | Medieval | 1100 | 40 | A proper ring of fighting pits with regular bouts, drawing crowds eager to watch and wager. |
| 3 | **Colosseum** | Medieval | 2800 | 115 | A colosseum of blood sport, keeping the populace's darker appetites sated at the cost of a little loyalty. |
| 3 | **Grand Stadium** | Industrial | 2800 | 120 | A grand stadium hosting organised sport rather than bloodshed, packing in crowds for a clean and profitable spectacle. |
| 4 | **Broadcast Spectacle Network** | Spacer | 6000 | 250 | A broadcast network beaming every match across the settlement and beyond, turning spectacle into a steady source of revenue. |
| 5 | **Interstellar Circuit** | Ultra | 14000 | 470 | A stop on the interstellar sporting circuit, drawing spectators and coin from across known space. |

**With Cities & Fields active:** buildable only in City.

**Branch points:**
- **Fighting Pits** upgrades into: Grand Stadium, Colosseum

---

## Chain 14: Assize & Gaol

| Tier | Name | Tech Level | Cost | Upkeep | Description |
|---|---|---|---|---|---|
| 1 | **Moot Stone** | Neolithic | 300 | 5 | A worn standing stone where elders gather to settle disputes. |
| 2 | **Circuit Assize** | Medieval | 1000 | 35 | A travelling assize that holds regular court, giving the settlement's law a consistent and predictable hand. |
| 3 | **House of Correction** | Industrial | 2500 | 105 | A house of correction that favours rehabilitation over punishment, returning reformed workers to the settlement. |
| 3 | **Penal Colony** | Industrial | 2600 | 100 | A hard penal colony that puts convicts straight to work, cheap and plentiful but resentful of their lot. |
| 4 | **High Court** | Spacer | 6000 | 245 | A high court whose rulings carry real weight, giving the settlement's law both teeth and legitimacy. |
| 5 | **Arbiter Core** | Archotech | 15000 | 500 | An impartial archotech arbiter that renders judgment instantly and without bias, keeping the settlement's law airtight. |

**With Cities & Fields active:** buildable only in City.

**Branch points:**
- **Circuit Assize** upgrades into: House of Correction, Penal Colony

---

## Chain 15: Signal & Post

| Tier | Name | Tech Level | Cost | Upkeep | Description |
|---|---|---|---|---|---|
| 1 | **Runners' Post** | Undefined | 350 | 8 | A post of fast runners who relay messages and orders between settlement offices. |
| 2 | **Semaphore Line** | Medieval | 1000 | 35 | A line of semaphore towers relaying messages across the settlement in minutes rather than hours. |
| 3 | **Field Signal Corps** ⚔️ | Industrial | 2600 | 110 | A dedicated military signal corps, keeping orders moving fast and units coordinated in the field. |
| 3 | **Telegraph Office** | Industrial | 2500 | 105 | A telegraph office wiring the settlement's administration directly together, letting policy move at the speed of the signal. |
| 4 | **Planetary Comms Array** | Spacer | 6200 | 260 | A planetary communications array unifying civil and military signal traffic into one instantaneous network. |
| 5 | **Quantum Entanglement Link** | Ultra | 15000 | 510 | A quantum entanglement link giving the settlement instantaneous, uninterceptable communication with the rest of the Empire. |

**Branch points:**
- **Semaphore Line** upgrades into: Telegraph Office, Field Signal Corps

---

## Chain 16: Scrap & Reclamation

| Tier | Name | Tech Level | Cost | Upkeep | Description |
|---|---|---|---|---|---|
| 1 | **Midden Heap** | Neolithic | 300 | 5 | A sorted refuse heap where usable scrap is picked out by hand before the rest rots down. |
| 2 | **Scrapyard** | Medieval | 950 | 30 | A proper scrapyard sorting salvage into usable metal and burnable waste. |
| 3 | **Pyrolysis Works** | Industrial | 2400 | 105 | A pyrolysis plant that cooks waste down into chemfuel and reclaimed power, turning refuse into an energy source. |
| 3 | **Reclamation Plant** | Industrial | 2400 | 100 | A reclamation plant that strips salvage down to raw material and reusable fabric, feeding it back into the settlement's supply. |
| 4 | **Molecular Reclaimer** | Spacer | 6000 | 250 | A reclaimer that breaks salvage down to the molecular level, extracting metal and fuel with almost nothing left over. |
| 5 | **Closed Matter Loop** | Ultra | 14500 | 480 | A closed-loop matter reclaimer that recycles nearly everything the settlement discards back into useful material. |

**With Cities & Fields active:** buildable only in Mining Camp or Chemfuel Refinery.

**Branch points:**
- **Scrapyard** upgrades into: Reclamation Plant, Pyrolysis Works

---

## Chain 17: Remount & Column

| Tier | Name | Tech Level | Cost | Upkeep | Description |
|---|---|---|---|---|---|
| 1 | **Remount Paddock** ⚔️ | Undefined | 400 | 10 | A paddock of fresh mounts kept ready so messengers and levies can move out without delay. |
| 2 | **Campaign Stables** ⚔️ | Medieval | 1200 | 45 | Proper campaign stables that keep a standing cavalry force fed, shod, and ready to ride out on short notice. |
| 3 | **Baggage Train Depot** ⚔️ | Industrial | 2600 | 110 | A well-stocked baggage train that keeps soldiers supplied and wounded properly treated in the field. |
| 3 | **Light Horse Regiment** ⚔️ | Industrial | 2700 | 115 | A fast light-horse regiment that strikes and withdraws before the enemy can properly respond. |
| 4 | **Mechanized Column** ⚔️ | Spacer | 6400 | 275 | A mechanized column of armoured transports, moving troops fast while keeping them supplied and protected. |
| 5 | **Rapid Deployment Wing** ⚔️ | Ultra | 16000 | 550 | A rapid deployment wing capable of getting a fully equipped force into the field almost instantly. |

**Branch points:**
- **Campaign Stables** upgrades into: Light Horse Regiment, Baggage Train Depot

---

## Chain 18: Embassy Row

| Tier | Name | Tech Level | Cost | Upkeep | Description |
|---|---|---|---|---|---|
| 1 | **Envoy's Lodge** | Undefined | 450 | 12 | A simple lodge where travelling envoys can be received and hosted. |
| 2 | **Guest Hall** | Medieval | 1200 | 42 | A dedicated guest hall for foreign dignitaries, making the settlement a proper stop on the diplomatic circuit. |
| 3 | **Foreign Chancellery** | Industrial | 2800 | 120 | A foreign chancellery building lasting alliances, buying goodwill that keeps threats at arm's length. |
| 3 | **Trade Legation** | Industrial | 2700 | 115 | A trade legation negotiating favourable terms with every merchant that passes through. |
| 4 | **Foreign Ministry** | Spacer | 6500 | 270 | A full foreign ministry running trade and diplomacy together as one coordinated arm of the Empire. |
| 5 | **Interstellar Consulate** | Ultra | 15500 | 520 | An interstellar consulate representing the Empire's interests across known space, equal parts embassy and trading house. |

**With Cities & Fields active:** buildable only in City.

**Branch points:**
- **Guest Hall** upgrades into: Trade Legation, Foreign Chancellery

---

## Chain 19: Harbour Works

| Tier | Name | Tech Level | Cost | Upkeep | Description |
|---|---|---|---|---|---|
| 1 | **Fishing Weir** | Neolithic | 300 | 6 | A simple woven weir strung across a coastal shallow, funnelling fish in on the tide. |
| 2 | **Stone Quay** | Medieval | 1000 | 35 | A stone quay giving boats somewhere proper to dock and unload their catch. |
| 3 | **Deepwater Fishery** | Industrial | 2400 | 100 | A deepwater fishery with proper trawling boats, bringing in far more than a weir or a quay ever could. |
| 3 | **Commercial Harbour** | Industrial | 2600 | 110 | A commercial harbour drawing merchant vessels from up and down the coast. |
| 4 | **Deepwater Port** | Spacer | 6000 | 250 | A deepwater port capable of berthing far larger vessels, combining a strong catch with strong trade. |
| 5 | **Orbital Tether Port** | Ultra | 15000 | 500 | A port anchoring an orbital tether out over the water, moving cargo and catch alike straight up into orbit. |

**Branch points:**
- **Stone Quay** upgrades into: Deepwater Fishery, Commercial Harbour

---

## Chain 20: Marcher Fort

| Tier | Name | Tech Level | Cost | Upkeep | Description |
|---|---|---|---|---|---|
| 1 | **Boundary Cairn** ⚔️ | Neolithic | 300 | 6 | A cairn marking the settlement's frontier, raised on rising ground for visibility. |
| 2 | **Marcher Tower** ⚔️ | Medieval | 1100 | 40 | A tower manned by frontier marchers, watching the high ground and holding it if trouble comes. |
| 3 | **Border Garrison** ⚔️ | Industrial | 2700 | 120 | A standing garrison holding the frontier, trading raw terrain advantage for a proper permanent force. |
| 3 | **Cliff Fort** ⚔️ | Medieval | 2600 | 110 | A fort cut into the cliffside, using the terrain itself as the first line of defence. |
| 4 | **Bastion Complex** ⚔️ | Spacer | 6500 | 280 | A complex of bastions and interlocking fields of fire, turning the high frontier into a genuine fortress line. |
| 5 | **Mountain Citadel** ⚔️ | Ultra | 16500 | 570 | A citadel carved into the mountain itself, all but impossible to root out once it's built. |

**Branch points:**
- **Marcher Tower** upgrades into: Cliff Fort, Border Garrison

---

## Chain 21: Reliquary (Anomaly)

| Tier | Name | Tech Level | Cost | Upkeep | Description |
|---|---|---|---|---|---|
| 1 | **Cabinet of Oddities** | Medieval | 800 | 25 | A locked cabinet holding a handful of strange curios that scholars can't quite explain. |
| 2 | **Sealed Reliquary** | Industrial | 2200 | 95 | A sealed reliquary properly warded against whatever it is that's kept inside. |
| 3 | **Containment Laboratory** | Industrial | 2800 | 125 | A proper containment laboratory, letting researchers study what's inside the reliquary without letting it out. |
| 3 | **Void Shrine** | Industrial | 2600 | 110 | A shrine raised to whatever watches from beyond, binding the settlement's faith to something stranger than the old gods. |
| 4 | **Void Sanctum** | Ultra | 15000 | 520 | A sanctum fusing study and worship of the void into one institution, drawing knowledge and devotion from the same unsettling source. |

**Branch points:**
- **Sealed Reliquary** upgrades into: Containment Laboratory, Void Shrine

---

## Chain 22: Psychic Conclave (Royalty)

| Tier | Name | Tech Level | Cost | Upkeep | Description |
|---|---|---|---|---|---|
| 1 | **Meditation Grove** | Neolithic | 400 | 8 | A quiet grove set aside for meditation, calming minds and sharpening focus alike. |
| 2 | **Psychic Antenna** | Industrial | 1400 | 55 | A psychic antenna amplifying and focusing the settlement's collective mental discipline. |
| 3 | **Dominion Spire** | Spacer | 3000 | 130 | A spire that projects quiet psychic authority over the settlement, binding loyalty through subtle dominance. |
| 3 | **Harmony Choir** | Industrial | 2700 | 115 | A choir of psychically attuned singers whose harmonies settle the whole settlement's mood. |
| 4 | **Psychic Conclave** | Spacer | 6500 | 270 | A conclave of psychically gifted advisors, guiding the settlement's mood and loyalty as one unified will. |
| 5 | **Noosphere Anchor** | Archotech | 16000 | 540 | An anchor point into the noosphere itself, letting the settlement's collective mind reach further than any single psychic ever could. |

**Branch points:**
- **Psychic Antenna** upgrades into: Harmony Choir, Dominion Spire

---

## Chain 23: Physic Garden

| Tier | Name | Tech Level | Cost | Upkeep | Description |
|---|---|---|---|---|---|
| 1 | **Herb Plot** | Neolithic | 300 | 6 | A small plot of medicinal herbs tended by hand. |
| 2 | **Physic Garden** | Medieval | 1000 | 35 | A cultivated physic garden run by a trained herbalist, producing reliable medicine and a bit of comfort besides. |
| 3 | **Medicinal Distillery** | Industrial | 2500 | 105 | A distillery producing medicine in real quantity, well beyond what any garden could manage alone. |
| 3 | **Field Infirmary** | Industrial | 2500 | 110 | A field infirmary staffed for trauma care, keeping the wounded — soldier and mercenary alike — alive and recovering faster. |
| 4 | **Pharmaceutical Works** | Spacer | 6000 | 250 | A full pharmaceutical works combining bulk production with genuine clinical care. |
| 5 | **Vitae Synthesis Plant** | Ultra | 14500 | 490 | A synthesis plant that manufactures advanced medicine from raw chemical stock, faster and cleaner than any garden or distillery. |

**Branch points:**
- **Physic Garden** upgrades into: Medicinal Distillery, Field Infirmary

---

## Chain 24: Pilgrimage

| Tier | Name | Tech Level | Cost | Upkeep | Description |
|---|---|---|---|---|---|
| 1 | **Wayshrine** | Neolithic | 300 | 6 | A humble wayshrine marking a stop for travelling pilgrims, raised beside the settlement's existing shrine. |
| 2 | **Pilgrim Hostel** | Medieval | 1000 | 35 | A hostel where travelling pilgrims can rest, eat, and spend a little coin before moving on. |
| 3 | **Great Pilgrimage Route** | Medieval | 2600 | 105 | A well-marked pilgrimage route drawing crowds of the faithful from across the Empire. |
| 3 | **Relic Vault** | Industrial | 2700 | 115 | A vault housing holy relics, drawing devoted pilgrims willing to pay handsomely for a glimpse. |
| 4 | **Grand Basilica** | Spacer | 6200 | 260 | A grand basilica anchoring the pilgrimage route to the settlement's established faith, whichever form it has taken. |
| 5 | **Stellar Pilgrimage Terminus** | Ultra | 15000 | 500 | A terminus welcoming pilgrims arriving from other worlds entirely, the faith having long since outgrown a single planet. |

**With Cities & Fields active:** buildable only in City.

**Branch points:**
- **Pilgrim Hostel** upgrades into: Great Pilgrimage Route, Relic Vault

**Prerequisites (must already exist in the settlement):**
- **Wayshrine** requires: Ancestor Shrine
- **Grand Basilica** requires: Grand Cathedral, Inquisitorial Seat, Philosophers' Portico

---
