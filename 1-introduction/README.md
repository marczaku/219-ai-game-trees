# 1 What's A.I. in Games?

Challenging NPC Opponents

<img src="https://cdn.vox-cdn.com/thumbor/WwDkpf0Qp72AdHu9JOXFFhnemnQ=/0x0:3360x2100/1820x1213/filters:focal(1412x782:1948x1318):format(webp)/cdn.vox-cdn.com/uploads/chorus_image/image/65584607/AS_Bnet_Protoss.0.jpg">

- The most classic use case is to provide Non-Player-Characters to allow the player to play a game without matchmaking, toxic behavior, disconnects, etc, like here in StarCraft 2.

Matchmaking

<img src="https://i.imgur.com/TqV4XAl.png">

- While we're at it: as soon as it's not Single-Player, an A.I. is needed to match players for engaging matches. Trying to avoid win- or lose-streaks, unbalanced matches, conflicts in play-styles etc like here in League of Legends.

Finding Cover

<img src="https://eu-images.contentstack.com/v3/assets/blt95b381df7c12c15d/bltb00e7daef8d816a3/611e99f975830930bf6e434e/the-division-cover.jpg?width=828&quality=80&format=webply&disable=upscale">

- In The Division, not only encountered enemies, but also the player can find cover. An AI analyzes what counts as cover and calculates a short path there when the player presses the "Take Cover"-Button.

Driving Human-Like

<img src="https://eu-images.contentstack.com/v3/assets/blt95b381df7c12c15d/blt18536004a8c74b87/611e99fc8ab5544acc6456b8/ForzaDrivatar.jpg?width=828&quality=80&format=webply&disable=upscale">

- Forza adapts its driving style to real player-data to feel more human-like.

Hunting (Stealth-Game)

<img src="https://eu-images.contentstack.com/v3/assets/blt95b381df7c12c15d/blt650396c4ffceb138/611e99fe88a9a63b61fca713/AlienIsolationXenomorph.jpg?width=828&quality=80&format=webply&disable=upscale">

- Alien's AI has smart roaming behavior and can react to signals like sound and movement to adjust its hunting pattern.

Playtesting

<img src="https://eu-images.contentstack.com/v3/assets/blt95b381df7c12c15d/blte1e3d0f819b3592d/611e9a029a154b63bef7fa19/CityConquest.jpg?width=828&quality=80&format=webply&disable=upscale">

- Hiring staff to test your games can be extremely expensiv. City Conquest utilized Genetic Algorithms to Playtest and play each session differently in order to find bugs and help balance the levels.

AI Directors

<img src="https://eu-images.contentstack.com/v3/assets/blt95b381df7c12c15d/bltd9bbddd5ebe796a0/611e9a0675830930bf6e435c/l4d04.jpg?width=828&quality=80&format=webply&disable=upscale">

Left 4 Dead used an AI that "directed" the Game's Pacing, by keeping an eye on the group's health and progression speed and adapting to it with smart climaxes of tension, but also moments to recover and punishing players that start camping to get them out of their cover.


# 2 Constraints

## 2.1 Time

One of our biggest issues is time. Especially, if decisions need to happen in real-time, time and therefore processing power is extremely limited.

## 2.2 Fun

Game A.I. is often considered to not be "real' artificial intelligence, due to our goal often not being to write the optimal Algorithms, but the most fun ones.

## 2.3 Humanity

Very often great algorithms fulfil all other requirements, but still not satisfy our demand for AIs to behave human-like. This might mean making mistakes, having delays or other irrational behavior.

## 2.4 Game Rules

Does your A.I. utilize means that players can't?

There's multiple ways of cheating:

- Breaking game mechanics, e.g. getting extra resources in an RTS, extra speed when behind in a Racing Game or picking, which card will be drawn next. Maybe even swapping out cards from its deck mid-game.
- complete information, e.g. reacting to your strategy in an RTS without scouting your base, or knowing, what card will be drawn next.
-  Super-human behavior, e.g. directly aiming at your head, without the need of reaction time and time for moving the cursor

## 2.5 Configurability

Is your A.I. configurable, so it allows for different difficulties or experiences
- easy, medium, hard
- defensive, neutral, aggressive

## 2.6 Adaptability

Does your A.I. improve by learning from past matches?


# 3 Classifications

## 3.1 Perfect / Imperfect Information

- Perfect: All moves can be seen, all information available (chess)
- Imperfect: Limited knowledge (card games)

## 3.2 Symmetric / Asymmetric

- Symmetric: Same goals, only different strategies to achieve them (rts)
- Asymmetric: Different goals, conflicting or not (werewolves)

## 3.3 Deterministic / Non-Deterministic

- Deterministic: All moves have predictable outcomes (chess)
- Non-Deterministic: Random chance play a roll (poker)

## 3.4 Simultaneous / Sequential

- Simultaneous: Actions can be taken concurrently (real-time strategy)
- Sequential: moves are done in order (round-based strategy)

## 3.5 Zero-Sum / Non-Zero-Sum
- Zero-Sum: An action that benefits one player equally damages the other player
- Non-Zero-Sum: Multiple players can benefit of the gains of another player
