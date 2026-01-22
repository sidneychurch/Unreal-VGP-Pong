## 6. Adding Collision Detection

### Ball Collision with Paddles
1. Open **BP_Ball** Blueprint
2. In **Event Graph**, right-click and search for "Event ActorBeginOverlap"
3. This creates an overlap event node

**Bounce Logic:**
1. From the **Other Actor** pin, drag and search for "Cast to BP_Paddle"
    - This checks if we hit a paddle
2. From the **Cast Success** pin (top execution pin), create the bounce:
    - Get **Current Velocity**
    - Use a **Multiply** node (Vector × Float) and set to -1.0 on the Y component
    - Or better: Use **"MirrorVectorByNormal"** node
    - For the normal, create a **Make Vector** with X=0, Y=1, Z=0 (or -1 depending on paddle side)
    - Set the result back to **Current Velocity**

![img.png](img.png)

### Ball Out of Bounds Detection
1. In BP_Ball Event Graph
2. From **Event Tick**, add a **Branch** node
3. Get **Actor Location**, break the vector (right-click the pin → **Split Struct Pin**)
4. Check if **Location Y** > 1000 or < -1000
5. If true, this is a score event (we'll expand this later)

---
