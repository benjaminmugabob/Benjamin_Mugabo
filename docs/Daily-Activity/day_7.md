# 7. Activity of Day 7

# Digital Fabrication III: CNC Router Milling

## Overview
CNC (Computer Numerical Control) Routing is a **subtractive** manufacturing process. Unlike 3D printing which builds layers, the CNC router starts with a solid sheet of material and cuts away the excess using a spinning tool.

## 1. Systems & Components
Understanding the machine architecture is the first step to safe operation.

* **Spindle:** The motor that rotates the cutting tool (End Mill).
* **Gantry:** The bridge that moves the spindle along the X and Y axes.
* **Bed/Spoilboard:** The sacrificial layer (usually MDF) that supports the stock material.
* **Collet:** The cone-shaped sleeve that grips the tool bit.

---

## 2. Tooling & Material Compatibility
Selecting the right "End Mill" (bit) is critical for finish quality and machine safety.

| Tool Type | Geometry | Best Application |
| :--- | :--- | :--- |
| **Flat End Mill** | Flat tip | Cutting profiles, pockets, and straight edges. |
| **Ball Nose Mill** | Rounded tip | 3D contouring, curved surfaces. |
| **V-Bit** | V-shaped tip | Engraving text, chamfering edges. |
| **Compression Bit** | Up/Down spiral | Cutting plywood without chipping the top or bottom veneer. |

!!! warning "Feeds & Speeds"
    Every material (Plywood, Acrylic, Aluminum) requires a specific **Feed Rate** (speed of movement) and **Spindle Speed** (RPM). Running too fast can break the bit; too slow can burn the material.

---

## 3. CAM Workflows & Toolpath Strategies
Computer-Aided Manufacturing (CAM) is the bridge between your CAD design and the machine.

### Core Toolpath Strategies
1.  **Profile / Contour:** Cutting along the outline to separate the part from the sheet.
2.  **Pocketing:** Clearing out an internal area to a specific depth (not cutting through).
3.  **Drilling:** Creating vertical holes for screws or alignment.
4.  **Engraving:** Following a line on the surface for text or artwork.

### Nesting & Optimization
**Nesting** is the process of arranging multiple parts on a single sheet to maximize yield and minimize waste.
* **Gap:** Always leave at least `2x Tool Diameter` between parts for stability.
* **Tabs:** Small bridges of material left behind to hold the part in place so it doesn't fly loose when cut.

---

## 4. Design for CNC Fabrication
CNC routers have physical limitations that usually dictate the design logic.

### The "Internal Corner" Problem
Because the cutting tool is round, a CNC router **cannot cut a sharp internal 90° corner**. The radius of the tool will always remain.

!!! tip "Solution: Dog-Bones & T-Bones"
    To fit a rectangular tenon into a slot, we must create **"Dog-Bone" fillets** (over-cutting the corners) to allow the mating part to seat fully square.



### Tolerances & Press-Fit Joinery
For parts to snap together without glue (Press-Fit), tolerances must be exact.
* **Kerf/Runout:** The actual cut width is often slightly larger than the tool diameter due to vibration.
* **Offset:** Designing parts with a `0.1mm - 0.2mm` interference for a tight friction fit.

---

## 5. Assembly & Structural Evaluation
* **Joinery:** Using Mortise & Tenon or Box Joints for mechanical strength.
* **Structural Evaluation:** Checking if the sheet material direction (grain) aligns with the load-bearing requirements of the assembly.
