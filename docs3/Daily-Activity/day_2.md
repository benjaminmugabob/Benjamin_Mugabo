# 2. Activity of Day 2

# Digital Modeling: L-Bracket Project

## Project Overview
**Objective:** Design a structural L-shaped bracket using **FreeCAD**.
**Design Intent:** Create a robust mounting point with 90° geometry, reinforced mounting holes, and stress-relieving fillets.
**Software:** FreeCAD (Part Design Workbench).

---

## Modeling Workflow
My workflow follows the standard **Parametric Modeling** approach: *Sketch, Constrain, Extrude, Refine.*



### Phase 1: Creating the Base Body (Additive)

=== "1. Setup & Sketch"
    I started by creating a new **Body** in the Part Design Workbench and selecting the **XY Plane**.
    
    * **Tool:** Polyline `CreatePolyline`
    * **Action:** Drew a rough "L" shape starting from the origin (0,0).
    * **Constraints:**
        * Applied **Vertical** and **Horizontal** constraints to ensure 90° angles.
        * **Vertical Height:** 60mm
        * **Horizontal Length:** 40mm
        * **Thickness:** 10mm (uniform)

    !!! "Parametric Logic"
        By fully constraining the sketch (turning the lines green), I ensure that the dimensions can be easily modified later without breaking the model geometry.

=== "2. Padding (Extrusion)"
    Once the 2D profile was defined, I transformed it into a 3D solid.
    
    * **Tool:** Pad `PartDesign_Pad`
    * **Parameter:** Length = 40mm
    * **Result:** A solid 3D block representing the raw material volume.

    ![Screenshot of the Extruded L-Shape](../images/left.png)

---

### Phase 2: Adding Features (Subtractive & Refinement)

=== "3. Creating Holes"
    To allow for mounting screws, I used a **Subtractive** process to remove material.
    
    1.  **Select Face:** Clicked the top flat face of the bracket.
    2.  **Sketch:** Drew a circle and constrained the radius to **2.5mm** (for M5 bolts).
    3.  **Pocket:** Used the Pocket tool `PartDesign_Pocket` set to **"Through All"**.
    
    > *Repeating this process on the vertical face ensures the bracket can be mounted on two axes.*

=== "4. The Fillet (Edge Refinement)"
    Sharp corners in mechanical parts are stress concentrators. To mitigate this, I added a fillet.
    
    * **Tool:** Fillet `PartDesign_Fillet`
    * **Target:** The inner corner of the "L".
    * **Radius:** 5mm
    
    ![Screenshot of the Filleted Corner](../images/top.png)

---

## The "Rib" Reinforcement (Advanced)
*Note: While the basic requirement was a simple L-shape, I added a structural rib (as seen in the project reference) to increase rigidity.*

1.  **Sketch Plane:** Created a sketch on the side face of the bracket.
2.  **Geometry:** Drew a triangle connecting the vertical and horizontal arms.
3.  **Pad:** Extruded the triangle using **"Symmetric to Plane"** to center it perfectly on the bracket.

---

## Fabrication Considerations

![Screenshot of the Filleted](../images/day_2/Day2_Activity1.png)
Connecting this design to the physical production process:

| Feature | Fabrication Logic |
| :--- | :--- |
| **Flat Faces** | Designed to lay flat on the 3D printer bed (minimizing supports). |
| **Hole Diameter (5mm)** | Designed with a **0.2mm tolerance** (actual print: 4.8mm) to ensure screws fit. |
| **Fillet** | Prevents layer separation at the corner during 3D printing. |


