# The Halloween Spellbook of Pankaj

A Halloween web game made as a gift for Pankaj Kukkal. For years he ran a special Halloween event for his Qualcomm department, and this game carries the tradition forward. Pankaj is the star as **Pankaj the Wise**, a wizard defending a moonlit graveyard party from spirits that want to crash it.

Everything is in one file, `index.html`, including both images. There's nothing to install and no build step.

---

## How to play

1. Open `index.html` in a browser.
2. Click **Open the Spellbook**. Pankaj turns from his suit into his wizard robes.
3. Click **Defend the party** to start the 75-second round.

| Action | Mouse / keyboard | Touchscreen |
|---|---|---|
| Zap a creature with the staff | Click it | Tap it |
| Cast the Great Spell (spellbook full) | Press **Space** or click Pankaj | Tap Pankaj |
| Mute or unmute | ♫ button, bottom right | ♫ button |

### Rules
- **Candles:** Pankaj starts with 5. Each creature that reaches him puts one out, and the round ends early if all 5 go out.
- **Spellbook:** Each creature you banish adds to the meter. When it's full, the Great Spell clears every creature on screen.
- **Golden pumpkin:** It flies across the sky about every 20 seconds. Catch it for 100 points and a full spellbook.
- **Combos:** Banishing creatures quickly in a row raises your score multiplier, up to ×4.
- **Waves:** New creatures join as the round goes on, and everything speeds up.

### Creatures
| Creature | Points | Notes |
|---|---|---|
| Ghost | 10 | Drifts and sways |
| Bat | 15 | Fast and zig-zags |
| Jack-o'-lantern | 25 | Bounces, takes 2 hits |
| Will-o'-wisp | 30 | Fastest; appears after 40 seconds |
| Golden pumpkin | 100 | Doesn't attack; fills the spellbook |

### Ranks
The ending card gives a rank based on candy collected:

| Candy | Rank |
|---|---|
| 0+ | Halloween Intern |
| 400+ | Staff Sorcerer |
| 900+ | Senior Staff Sorcerer |
| 1,600+ | Principal Engineer of the Dark Arts |
| 2,600+ | Director of Spooky Operations |
| 3,800+ | VP of All Things Haunted |

---

## Running and sharing

- **Locally:** Double-click `index.html`. It works in current versions of Chrome, Edge, Safari and Firefox on desktop or mobile.
- **Hosting:** Upload the file to any static host, such as GitHub Pages, Netlify or a personal site. No server code is needed.
- **Sending it:** Many email services block `.html` attachments, so a hosted link is usually more reliable than attaching the file.
- **Fonts:** The headings use Cinzel Decorative and IM Fell English from Google Fonts. Without an internet connection the page switches to a standard serif font, and the game still works fully.

---

## Customizing

All of these are in `index.html` and can be changed in any text editor.

| What | Where to look |
|---|---|
| Sign-off on the ending card | Search for `From your old Qualcomm crew` |
| Thank-you message | Search for `For years you turned one October day` |
| Intro story text | Search for `Every October, one leader` and `Tonight, the spirits want` |
| Name on the plaque | Search for `Pankaj the Wise` |
| Round length | `const GAME_LEN=75;` (seconds) |
| Starting candles | `candles=5` in the `reset()` function |
| Creature speeds | `sp:52*U*diff` (ghost), `sp:72*U*diff` (bat), `sp:36*U*diff` (pumpkin), `sp:100*U*diff` (wisp) |
| Rank names and score thresholds | The `ranks` list in `showEnd()` |
| Wave announcements | The `waves` list |

---

## How it's built

- **One HTML file** with inline CSS and JavaScript and no libraries. The two portraits are embedded as base64 JPEGs.
- **Canvas 2D rendering:** The graveyard is drawn in code, including the moon, the haunted house, recursively generated trees, gravestones and the glowing jack-o'-lanterns. The fog, clouds, bats in the distance and lightning are animated live.
- **Creatures and effects** are also drawn in code. The page scales for high-resolution screens and for any window size.
- **Audio** is made with the Web Audio API, so there are no sound files: a low drone, a looping minor-key music-box tune, and sound effects for zaps, pops, damage, the golden pumpkin, thunder and the Great Spell.
- **Artwork:** The suit and wizard portraits come from the Halloween images made earlier for this gift.

---

*Happy Halloween, Pankaj. The tradition lives on.* 🎃
