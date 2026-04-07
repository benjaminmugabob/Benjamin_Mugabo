# Day 1: Foundations of Modeling & Fabrication

## Introduction
Day 1 established the intellectual and practical basis for the ACEIoT Digital Fabrication module. The session emphasized that modern design is not only about geometry; it is computational, material-driven, and production-aware. In this perspective, fabrication is not a final execution step but a core design parameter that shapes decisions from concept development to final validation.

As an MSc student in IoT Embedded Computing Systems, I approached this activity as both a technical exercise and a documentation challenge: to demonstrate design reasoning, reproducibility, and reflective practice through a professional MkDocs workflow.

## Context of Day 1
The class focused on the transition from design intent to physical realization through the **Design → Model → Prototype → Fabricate → Evaluate** continuum. The emphasis was on iterative development, where each prototype functions as evidence that informs the next design decision.

Day 1 also introduced the required post-class outputs:

1. Build and organize a MkDocs Material documentation website.
2. Publish the documentation through GitHub Pages.
3. Conduct and record documentation quality peer review.

## Objectives of the Session
The technical and learning objectives were to:

- Explain modeling as representation of **form, logic, and behavior**.
- Distinguish key digital fabrication paradigms and their implications.
- Understand how **materials, tolerances, and machine constraints** affect design quality.
- Establish documentation as a formal part of engineering workflow.
- Produce and publish structured, reproducible Day 1 records.

## Overview of Digital Fabrication
Digital fabrication integrates digital models with controlled manufacturing processes such as CNC machining, 3D printing, and computer-guided forming methods. The critical principle learned is that **fabrication method is a design choice**: each method constrains and enables specific geometries, tolerances, material behaviors, cost profiles, and sustainability outcomes.

### Key Concepts Learned

#### 1. Modeling Principles
- **Geometric modeling:** Defines dimensions, shape, and explicit form.
- **Parametric/rule-based modeling:** Uses variables and constraints to enable fast design variation.
- **Model intelligence:** A robust model encodes assumptions, not just surfaces.

#### 2. Fabrication Processes
- **Subtractive fabrication:** Removes material (e.g., CNC milling, laser cutting).
- **Additive fabrication:** Builds material layer-by-layer (e.g., FDM 3D printing).
- **Formative fabrication:** Shapes material via molds, pressure, or heat.
- **Hybrid fabrication:** Combines methods to exploit complementary strengths.

#### 3. Technical Insights
- Real systems introduce **error, deformation, and tolerance deviation**.
- Overlooking kerf, tool diameter, wall thickness, or shrinkage causes assembly failure.
- Prototyping is a research activity: failure reveals hidden constraints.

### Importance in Engineering and IoT
For engineering and IoT product development, digital fabrication accelerates transition from concept to functional prototype. It supports enclosure design, fixture development, board integration, and iterative hardware testing. The ability to model with fabrication logic reduces redesign cycles, improves manufacturability, and strengthens system reliability.

## Activities Performed

### Activity 1: Building Documentation with MkDocs Material

#### Step-by-Step Process
1. Set up project dependencies and documentation environment.
2. Organized Day-based Markdown structure under `docs/`.
3. Drafted Day 1 content on course understanding, modeling, and fabrication logic.
4. Added visuals and captions to support reproducibility.
5. Reviewed formatting, heading hierarchy, and page readability in live preview.

#### Tools/Software Used
- `MkDocs`
- `Material for MkDocs`
- `Markdown`
- `Git`
- `GitHub`

#### Methods Followed
- Modular page organization for incremental daily reporting.
- Evidence-based writing: each claim linked to observed process or course concept.
- Iterative refinement through local preview.

#### Representative Commands
```bash
pip install mkdocs-material
mkdocs serve
mkdocs build
```

### Activity 2: Publishing Documentation via GitHub Pages

#### Step-by-Step Process
1. Initialized/versioned the project with Git.
2. Pushed documentation source files to GitHub repository.
3. Configured publishing workflow for static deployment.
4. Deployed and validated public website accessibility.

#### Representative Commands
```bash
git add .
git commit -m "Refine Day 1 documentation"
git push origin main
mkdocs gh-deploy
```

### Activity 3: Documentation Quality and Peer Review

#### Step-by-Step Process
1. Reviewed a peer documentation page using predefined criteria.
2. Evaluated clarity, structure, visual quality, and reproducibility.
3. Wrote concise, constructive feedback and practical improvement points.

#### Review Criteria Applied
- Clarity of technical explanation
- Justification of modeling/fabrication decisions
- Logical navigation and section coherence
- Reproducibility from documentation only
- Professional tone and formatting quality

## Key Concepts Learned

### Modeling Principles
Effective modeling requires explicit constraints, parameter control, and design intent capture. Parametric strategy improves adaptability when fabrication feedback requires dimensional changes.

### Fabrication Processes
Process selection must be made early. For example, subtractive methods require tool-access-aware geometry, while additive methods require overhang and support considerations. These constraints influence part orientation, wall thickness, and assembly interfaces.

### Additional Technical Insights
- Tolerance planning is mandatory for part-fit reliability.
- Prototype evaluation should include dimensional checks and functional checks.
- Documentation quality directly affects collaboration and technology transfer.

## Challenges Encountered

1. **Structural inconsistency in early draft**  
	Initial notes were fragmented and not aligned with required deliverable sections.

2. **Insufficient technical depth**  
	Early text described concepts but did not adequately explain fabrication constraints or modeling rationale.

3. **Evidence and reproducibility gaps**  
	Some steps lacked explicit methods, commands, and clear output statements.

### How Challenges Were Solved
- Reorganized content using a strict academic section hierarchy.
- Added process-level detail (workflow steps, tools, constraints, outputs).
- Incorporated terminology from course foundations: parametric thinking, tolerance, iterative validation, and design-for-fabrication.

## Results / Outputs
By the end of Day 1, the following outputs were achieved:

- A structured MkDocs documentation page for Day 1.
- Local live-preview and static build workflow validated.
- Git-based publication workflow prepared and executed.
- Documentation peer review completed with constructive feedback.
- A coherent record connecting design theory to fabrication practice.

## Reflection and Insights
The most significant lesson from Day 1 is that design quality depends on how early fabrication realities are integrated into modeling decisions. Treating prototyping as evidence, not error, improved both technical judgment and iteration speed.

I also learned that rigorous documentation is an engineering competency. Clear structure, explicit process records, and reflective analysis make work reproducible and professionally communicable. These skills are directly relevant to future IoT hardware projects, where multidisciplinary teams depend on reliable technical records for design handover, testing, and scale-up.

In future sessions, I will strengthen this workflow by adding more quantitative validation (measured tolerances, parameter tables, and test metrics) to further increase the scientific quality of my documentation.

