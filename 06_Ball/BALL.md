## 5. Creating the Ball

### Create the Ball Blueprint
1. Click **"Create"** → **Blueprint Class** → **Actor**
2. Name it "BP_Ball"
3. Double-click to open

**Add Components:**
1. Click **"Add"** → **Sphere** (Static Mesh)
2. Select the Sphere component
3. In Details:
    - **Scale:** X=0.5, Y=0.5, Z=0.5
4. Scroll down to **Physics**:
    - Uncheck **"Enable Gravity"** = False
    - Set **Linear Damping** = 0 (no slowdown)
    - Set **Angular Damping** = 0
   
![img.png](img.png)

**Add Variables:**
1. Create variable "StartSpeed" (Float) = 600.0
2. Create variable "CurrentVelocity" (Vector) = X=0, Y=0, Z=0

![img_1.png](img_1.png)

**Add Launch Logic:**
1. Go to **Event Graph**
2. Find the **Event BeginPlay** node (should already be there)
3. From BeginPlay, drag out and search for "Set Current Velocity"
4. Create a **Make Vector** node
    - Set X = 1.0, Y = 1.0, Z = 0
5. Drag from Make Vector output and search for "Normalize"
6. From Normalize output, drag and search for "Multiply" (Vector × Float)
7. Connect **StartSpeed** variable to the multiply
8. Connect the result to **Set Current Velocity**

![img_2.png](img_2.png)

**Add Movement Logic:**
1. Right-click and add **Event Tick**
2. From Event Tick:
    - Add **GetActorLocation**
    - Add **CurrentVelocity** variable (getter)
    - Add **Get World Delta Seconds**
    - Multiply CurrentVelocity by Delta Seconds
    - Add those vectors together with an **Add** node (Vector + Vector)
    - Use **SetActorLocation** with the result

![img_3.png](img_3.png)

9. **Compile** and **Save**

### Place Ball in Level
1. Drag **BP_Ball** into the viewport
2. Position: X=0, Y=0, Z=0 (center of play field)
