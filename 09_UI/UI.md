## 8. Creating the UI (HUD)

### Create Widget Blueprint
1. Right-click in Content Browser → **User Interface** → **Widget Blueprint**
2. Name it "WBP_PongHUD"
3. Double-click to open the **UMG Designer**

**Design the HUD:**
1. From the **Palette** panel (left), drag a **Canvas Panel** to the hierarchy
2. Drag two **Text** blocks onto the Canvas Panel
3. Select first Text:
    - Rename to "Player1ScoreText"
    - In Details:
        - **Position X:** 200, **Position Y:** 50
        - **Text:** "0"
        - **Font Size:** 72
        - **Justification:** Center
4. Select second Text:
    - Rename to "Player2ScoreText"
    - **Position X:** 1720, **Position Y:** 50
    - **Text:** "0"
    - **Font Size:** 72

**Add Center Line (Optional):**
1. Drag an **Image** widget to the canvas
2. Set size: Width = 5, Height = 1080
3. Position: Center of screen
4. Set color to white

**Create Update Function:**
1. Switch to **Graph** tab
2. In **Functions**, create "UpdateScore"
3. Add two input parameters:
    - "P1Score" (Integer)
    - "P2Score" (Integer)
4. In the function:
    - Get reference to **Player1ScoreText**
    - Use **Set Text** and convert P1Score to Text (Int → Text node)
    - Do the same for Player2ScoreText

**Compile and Save**

### Display the HUD
1. Open **BP_PongGameMode**
2. In **Event BeginPlay**:
    - Add **Create Widget** node
    - Set Class to **WBP_PongHUD**
    - From the return value, use **Add to Viewport**
    - Store the widget reference in a variable "HUDReference"
