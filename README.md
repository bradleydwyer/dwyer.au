# dwyer.au

Personal homepage for Brad Dwyer — a maximalist, chaotic tribute to computing and gaming history wrapped in a retro-terminal/glitch aesthetic. The page is essentially alive: it constantly glitches, spawns animated pixel-art game scenes, cycles through loading messages, and runs a full HBO-style intro on first load.

Everything — CSS, all 48 game renderers (plus 17 bread-themed toast mode scenes), glitch system, HBO intro, warning overlay, matrix rain, cursor proximity, favicon cycling, color drift, name rotation, typing engine — is contained in one `index.html` with no external JS dependencies beyond a Google Fonts CSS link.

## Visual Design

- **Font:** JetBrains Mono (with SF Mono, Cascadia Code, Fira Code fallbacks)
- **CRT scanlines:** Full-viewport repeating-linear-gradient overlay (2px transparent, 2px rgba black at 8% opacity) at z-index 999
- **Color drift:** The name text continuously drifts in hue via requestAnimationFrame — very subtle chromatic shift
- **Glitch effects:** Individual characters get random transforms (translate, skewX), color shifts to glitch palette (#0ff, #f0f, #f00, #0f0, #ff0, #f80), text-shadows with color splits, clip-path slicing, and opacity drops. The body itself can get hue-rotate + saturate filters and background flickers

## Interactive Elements

- **Mouse proximity distortion:** Moving the cursor near the name pushes individual letters away (120px influence radius) with color shifts and glow
- **Click on name:** Forces a maximum-intensity glitch + matrix rain burst
- **Click on background:** Spawns a new game scene at the click position
- **Click on a game scene:** Kills it with a glitch-death animation

## The Intro Sequence

### Phase 1 — Photosensitivity Warning
Full-screen overlay with an animated SVG warning triangle (stroked on over 1s), exclamation mark that pops in, warning text, and a 10-second progress bar countdown. Click/keypress skips with an ease-out drain animation.

### Phase 2 — Warning Glitch-Out
90 frames of ramping chaos: random transforms, hue-rotate/saturate/brightness filters, clip-path slicing, opacity flickers, background color flashes.

### Phase 3 — HBO Color Bars Intro
- Frames 0–30: Classic 7-stripe color bars (white, yellow, cyan, green, magenta, red, blue) with bottom alternate bars
- Frames 30–38: Bars fade into static
- Frames 38–85: Full TV static with horizontal tear lines, page text bleeding through
- Frames 85–130: Static fades out revealing the page

## Game Scenes (48 total)

All scenes render on a 160×120 pixel canvas displayed at 240×180 with `image-rendering: pixelated`. Each runs for 300–600 frames before expiring with a glitch-kill animation.

### Arcade Classics
| Scene | Reference | Description |
|-------|-----------|-------------|
| Pac-Man | Pac-Man (1980) | Pac-Man eating dots, ghosts chasing, score |
| Pong | Pong (1972) | Two AI paddles, bouncing ball, score tracking |
| Breakout | Breakout / Arkanoid | 5 rows of colored bricks, AI paddle, ball physics |
| Space Invaders | Space Invaders (1978) | 3×8 alien grid, formation movement, player ship, bullets |
| Asteroids | Asteroids (1979) | Wireframe ship, rotating asteroids that split, bullets, particles |
| Frogger | Frogger (1981) | Traffic lanes, river with logs/turtles, hopping frog, lily pads |
| Galaga | Galaga (1981) | Alien formations with wing-flap animation, curved dive-bombing, stage counter |
| Missile Command | Missile Command (1980) | Cities, falling missiles, AI defense battery with expanding blast radii |
| Donkey Kong | Donkey Kong (1981) | Sloped girder platforms, ladders, DK throwing barrels, Mario climbing, Pauline |

### Console / Platformers
| Scene | Reference | Description |
|-------|-----------|-------------|
| Sonic | Sonic the Hedgehog (1991) | Side-scroller, checkerboard ground, rings, speed blur, rolling ball form |
| Mario | Super Mario Bros. (1985) | Brick/? blocks, pipes, goombas, coins, clouds, "WORLD 1-1" HUD |
| Zelda | The Legend of Zelda (1986) | Top-down overworld, Link with sword slash, octoroks, hearts, dungeon entrance |
| Commander Keen | Commander Keen Ep. 4 (1991) | Platforms, Keen with ray gun, alien slugs, lollipop collectibles |

### PC / DOS Games
| Scene | Reference | Description |
|-------|-----------|-------------|
| Doom | Doom (1993) | Raycaster 3D corridor, 4 level types, enemies, weapons with muzzle flash, Doom Guy face HUD |
| Wolfenstein 3D | Wolfenstein 3D (1992) | Raycaster blue/grey stone, Nazi banners, guard enemies, pistol |
| Prince of Persia | Prince of Persia (1989) | Stone dungeon, platforms, spike traps, torch flames, sword combat with guard |
| Oregon Trail | The Oregon Trail (1985) | Scrolling wagon, typed event messages (dysentery, etc.), status bar |
| Gorillas | GORILLAS.BAS (QBasic) | City skyline, two gorillas throwing banana projectiles, parabolic arcs, explosions |
| Minesweeper | Windows Minesweeper | 12×9 grid, authentic Win95 styling, AI reveals cells, numbered colors, flags |
| Pipe Dream | Pipe Dream (LucasArts) | Grid of pipe segments, green ooze flowing through path |
| Game of Life | Conway's Game of Life | B3/S23 rules, toroidal wrap, colored by neighbor count, generation counter |

### Adventure Games (Sierra)
| Scene | Reference | Description |
|-------|-----------|-------------|
| Space Quest | Space Quest (Sierra) | Night scene, Roger Wilco walking, "SIERRA ON-LINE" building, parser text box |
| King's Quest | King's Quest (Sierra) | EGA castle scene, Sir Graham walking, parser commands, score |
| Quest for Glory | Quest for Glory (Sierra) | Night town gate "SPIELBURG", torches, hero stats popup, scrolling messages |
| Police Quest | Police Quest (Sierra) | City night, police car with siren lights, Officer Sonny Bonds, radio dispatch messages |
| Carmen Sandiego | Where in the World Is Carmen Sandiego? | 3-phase: briefing with Carmen sprite, city landmarks with clues, world map with plane travel |

### Simulation / Building
| Scene | Reference | Description |
|-------|-----------|-------------|
| SimCity | SimCity (1989) | Isometric grid of R/C/I zones, growing buildings with windows, roads, population counter |
| Minecraft | Minecraft (2011) | Day/night cycle, isometric terrain, Steve mining blocks, Creeper, hearts/XP/hotbar HUD |

### OS / Computing
| Scene | Reference | Description |
|-------|-----------|-------------|
| BSOD | Windows Blue Screen | Authentic blue screen, IRQL_NOT_LESS_OR_EQUAL, crash dump progress |
| Spinning Pinwheel | macOS Beach Ball | Finder "Not Responding" window, rainbow spinning disc, Force Quit hint |
| Windows 95 | Windows 95 Boot | DOS boot → logo with clouds/progress bar → teal desktop with Start button and icons |
| Amiga Boing Ball | Amiga Demo (1984) | Red/white checkerboard sphere bouncing with 3D rotation, grid background |
| DOS Boot | MS-DOS | Boot sequence with HIMEM, MSCDEX, then DIR listing of classic game directories |

### Puzzle / Casual
| Scene | Reference | Description |
|-------|-----------|-------------|
| Tetris | Tetris (1984) | Full working Tetris with all 7 tetrominoes, row clearing, score |
| Wordle | NYT Wordle | Full Wordle grid, AI guesses with correct green/yellow/gray coloring logic |
| Snake | Snake | Green snake eating red food, growing body, score |

### Shooters / Action
| Scene | Reference | Description |
|-------|-----------|-------------|
| Flappy Bird | Flappy Bird (2013) | Pipe gaps, gravity-based bird, score |
| Angry Birds | Angry Birds (2009) | Slingshot, projectile physics, wood/plank structure, green pigs, debris |
| Need for Speed | Need for Speed | Perspective road, traffic cars, roadside trees, player car, MPH/lap HUD |

### Internet Culture / Humor
| Scene | Reference | Description |
|-------|-----------|-------------|
| AI Chat | ChatGPT/Claude/Gemini | Cycles through AI models with sardonic conversations parodying AI assistants |
| Zombo.com | Zombo.com | White background, rotating colored blobs, rainbow "ZOMBO.COM" text, cycling messages |
| Strong Bad Email | Homestar Runner | Compy 386 monitor, email typing, Strong Bad pixel art with boxing gloves |
| Trogdor | Homestar Runner | Trogdor burninating cottages, beefy arm, consummate V's, fleeing peasants |

### Demoscene
| Scene | Reference | Description |
|-------|-----------|-------------|
| Plasma | Demoscene plasma effect | Per-pixel sine-wave plasma, scrolling "GREETINGS FROM THE DEMOSCENE" text, copper bars |

### WarGames
| Scene | Reference | Description |
|-------|-----------|-------------|
| WOPR Terminal | WarGames (1983) | Green terminal typing "SHALL WE PLAY A GAME?", blinking cursor |
| WOPR Map | WarGames (1983) | Wireframe world map, missile arcs, expanding explosions, DEFCON 1 HUD |
| Street Fighter | Street Fighter II | Two stick-fighters, punches/kicks/hadoukens, HP bars, round counter, K.O. overlay |

### Lemmings
| Scene | Reference | Description |
|-------|-----------|-------------|
| Lemmings | Lemmings (1991) | Spawning lemmings, walking/falling/digging/umbrella mechanics, entrance/exit, saved counter |

## Code Snippets (~130 floating text artifacts)

Randomly displayed as ephemeral floating overlays. Categories:

- **Real programming:** Go error handling, C boilerplate, Rust hello world, SQL injection, vim `:wq!`, `git push --force`, npm, pip, Java/Python/Rust/Node stack traces and crashes
- **QBasic / DOS:** BASIC programs, SCREEN 13, AUTOEXEC.BAT, FORMAT, DELTREE, HIMEM, EMM386
- **WarGames:** "SHALL WE PLAY A GAME?", "GREETINGS PROFESSOR FALKEN", "THE ONLY WINNING MOVE IS NOT TO PLAY", "LOGON: Joshua"
- **Sierra adventures:** SIERRA ON-LINE, Roger Wilco, King's Quest, Quest for Glory, Police Quest, parser commands (">LOOK AROUND", ">GET LAMP")
- **Classic text adventures:** "YOU ARE LIKELY TO BE EATEN BY A GRUE" (Zork), Commodore 64 `LOAD"*",8,1`
- **Fighting games:** "ROUND 1 FIGHT!", "HADOUKEN!", "FINISH HIM!", "FATALITY", "TOASTY!"
- **Gaming memes:** "INSERT COIN", "ALL YOUR BASE ARE BELONG TO US", "THE CAKE IS A LIE", "DO A BARREL ROLL!", Konami Code
- **80s/90s computing:** "GURU MEDITATION ERROR" (Amiga), "KEYBOARD NOT FOUND PRESS F1 TO CONTINUE", "ABORT, RETRY, FAIL?", "PC LOAD LETTER" (Office Space)
- **Carmen Sandiego:** "WHERE IN THE WORLD IS CARMEN SANDIEGO?", ACME Detective Agency case files
- **Oregon Trail:** "You have died of dysentery."
- **Homestar Runner:** "DELETED!!", "How do you type with boxing gloves on?", "BURNINATING THE COUNTRYSIDE!", "Come on, fhqwhgads", "The system is down."
- **Minecraft:** "Ssssss... BOOM!", "That's a nice everything you have there..."
- **AI/LLM satire:** "I'd be happy to help!", "As an AI language model", "I apologize for the confusion. Let me try again. *same answer*", "Confidence: 100% Accuracy: ¯\\\_(ツ)\_/¯", "AI REPLACING: [████░░░░░] 42% YOUR JOB"
- **New games:** Asteroids, Frogger, Galaga, SimCity, Sonic, Mario, Zelda, Donkey Kong themed snippets
- **Need for Speed:** "BUSTED! You were doing 198 in a 35", "NITROUS ENGAGED"
- **Zombo.com:** "YOU CAN DO ANYTHING AT ZOMBO.COM", "THE ONLY LIMIT IS YOURSELF"

## Status Bar Messages (57 rotating)

Typed out one character at a time (70ms/char), paused (2.5s), deleted (40ms/char), next message.

- **Under construction:** "Website arriving soon", "Under construction", "Work in progress", "Launching soon", "New site who dis"
- **Classic loading jokes:** "Reticulating splines" (SimCity), "Adjusting bell curves", "Calculating llama expectoration trajectory", "Compressing fish files", "Initializing rhinoceros breeding timetable", "Pixelating nude patch", "Sequencing particles"
- **AI jokes:** "That's a great question!", "Hallucinating confidently", "Replacing developers", "Your job is safe (for now)", "Generating sycophantic praise"
- **Homestar Runner:** "Burninating the countryside", "Checking sbemail", "Consummate V's!"

## Scene Selection — Fair Rotation

The `recentScenes` queue tracks which scenes have been shown. New scenes prefer types not in the recent history (last 75% of all scene types). Only falls back to the full pool once nearly all scenes have played. This prevents the same scenes repeating while keeping random order.

## Other Features

- **Name rotation:** Every 25–35 seconds, cycles between "Brad Dwyer", "brad@dwyer.au", and "dwyer.au" with a glitch-scramble transition
- **Favicon cycling:** Changes every 2–7 seconds between pixel "B", pixel "D", random glitch noise, and a Space Invader — all dynamically generated via canvas
- **Matrix rain:** Triggered on intense glitch events or clicking the name — katakana + ASCII characters with leading bright char and fading green trails

## Toast Mode 🍞

A hidden Easter egg that transforms the entire site into a warm, bread-themed experience for 2 minutes. Inspired by the common misspelling of "Brad Dwyer" as "bread dryer".

### Activation
- **Press T** on the keyboard
- **Type "bread"** as a secret code
- **Click "yes"** on the "is it toast time?" prompt that appears 30–90 seconds after page load

### What Changes

**Visual overhaul:**
- All glitch colors shift from cyan/magenta/green to warm golds, ambers, and browns
- CRT scanlines turn amber
- Background shifts to warm dark brown
- Burnt toast vignette (dark radial gradient at screen edges)
- Warm golden glow pulses behind the name text like an oven light

**Name & text:**
- Name glitch-transitions to "bread dryer"
- Name rotation cycles: "bread dryer" → "bread@dwyer.au" → "dwyer.au"
- Status messages swap to bread puns: "On a roll", "The yeast I could do", "Loafing around", "Knead to know basis", "Proof of concept", etc. (23 messages)
- Browser tab title cycles through bread puns every 3 seconds
- Dough rise animation — name text inflates then settles, like rising dough

**Animations & particles:**
- Toast pop entrance — whole page bounces up like bread from a toaster
- Steam wisps (~≈∿∼) rise from the name text in warm gold
- Fermentation bubbles — translucent golden circles rise from the bottom
- Butter drips — golden streaks melt down the left and right screen edges
- Flour dust — tiny white specks drift around the screen
- Breadcrumb cursor trail — mouse leaves crumb particles (·•∘°) that fade

**Matrix rain:**
- Characters become bread emoji: 🍞🥖🥐🍩🥯🧈🌾🔥☕🍰🧁🥧🫓🥨
- Colors shift to warm amber/brown tones
- Font switches to 20px serif for crisp emoji rendering

**Code snippets (30 bread-themed):**
- `git push --force-rise`, `sudo rm -rf /crumbs`, `npm install sourdough`
- `while(true) { proof(); }`, `// TODO: let dough rest`, `pip install gluten`
- `fn knead(&mut self) -> Dough`, `make bread — make: bread is up to date.`
- `TOASTER STATUS: [████████] 100% *DING!*`, and more

**Toast notifications:**
- Meta toast-notification popups appear periodically: "🍞 Your toast is ready!", "🍞 Gluten matrix stable", "🍞 Crust integrity: 100%", etc.

**Favicon:**
- Cycles between pixel art toast slice, bread loaf, croissant, and toaster

**Sound:**
- Toaster ding on activation (Web Audio API synthesized tone)

**Persistence:**
- Toast counter stored in localStorage, displayed as "toasted N×" in bottom-right corner

### Toast Mode Game Scenes (17 total)

| Scene | Description |
|-------|-------------|
| Bread Loaf | Fresh loaf on a table with rising steam wisps |
| Croissant | Golden croissant on a white plate |
| Toast | Toaster with two slices popping up, steam rising |
| Baguette | Endless baguette conveyor on a bakery shelf |
| Tumble Dryer | Front-load dryer with 🍞🥐🥖 tumbling inside |
| Laundry Room | Two side-by-side dryers with bread emoji spinning |
| Paris Boulangerie | Eiffel Tower silhouette with falling baguettes and a café awning |
| Wheat Field | Golden wheat stalks swaying in the wind at sunset |
| Conveyor Bakery | Factory line of scored loaves heading into a fiery oven |
| Pancake Flip | Pan flipping a pancake in the air with butter pat |
| Bread Pong | Pong with baguette paddles and a bread roll ball |
| Pizza Oven | Brick oven with flickering flames, pizza sliding in/out on a peel |
| Sandwich Stacker | Ingredients dropping and stacking: bread, lettuce, tomato, cheese, meat |
| Sourdough Jar | Bubbling sourdough starter with rising bubbles and "DAY 47" counter |
| Bread Rising | Dough expanding in a bowl under a towel with progress percentage |
| Donut Shop | Display case of frosted donuts with glaze drips |
| Waffle Iron | Steaming waffle grid with blinking indicator light |

## Hidden Features

- **Press T** or **type "bread"** to activate toast mode
- **Click a game scene** to glitch-kill it immediately
- **Click empty space** to spawn a new game scene at that position
- **Click the name** to force a maximum-intensity glitch + matrix rain burst
- **Hover over the name** to push letters away from the cursor
