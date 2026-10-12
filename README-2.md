# Doodle Guesser

Our K-12 tabling station. A kid gets a word, draws it, and an AI tries to guess it live before 20 seconds run out.

## How it works

It runs DoodleNet through ml5.js, a model trained on Google's open source Quick, Draw! dataset (50 million doodles, 345 categories). Everything runs in the browser, so there's no server and no install.

Heads up: Google released the dataset, not the code for their game. This is our own version built on top of that data.

## Run it

Easiest: open the GitHub Pages link on any laptop or tablet.

Locally: open `index.html` in VS Code and use Live Server. Double clicking the file can work too, but some browsers block the model from loading that way.

Needs internet the first time so it can load the libraries and the model.

## What's built

* Random kid friendly prompt word each round
* Drawing canvas that works with fingers on a tablet
* Live top 3 guesses with confidence bars
* 20 second timer, win screen when the AI gets it, and a score counter
* Clear and Skip buttons
* AI only guesses from our word list, so random categories can't steal the win
* Auto crop that zooms in on the doodle and centers it before the AI looks, so small drawings still work

## Logo

Put the official UA logo in the repo root as `logo.png` and it shows up in the header automatically. If the file isn't there, the header just shows the text.

## Tweaking stuff

All the settings are at the top of the script in `index.html`:

* `ROUND_SECONDS` for round length
* `WORDS` for the prompt list (only use real Quick, Draw! categories or the AI can never win)
* `GUESS_INTERVAL_MS` for how often it guesses. Raise it if the tablet lags
* `ONLY_GUESS_PROMPT_WORDS` set to false lets it guess from all 345 categories again
* `WIN_CONFIDENCE` for how sure the AI has to be before it counts as a win

## Ideas for next

* Leaderboard or streak counter
* Difficulty levels (easy words for little kids)
* A "how does it know?" info card for the table
* Offline mode so we don't depend on venue wifi
