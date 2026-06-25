# 💭 Reflection: Game Glitch Investigator

Answer each question in 3 to 5 sentences. Be specific and honest about what actually happened while you worked. This is about your process, not trying to sound perfect.
## 1. What was broken when you started?

At first, I noticed that I was able to enter my guess and the game was telling me to go lower while the actual correct number was higher than what I guessed. The hints were overall backwards and the secret number didn’t match my guess. When I tried to start a new game, it kept saying game over and didn’t allow me to start the new game.

**Bug Reproduction Log**

Document at least 3 bugs you found. Add rows as needed.
<img width="486" height="194" alt="Screenshot 2026-06-25 150416" src="https://github.com/user-attachments/assets/157cfaf1-49f7-4aed-9c28-f12bc0045d8b" />

## 2. How did you use AI as a teammate?

For this project, I used Github Copilot to help with any errors or bugs I needed to fix. One example of a suggestion that was correct was the game logic functions that were refactored into logic_utils. One example of a suggestion that was incorrect was in the check guess function. I verified the result by running the app to see how it worked.

## 3. Debugging and testing your fixes

I decided that a bug was really fixed by running the app again to ensure that the same error didn’t repeat. The AI helped understand the tests by knowing the purpose behind them and how they acted as the specification for the function behavior. 

## 4. What did you learn about Streamlit and state?
I would explain it like this: Imagine your app is a recipe that gets cooked from scratch every time something happens:
•	When a user clicks a button, types something, or moves a slider → the entire app.py script runs from line 1 to the end again
•	This is called a "rerun"
•	Without special handling, all your variables would get reset to their default values (like attempts = 1 would reset back to 1)

## 5. Looking ahead: your developer habits
One habit or strategy I would want to reuse in future labs or projects is to not solely rely on the AI tool, but to ensure I double check since it can make errors. This project changed the way I thought about AI generated code was that I somewhat thought that it wasn't always accurate or original, but I came to realize that it can be very helpful and it allows you to learn while you're coding. 
