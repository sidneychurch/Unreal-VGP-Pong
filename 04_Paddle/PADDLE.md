# Creating the Paddles

First let's create a new folder to contain our Blueprints.
Name it Blueprints.

<img src="img.png" width="20%">

## Create A BluePrint
1. Inside the folder, Click **"Add"** → **Blueprint Class**

![img_1.png](img_1.png)

2. Select **Pawn** as the parent class

![img_2.png](img_2.png)

3. Name it "BP_Paddle"

<img src="img_3.png" width="20%">

4. Double-click BP_Paddle to open the Blueprint Editor

### Inside the Blueprint:
1. In the **Components** panel (top-left), you'll see "DefaultSceneRoot"
2. Click **"Add"** → **Cube**

<img src="img_4.png" width="50%">

3. Select the Cube component, then in Details:
    - **Scale:** X=0.5, Y=3, Z=2
4. Set **Collision Presets** to "OverlapAll"

    <img src="img_5.png" width="50%">


**Add a Variable for Paddle Speed:**
1. In the **My Blueprint** panel (left side), find **Variables** section
2. Click the **"+"** button

<img src="img_6.png" width="50%">

3. Name it "MoveSpeed"
4. Click the variable, in Details set:
    - **Variable Type:** Float

   <img src="img_7.png" width="50%">
   
5. Click Compile at the top so that we can set a default value for MoveSpeed
   
    <img src="img_8.png" width="50%">
- **Default Value:** 500.0 (compile first by clicking "Compile" at the top)
   
    <img src="img_9.png" width="50%">
 
6. Make MoveSpeed **"Instance Editable"** by checking the property or the eye icon.

7. **Compile** and **Save** the Blueprint

## Place Paddles in the Level
1. Drag **BP_Paddle** from the Content Browser into the viewport
2. Position it:
    - **Location:** X=-900, Y=0, Z=0
3. Rename this instance to "PlayerPaddle" in the Outliner
4. Duplicate it (Ctrl+D)
5. Position the duplicate:
    - **Location:** X=900, Y=0, Z=0
6. Rename to "AIPaddle"

If you select the Camera Actor in the Outliner, the camera preview should look like this:
![img_10.png](img_10.png)


---
>Prev: [Creating the Game Area](/03_Area/AREA.md) |  Next: [Player Input](/05_Input/INPUT.md)