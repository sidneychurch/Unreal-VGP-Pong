## 7. Creating the Score System

### Create Game Mode Blueprint
1. **Create** → **Blueprint Class** → **Game Mode Base**
2. Name it "BP_PongGameMode"
3. Open it

**Add Score Variables:**
1. Add variable "Player1Score" (Integer) = 0
2. Add variable "Player2Score" (Integer) = 0
3. Add variable "MaxScore" (Integer) = 5

**Add Score Functions:**
1. In **Functions** section (My Blueprint panel), click **"+"**
2. Name it "AddPointPlayer1"
3. In the function graph:
    - Get **Player1Score**
    - Add **Increment** node (or add 1)
    - Set **Player1Score** with the new value
    - Call a custom event "UpdateScoreUI" (we'll create this with the UI)
4. Create similar function "AddPointPlayer2"

**Add Ball Reset Function:**
1. Create function "ResetBall"
2. Get all actors of class **BP_Ball**
3. Set their location to X=0, Y=0, Z=0
4. Randomize their starting velocity

**Set as Default Game Mode:**
1. Go to **Edit** → **Project Settings** → **Maps & Modes**
2. Set **Default GameMode** to **BP_PongGameMode**
