## 9. Game Over Logic

### Check Win Condition
1. In **BP_PongGameMode**
2. In both "AddPointPlayer" functions:
    - After incrementing score, add a **Branch**
    - Check if score >= MaxScore
    - If true, call **"GameOver"** custom event

**Create GameOver Event:**
1. Add Custom Event "GameOver"
2. Add input parameter "Winner" (Integer) - 1 or 2
3. In the event:
    - Show a Game Over widget
    - Stop ball movement
    - Option to restart

**Create Game Over Widget:**
1. Create new Widget Blueprint "WBP_GameOver"
2. Add:
    - Large text: "Player X Wins!"
    - Button: "Play Again"
3. In the button's OnClicked event:
    - Use **Open Level** node with current level name
    - This resets the game
