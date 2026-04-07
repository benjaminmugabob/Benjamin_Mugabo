# Day 7 — Digital Fabrication III: PCB Milling

## Objective
The purpose of this session was to fabricate a printed circuit board by translating the Day 3 KiCad design into a physical artifact through CNC milling. The workflow required careful preparation of toolpaths, accurate machine calibration, controlled machining parameters, and systematic inspection of the finished board. In the broader project context, this PCB becomes part of the electronic core that supports the Circuit Brain concept, where circuitry and form work together as a visual metaphor for intelligent systems.

<figure markdown>
![CNC milling setup and machine frame](../images/day_7/IMG-20260402-WA0085.jpg)
<figcaption>The CNC milling machine used for PCB fabrication, shown with the copper-clad workpiece mounted on the bed.</figcaption>
</figure>

## Introduction to PCB Milling
PCB milling is a subtractive digital fabrication method in which copper is selectively removed from a clad board to isolate conductive tracks. Unlike additive processes that build material layer by layer, milling starts with a complete copper surface and removes only the regions that must not conduct. This approach is especially useful for prototyping because it eliminates chemical etching, shortens turnaround time, and allows design iterations to be fabricated directly from digital files.

Three parameters govern the quality of the milled PCB. Tool diameter determines the minimum trace spacing and the sharpness of internal corners. Feed rate controls how quickly the cutter advances across the board; if it is too high, the tool can chatter, deflect, or break, while a feed rate that is too low may generate excess heat and rough edges. Spindle speed influences the cutting action at the tool tip and must be balanced with the board material, cutter geometry, and depth of cut to obtain clean copper isolation.

| Parameter | Technical role | Practical effect |
| --- | --- | --- |
| Tool diameter | Defines the minimum feature size | Smaller tools resolve finer traces but are more fragile |
| Feed rate | Linear advance of the cutter | Affects cutting load, vibration, and surface finish |
| Spindle speed | Tool rotation rate | Determines cutting efficiency and heat generation |
| Depth of cut | Vertical engagement per pass | Controls tool stress and isolation consistency |

## Machine Overview
The machine operates through coordinated motion in the X, Y, and Z axes while the spindle rotates the cutter at high speed. The bed supports the copper-clad board, while the controller interprets the loaded program and converts it into precise motion commands. In PCB fabrication, rigidity and repeatability are essential because even a small positional error can compromise trace isolation or drill alignment.

The software interface used during the session displayed the loaded job, tool progress, and machine status. This made it possible to verify that the milling file was correctly imported before the spindle engaged the board.

<figure markdown>
![Machine interface showing the loaded milling job](../images/day_7/IMG-20260402-WA0079.jpg)
<figcaption>Carbide Motion job screen showing the PCB milling file ready for execution.</figcaption>
</figure>

<figure markdown>
![Machine controller and work area](../images/day_7/IMG-20260402-WA0081.jpg)
<figcaption>The CNC machine, control computer, and work area arranged for the PCB milling workflow.</figcaption>
</figure>

## PCB Design Preparation
The PCB design was prepared in KiCad and exported into manufacturing files that define the traces, holes, and board outline. This preparation stage is crucial because the machine does not interpret schematic intent directly; it executes only the geometry encoded in the toolpath files. Any omission at this stage, such as missing drill data or incorrect layer export, would propagate into the physical board.

The design package typically includes copper isolation paths, hole locations, and the final contour. These elements are translated into tool motions that the milling machine can reproduce with high precision. The software preview serves as a final verification step before machining begins.

<figure markdown>
![Software job information before machining](../images/day_7/IMG-20260402-WA0067.jpg)
<figcaption>Job information and program status displayed before the tool begins milling the PCB.</figcaption>
</figure>

## Toolpath Generation
Toolpath generation bridges the digital layout and the physical process. During this stage, the board artwork is converted into isolation passes that remove a narrow band of copper around each trace, followed by drilling paths for component holes and a contour path for board separation. The objective is to preserve the conductive regions while creating a reliable electrical gap between adjacent tracks.

For PCB work, the geometry of the milling tool is especially important. A smaller cutter can produce finer isolation channels, but it also demands more careful control of feed, spindle speed, and depth. The generated toolpath therefore reflects a balance between feature resolution, machine stability, and production time.

<figure markdown>
![PCB toolpath preview in the control software](../images/day_7/IMG-20260402-WA0047.jpg)
<figcaption>Milled PCB surface showing the translated trace geometry and the routed isolation paths.</figcaption>
</figure>

## Machine Calibration
Calibration established the reference position of the machine before machining began. The workpiece was secured on the bed, the cutting bit was installed, and the spindle position was aligned with the intended origin. Z-height calibration was particularly important because the milling depth must be shallow enough to clear only the copper layer without excessively removing the underlying substrate.

