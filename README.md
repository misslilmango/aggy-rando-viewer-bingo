# Aggy Randomizer Bingo

An interactive, serverless, and completely free bingo game built for viewers to play along during Aggy's Weekly Randomizer streams! 

This web app generates a unique bingo card for every player based on their Twitch username. When Aggy starts a new weekly run, the host changes the weekly ID, and everyone’s card automatically resets for the new run.

---

## Credits & Acknowledgments
* **Original Idea:** UltimaPhoenix2405
* **Implementation & Code:** misslilmango

---

## Features
* Runs entirely in the viewer's browser. No database, servers, or hosting costs.
* Viewers enter their Twitch username to get a card that is completely unique to them. No two players have the exact same card!
* If a viewer accidentally refreshes their page, their username will regenerate the exact same card for that week. No progress lost!
* Built-in automatic 5-in-a-row (horizontal, vertical, or diagonal) detection.
* Features a "Download PNG" button that cleanly renders the user's card so they can post it on Discord.

---

## How the "Random" Math Works (No Database Required)

1. The viewer inputs their username (e.g., `Mango`).
2. The browser combines the username with the current Weekly ID (e.g., `Mango_Week_1`).
3. This text string is put through a fast hashing algorithm (`cyrb128`) to generate a unique 32-bit mathematical seed.
4. A deterministic random function (`mulberry32`) shuffles the item pool using that seed.

Because the math is entirely deterministic, the same username will always yield the exact same card for that specific week, but different usernames will generate completely unique grids.
