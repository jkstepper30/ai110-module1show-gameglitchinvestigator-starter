# 🎮 Game Glitch Investigator: The Impossible Guesser

## 🚨 The Situation

You asked an AI to build a simple "Number Guessing Game" using Streamlit.
It wrote the code, ran away, and now the game is unplayable. 

- You can't win.
- The hints lie to you.
- The secret number seems to have commitment issues.

## 🛠️ Setup

1. Install dependencies: `pip install -r requirements.txt`
2. Run the broken app: `python -m streamlit run app.py`

## 🕵️‍♂️ Your Mission

1. **Play the game.** Open the "Developer Debug Info" tab in the app to see the secret number. Try to win.
2. **Find the State Bug.** Why does the secret number change every time you click "Submit"? Ask ChatGPT: *"How do I keep a variable from resetting in Streamlit when I click a button?"*
3. **Fix the Logic.** The hints ("Higher/Lower") are wrong. Fix them.
4. **Refactor & Test.** - Move the logic into `logic_utils.py`.
   - Run `pytest` in your terminal.
   - Keep fixing until all tests pass!

## 📝 Document Your Experience

The Game Glitch Investigator is a number-guessing game built with Streamlit where:
•	Players select a difficulty level (Easy: 1-20, Normal: 1-100, Hard: 1-50) that determines the range and attempt limit
•	Players guess a secret number and receive feedback (too high, too low, or correct)
•	A scoring system rewards successful guesses based on the number of attempts (100 - 10×attempts, minimum 10 points for a win)
•	Players earn/lose bonus points on wrong guesses (±5 points depending on guess direction and attempt number)
•	The game tracks history and displays debug information for transparency

Bugs Found
1.	NotImplementedError in logic_utils.py - All four core functions (check_guess, get_range_for_difficulty, parse_guess, update_score) were raising NotImplementedError instead of being implemented
2.	Undefined variable references in app.py - Lines at the top attempted to call check_guess(guess_int, secret) before those variables were defined, causing immediate crashes
3.	Wrong return format in check_guess() - The test file revealed the function should return emoji-based messages ("📈 Go HIGHER!", "📉 Go LOWER!", "🎉 Correct!") but the initial stub returned plain text
4.	Missing logic flow - The submit block didn't call check_guess() to determine the outcome, leaving outcome and message undefined when needed for scoring and UI display

Fixes applied.
1.	Implemented all logic_utils.py functions - Moved game logic from app.py (or created missing implementations) for difficulty ranges, input parsing, guess evaluation, and score updates
2.	Fixed check_guess() return values - Updated to return (outcome_string, emoji_message) tuples matching test specifications exactly
3.	Refactored app.py imports - Added proper imports for all four functions from logic_utils module
4.	Fixed submit logic - Added the missing check_guess() call in the submit block to evaluate guesses and set outcome/message variables


## 📸 Demo Walkthrough

Describe your fixed game in numbered steps so a reader can follow along without watching a video:

1. User enters a guess of 40
2. Game returns "Too Low"
3. User enters a guess of 70 → "Too High"
4. Score updates correctly after each guess
5. Game ends after the correct guess which is 63

<img width="648" height="440" alt="image" src="https://github.com/user-attachments/assets/5bfa32b8-8981-49bd-9eb3-50e70ec636f0" />


## 🧪 Test Results

```
# Paste your pytest output here, e.g.:
# pytest tests/
# ========================= X passed in 0.XXs =========================
```

## 🚀 Stretch Features

- [ ] [If you choose to complete Challenge 4, describe the Enhanced UI changes here — a screenshot is optional]