This step also included confirming that the selected cutter was appropriate for the required trace resolution. A fine bit was used to achieve narrow isolation channels, but because such cutters are delicate, handling had to be careful and deliberate. The images below show both the tool itself and the operator positioning it in the machine.

<figure markdown>
![PCB milling bit held before installation](../images/day_7/IMG-20260402-WA0083.jpg)
<figcaption>The fine cutting tool selected for trace isolation, illustrating the small diameter required for detailed PCB work.</figcaption>
</figure>

<figure markdown>
![Tool installation and calibration inside the machine](../images/day_7/IMG-20260402-WA0087.jpg)
<figcaption>Hands-on calibration of the cutter inside the machine before milling the board.</figcaption>
</figure>

<figure markdown>
![Board fixed on the machine bed during setup](../images/day_7/IMG-20260402-WA0051.jpg)
<figcaption>The copper-clad board secured on the bed, ready for origin setting and cutting.</figcaption>
</figure>

## Milling Process
Once the origin was confirmed, the machine began removing copper according to the generated toolpath. The isolation pass traced the circuit geometry, while later passes refined the outline and drilled the required holes. Throughout the operation, the spindle had to maintain a stable cutting action so that the trace width remained consistent and the board surface stayed free of major tear-out.

The machining sequence was documented at multiple stages, showing the cutter in motion and the board gradually taking shape. These images are important because they reveal the subtractive nature of PCB fabrication: each pass removes only the copper necessary to electrically separate the tracks.

<figure markdown>
![Milling in progress on the copper board](../images/day_7/IMG-20260402-WA0049.jpg)
<figcaption>The cutter removing copper during the trace-isolation stage.</figcaption>
</figure>

<figure markdown>
![Milling progress with the spindle close to the workpiece](../images/day_7/IMG-20260402-WA0053.jpg)
<figcaption>Fine-detail milling in progress, with copper dust accumulating around the toolpath.</figcaption>
</figure>

<figure markdown>
![Machine view during cutting](../images/day_7/IMG-20260402-WA0055.jpg)
<figcaption>Another angle of the PCB milling pass, showing the tool engaging the board surface.</figcaption>
</figure>

<figure markdown>
![Board still mounted after milling passes](../images/day_7/IMG-20260402-WA0057.jpg)
<figcaption>Intermediate result after machining, with traces and outline becoming visible.</figcaption>
</figure>

<figure markdown>
![Milling area with dust and partial isolation paths](../images/day_7/IMG-20260402-WA0059.jpg)
<figcaption>Isolation milling continued across the board, leaving clear copper-free channels.</figcaption>
</figure>

<figure markdown>
![Machine close-up during PCB milling](../images/day_7/IMG-20260402-WA0061.jpg)
<figcaption>The spindle continuing the copper isolation pass near the end of the job.</figcaption>
</figure>

<figure markdown>
![Machine cutting with board clamped in place](../images/day_7/IMG-20260402-WA0065.jpg)
<figcaption>The machine operating in a controlled state with the copper board clamped securely to the bed.</figcaption>
</figure>

<figure markdown>
![Machine frame and workpiece during milling](../images/day_7/IMG-20260402-WA0071.jpg)
<figcaption>The cutter working across the board while the enclosure preserves alignment and safety.</figcaption>
</figure>

<figure markdown>
![Continuation of the milling run](../images/day_7/IMG-20260402-WA0073.jpg)
<figcaption>Ongoing milling operation as the PCB trace network is progressively isolated.</figcaption>
</figure>

<figure markdown>
![Final cutting pass near the board outline](../images/day_7/IMG-20260402-WA0075.jpg)
<figcaption>The board approaching completion as the cutter refines the outer boundary and final features.</figcaption>
</figure>

## Hands-on Practice
Hands-on practice formed an important part of the session because PCB milling depends on careful manual setup even though the tool motion itself is automated. The operator handled the cutter, checked the machine interface, and observed the workpiece alignment while the job progressed. This practical engagement helped connect the digital instructions with the material behavior of copper-clad laminate.

The practice images also show the collaborative and iterative nature of digital fabrication. Small adjustments to the bit, the stock position, or the job setup can determine whether the final board meets fabrication tolerances.

<figure markdown>
![Operator handling the cutter during setup](../images/day_7/IMG-20260402-WA0089.jpg)
<figcaption>Manual handling of the tool during setup, emphasizing the precision required before machining starts.</figcaption>
</figure>

<figure markdown>
![Workpiece inspection during the milling session](../images/day_7/IMG-20260402-WA0038.jpg)
<figcaption>Inspection of the board during the process to verify positioning and toolpath alignment.</figcaption>
</figure>

<figure markdown>
![Board held for inspection after milling](../images/day_7/IMG-20260402-WA0044.jpg)
<figcaption>The milled PCB being examined by hand to confirm that the isolation paths were correctly produced.</figcaption>
</figure>

