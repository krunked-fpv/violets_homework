# 🐸👑 Violet's Championship Quest: Long /O/ & Metamorphosis Game Show!

**[🎮 PLAY VIOLET'S CHAMPIONSHIP QUEST LIVE (krunked-fpv.github.io/violets_homework) 🚀](https://krunked-fpv.github.io/violets_homework/)** • **[📦 GitHub Repository](https://github.com/krunked-fpv/violets_homework)** • **[🖥️ Companion Google Slides Game Show](https://docs.google.com/presentation/d/1oSDU7vfsShmhrNtLXLWaLAwuksxUnW3rqZwtxFD1Wv4/edit)** • **[📄 Printable 5-Star Practice Playbook Doc](https://docs.google.com/document/d/1toRghnHExDVKz3tHK-JaKdJVPER23ySkDWJlyjACcxU/edit)**

## 🌟 What Is This Project?

**Violet's Championship Quest** is the interactive HTML5 homework game show in **Violet's Weekly 3-Part Homework Suite** (paired with her [Google Slides Game Show](https://docs.google.com/presentation/d/1oSDU7vfsShmhrNtLXLWaLAwuksxUnW3rqZwtxFD1Wv4/edit) and [Printable 5-Star Practice Playbook](https://docs.google.com/document/d/1toRghnHExDVKz3tHK-JaKdJVPER23ySkDWJlyjACcxU/edit)). Built for **Violet** (2nd Grade at Paris Ridge Elementary, **Mrs. Molly Ulrich's** class) and coached by **Dad (Alex)** and **Marisa**, the app turns her structured 1-hour evening homework routine—two focused 10–15 minute sprints separated by a 5-minute movement break—into a broadcast television game show where earning all **5 Arena Stars** unlocks **30+ minutes of free creative time**!

## 🛡️ 3-Tier Persistence & Daily Reset Architecture (`Reset Daily` + `Local Sync` + `Shadow-Cookie Auto-Healer`)

So Violet never loses her weekly **Champion Coins**, **5 Arena Stars**, or **Monday–Thursday Parent Hub sign-offs** when refreshing the page or playing on her **Amazon Fire Kids Tablet**, `index.html` runs a 3-tier self-healing persistence stack:

| Persistence & Reset Layer | Header Control / Engine | How It Protects Violet's Weekly Progress |
| :--- | :--- | :--- |
| **1. Top-Bar `🔄 Reset Daily` Button** | `🔄 Reset Daily` (2-tap guarded) in top navigation bar | Clears today's practice boards (Ready Check, Karate Chop words, Long `/o/` Vault sorts, 5-Finger Retell cards, Teleprompter passes, and Math Lab inputs) for a fresh daily rep while **preserving** cumulative weekly Champion Coins, Arena Stars (`0/5`), Streak, Gratitude drawing/sentence, and Mon–Thu Parent Hub sign-offs. |
| **2. Self-Contained `💾 Local Sync` & HTML Baker** | `💾 Local Sync` modal + `<form id="quest-inline-state-form">` + `window.__VIOLET_QUEST_STATE__` | Modeled after the [Discogs Vinyl Vault](https://github.com/krunked-fpv/discogs_collection). Click **💾 Download Updated Game HTML (Bake Progress In)** to save a clean, self-contained `index.html` with all current points, stars, drawing, and sign-offs baked directly inside the HTML file, or export/import `violet_quest_sync.json` and clipboard sync strings. |
| **3. Shadow-Cookie Auto-Healer (`kv1_*`)** | `<script id="krunked-cookie-vault-v1">` in `<head>` (400-day `SameSite=Lax` cookies) | Defends against tablet OS and mobile browser `localStorage` eviction. Hooks `Storage.prototype.setItem`, `removeItem`, and `clear`, automatically strips heavy base64 `<canvas>` Gratitude Scene drawings (`data:image/...`) to stay under the 4 KB per-cookie limit, chunks `violet_quest_nov16_v1` into 3.2 KB cookies (`Max-Age=34560000`), restores `localStorage` at boot before the game initializes, and updates the shared `krunked_family_pulse` (`Path=/`) root cookie across `krunked-fpv.github.io`. |

### Patching, Rollback & Console Diagnostics

* **One-Command Ad-Hoc Patcher (`bolt_on_cookie_persistence.py`):**
  ```bash
  # Patch violets_homework index.html with automatic .cookie_bak backup
  python bolt_on_cookie_persistence.py C:\path\to\violets_homework

  # Roll back to .cookie_bak if needed
  python bolt_on_cookie_persistence.py --rollback C:\path\to\violets_homework
  ```
* **Browser Console Check:** Run `window.__KRUNKED_COOKIE_VAULT__.status()` in the browser console to inspect mirrored `kv1_*` cookie chunks and the shared `krunked_family_pulse` summary across [violets_homework](https://krunked-fpv.github.io/violets_homework/), [ozias_laboratory](https://krunked-fpv.github.io/ozias_laboratory/), and [discogs_collection](https://krunked-fpv.github.io/discogs_collection/).

## 🔊 Amazon Fire Kids Tablet 3-Part Spoken-Word Audio Engine

Because the **Amazon Kids (FreeTime) Web Browser** runs inside a restricted child profile that frequently blocks `window.speechSynthesis` or drops audio when `cancel()` and `speak()` fire together, `index.html` includes a dedicated 3-part spoken-word fallback (plus a live **Voice Engine & Fire Tablet Audio Diagnostic** panel inside **📋 Parent Hub**) while leaving native desktop and phone TTS untouched:

1. **60ms Chromium/Fire OS `cancel()` Debounce:** Prevents the Android WebView race condition where `speechSynthesis.cancel()` silences the immediately following `speak()` utterance.
2. **Flexible `en-US` / `en_US` Locale Matching:** Normalizes underscore and hyphen locale tags on Fire OS without assigning broken voice objects when `getVoices()` returns empty.
3. **300ms Watchdog, 2.5s Endpoint Timeout & HTML5 `<audio>` Dictionary MP3 / Streamed TTS Fallback:** If `speechSynthesis.onstart` does not fire within `300ms` (or immediately when Fire/Silk Kids browser is detected or **Tablet Media Audio: Forced ON** is enabled in Parent Hub), the game streams real dictionary pronunciation MP3s and TTS audio through a shared HTML5 `<audio>` media element—with a `2.5s` per-URL timeout so filtered endpoints never hang—using the exact same unrestricted media channel as the game show's **On-Air Chime**, **Crowd Fanfare**, and **Drumroll**.

## 🕹️ Inside the 6 Game Show Stages (1-Hour MTSS Routine)

| Stage / Sprint Window | Game Show Arena | Core 2nd Grade Skills & Interactive Mechanics |
| :--- | :--- | :--- |
| **Stage 0 • Pre-Sprint Ritual (5 Mins)** | **🚦 0. Ready Check & Soundboard** | Complete Mrs. Ulrich's **3-Step Champion Check** (*Clear the Deck, Body Ready, Eyes on Speaker, Repeat the Task*), speak the daily affirmation (*"I am loved, I am special, I can change the universe, and we really can!"*) for `+15 Coins`, and tap the **10 Long `/O/` Spelling Words Soundboard**. |
| **Arena 1 • Sprint 1 Phonics (5 Mins)** | **🥋 1. Tadpole-to-Frog Compound Word Karate Chop** | Chop the 5 compound spelling words (`tadpole`, `oatmeal`, `raincoat`, `snowball`, `toenail`) right between their two base words (`tad + pole`), arm-tap Shoulder–Elbow–Wrist, identify the hidden Long `/o/` pattern, and fuse the word back together. |
| **Arena 2 • Sprint 1 Spelling (5 Mins)** | **🔐 2. The 5 Secret Long `/O/` Vaults** | **3 Modes in 1:** (1) **Vault Sorter** into the 5 Long `/o/` patterns (`o`, `o_e`, `oa`, `ow`, `oe`), (2) **Mystery Letters** vowel-lock cracker, and (3) **Live Audio Spelling Test** with contextual sentences and non-spoiler Arm-Tap hints. |
| **Arena 3 • Movement Break (5 Mins)** | **🦋 3. Metamorphosis 5-Finger Retell & Pond Leap** | Sequence the **Frog** and **Butterfly** life cycles using Mrs. Ulrich's 5-Finger Retell words (**First, Then, Next, Then, Last**), act out each stage across the living room, and play the **Tadpole-to-Frog Pond Leap** arcade mini-game! |
| **Arena 4 • Sprint 2 Reading (15 Mins)** | **🎙️ 4. *Kids Excel* Sportscaster Desk & Gratitude Mic Drop** | Read two live teleprompter scripts packed with all 10 spelling words (Pass 1 Accuracy, Pass 2 Big TV Sportscaster Expression on `" "` quotation marks), then type a **Gratitude Mic Drop Sentence** with live 3-Star Self-Check and draw a Gratitude Scene on the digital `<canvas>`. |
| **Arena 5 • Sprint 2 Math Lab (15 Mins)** | **💥 5. "Explode" the Number Lab & Tadpole Hop Lines** | **Part A:** `+4` Challenger Flashcard Sprint (layered onto Teens, `+0`, `+1`, `+2`, `+3`, and Doubles). **Part B:** Click **💥 EXPLODE** to break 2-digit addition into Tens and Ones (`58 + 42 = 50 + 40` and `8 + 2`). **Part C:** Spot **Whole vs. Part** first, then hop the Tadpole back to a friendly 10 on the interactive number line (`53 - 23`: hop `-3` to `50`, jump `-10` to `40`, jump `-10` to `30`). |

## 🔐 Weekly Long `/O/` Spelling Vault Matrix

| Vault Pattern | Phonics Rule & Coach Tip | Target Spelling Words | Syllable Arm-Tap |
| :--- | :--- | :--- | :--- |
| **Vault 1: Open `o`** | Open syllable—the `o` at the end of the first syllable says its long name! | **moment**, **frozen** | `mo • ment`, `fro • zen` |
| **Vault 2: Magic `o_e`** | Silent Magic `e` jumps over one consonant to make `o` say `/ō/`! | **tadpole**, **explode** | `tad • pole`, `ex • plode` |
| **Vault 3: Team `oa`** | *"When two vowels go walking, the first one does the talking!"* (Usually in the middle) | **oatmeal**, **raincoat** | `oat • meal`, `rain • coat` |
| **Vault 4: Team `ow`** | `ow` says Long `/ō/` at the end of a base word or before `l`/`n`! | **snowball**, **elbow** | `snow • ball`, `el • bow` |
| **Vault 5: Team `oe`** | `oe` teams up right at the end of root words (`toe`, `goes`)! | **toenail**, **goes** | `toe • nail`, `goes` |

## 🚀 Quick Start & GitHub Pages Deployment

1. **Play Online (Laptop, Phone, or Amazon Fire Kids Tablet):** Open **[krunked-fpv.github.io/violets_homework](https://krunked-fpv.github.io/violets_homework/)**.
2. **Daily Replay vs. Weekly Save:**
   * Click **`🔄 Reset Daily`** in the top bar each school night (Monday–Thursday) to clear the activity boards for a fresh practice run while keeping all coins, stars, and Parent Hub checkmarks.
   * Open **`📋 Parent Hub`** to sign off Monday–Thursday coaching sessions, test the Fire Tablet voice engine, or open the companion Google Slides and Printable Playbook Doc.
   * Click **`💾 Local Sync`** anytime to export a JSON backup or click **`💾 Download Updated Game HTML (Bake Progress In)`** to download a self-contained `index.html` with Violet's latest progress permanently baked in.