## Observations
The most important observation from the session is that board quality is determined by the consistency of the trace isolation and the accuracy of the drilled holes. A successful PCB milling pass should leave clean copper channels, visible trace boundaries, and an outline that remains dimensionally faithful to the design. Burrs, incomplete isolation, and uneven milling depth indicate that the calibration or cutting parameters need refinement.

The finished board in this session shows that the toolpath tracked the design closely. The trace width is visually consistent, the hole positions are readable, and the outline follows the intended geometry. Residual copper dust and slight surface marks are expected in a milling-based process, but these do not prevent the board from being evaluated as a successful prototype.

| Quality criterion | What was evaluated | Result |
| --- | --- | --- |
| Trace isolation | Clear separation between adjacent copper tracks | Acceptable |
| Hole accuracy | Component and alignment holes aligned with the layout | Acceptable |
| Outline fidelity | Board perimeter matched the design geometry | Acceptable |
| Surface finish | Copper surface contained minor machining marks | Typical for milling |

## Final PCB Results
The final PCB demonstrates the value of subtractive fabrication for rapid prototyping. The board preserves the intended circuit geometry while removing only the copper needed to create electrical separation. The resulting pattern is suitable for downstream steps such as component soldering, electrical testing, and integration into the broader Circuit Brain artifact.

<figure markdown>
![Completed PCB close-up](../images/day_7/IMG-20260402-WA0024.jpg)
<figcaption>Close-up of the milled PCB showing clean isolation channels and the completed trace network.</figcaption>
</figure>

<figure markdown>
![Completed PCB on the machine bed](../images/day_7/IMG-20260402-WA0051.jpg)
<figcaption>The finished board still mounted on the bed, showing the board outline and trace isolation in context.</figcaption>
</figure>

## Challenges Encountered
The main challenges were securing the copper board firmly enough to prevent movement, setting the correct cutting depth, and maintaining a stable toolpath during fine isolation milling. Because PCB traces are narrow, even slight overcutting can damage the electrical pathway or undercut the surrounding copper. Tool handling also required caution, since the cutters used for PCB milling are delicate and can break if they are loaded incorrectly.

Another practical challenge was balancing speed with quality. A conservative feed rate helps protect the cutter and improve cut definition, but it also increases runtime. The session therefore required a compromise between precision and efficiency.

## Key Learnings
- PCB milling is a direct subtractive process that converts digital trace layouts into physical copper isolation.
- Tool diameter is one of the most important constraints because it governs the minimum achievable feature size.
- Feed rate and spindle speed must be tuned together to avoid chatter, overheating, and tool breakage.
- Accurate calibration of the X, Y, and Z origin is essential for trace alignment and board quality.
- Visual inspection after milling is necessary to confirm electrical isolation, drilling accuracy, and edge quality.

## Conclusion
Day 7 demonstrated the complete PCB milling workflow from digital preparation to physical fabrication. The session reinforced the relationship between design intent and manufacturing reality: a clean PCB depends not only on accurate CAD data, but also on disciplined calibration, appropriate cutting parameters, and careful observation during machining. The resulting board provides a functional substrate for later assembly and supports the technical ambition of the overall Circuit Brain project.

## Image Gallery

<div class="grid cards" markdown>

- ![](../images/day_7/IMG-20260402-WA0024.jpg)
- ![](../images/day_7/IMG-20260402-WA0038.jpg)
- ![](../images/day_7/IMG-20260402-WA0044.jpg)
- ![](../images/day_7/IMG-20260402-WA0047.jpg)
- ![](../images/day_7/IMG-20260402-WA0049.jpg)
- ![](../images/day_7/IMG-20260402-WA0051.jpg)
- ![](../images/day_7/IMG-20260402-WA0053.jpg)
- ![](../images/day_7/IMG-20260402-WA0055.jpg)
- ![](../images/day_7/IMG-20260402-WA0057.jpg)
- ![](../images/day_7/IMG-20260402-WA0059.jpg)
- ![](../images/day_7/IMG-20260402-WA0061.jpg)
- ![](../images/day_7/IMG-20260402-WA0065.jpg)
- ![](../images/day_7/IMG-20260402-WA0067.jpg)
- ![](../images/day_7/IMG-20260402-WA0069.jpg)
- ![](../images/day_7/IMG-20260402-WA0071.jpg)
- ![](../images/day_7/IMG-20260402-WA0073.jpg)
- ![](../images/day_7/IMG-20260402-WA0075.jpg)
- ![](../images/day_7/IMG-20260402-WA0077.jpg)
- ![](../images/day_7/IMG-20260402-WA0079.jpg)
- ![](../images/day_7/IMG-20260402-WA0081.jpg)
- ![](../images/day_7/IMG-20260402-WA0083.jpg)
- ![](../images/day_7/IMG-20260402-WA0085.jpg)
- ![](../images/day_7/IMG-20260402-WA0087.jpg)
- ![](../images/day_7/IMG-20260402-WA0089.jpg)

</div>
