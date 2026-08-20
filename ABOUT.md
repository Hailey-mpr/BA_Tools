# BA Model Recommender — Project Documentation

## Overview

The **BA Model Recommender** is a single-page web application built for Business Analysts. It recommends the most relevant BA framework or tool based on the problem a user describes or the outcome they need to achieve. Typing "manage stakeholders" surfaces the RACI Chart as the top result; typing "root cause analysis" surfaces the Fishbone Diagram and 5 Whys.

Every model card is clickable and opens a modal containing:

- A **diagram** of the tool drawn using inline SVG
- **Step-by-step instructions** for how to draw the diagram from scratch
- An **elements guide** explaining every component within the diagram

---

## Live Site

> https://hailey-mpr.github.io/BA_Tools

---

## What Was Built

| Feature | Detail |
|---|---|
| Search & recommendation engine | Keyword-weighted scoring algorithm — longer phrase matches score higher |
| Quick-pick chips | Pre-set common BA queries for one-click exploration |
| Category filter pills | Horizontal-scroll filter bar covering 9 BA disciplines |
| 32 BA model entries | Each with description, when-to-use, tags, keywords, diagram, drawing steps, and elements |
| Interactive modal | Opens on card click; closes on Escape, outside click, or × button |
| Relevance badges | "Best Match" and "Strong Match" labels on search results |
| Fully responsive layout | Adapts to desktop, tablet, and mobile |
| Keyboard accessible | Tab to card, Enter to open modal; all interactive elements are focusable |

---

## Tech Stack

The entire application is a **single self-contained HTML file** with no external dependencies, no frameworks, no build step, and no server required.

| Layer | Technology |
|---|---|
| Markup | HTML5 |
| Styling | CSS3 — custom properties (variables), CSS Grid, Flexbox, media queries |
| Logic | Vanilla JavaScript (ES6+) — no libraries or frameworks |
| Diagrams | Inline SVG — hand-authored within the JavaScript data array |
| Hosting | GitHub Pages (static site, no backend) |

---

## How the Diagrams Were Drawn

All 32 diagrams are **hand-authored SVG (Scalable Vector Graphics)** written directly as template literal strings inside the JavaScript `BA_MODELS` data array.

No diagramming software (Visio, Lucidchart, Draw.io) or SVG export tools were used. Each diagram was written using native SVG elements:

| SVG Element | Used For |
|---|---|
| `<rect>` | Boxes, tables, cards, lanes, quadrants, matrix cells |
| `<circle>` | Start/end events (BPMN), stakeholder dots, chance nodes |
| `<ellipse>` | Use case ellipses, onion diagram rings |
| `<polygon>` | Gateways (BPMN, Decision Tree), decision diamonds, arrow heads |
| `<polyline>` | Emotion curves (Customer Journey Map), cumulative lines (Pareto) |
| `<line>` | Arrows, connectors, axis lines, bones (Fishbone), swimlane dividers |
| `<text>` | All labels, values, descriptions, and legends inside diagrams |
| `<path>` | Custom arrow marker heads via `<marker>` + `<defs>` |
| `<defs>` + `<marker>` | Reusable arrowhead definitions for directed flow lines |

Each SVG uses a fixed `viewBox` so it scales cleanly at any screen size. Colours are drawn from the site's CSS custom property palette (`--primary`, `--accent`, `--accent2`) for visual consistency.

---

## Models Covered (32 total across 9 categories)

### Stakeholder Management
- RACI Chart
- Stakeholder Onion Diagram
- Power / Interest Grid

### Requirements
- MoSCoW Prioritisation
- Use Case Diagram
- User Stories
- Requirements Traceability Matrix (RTM)
- Context Diagram

### Process & Workflow
- Business Process Model & Notation (BPMN)
- Swimlane Diagram
- Value Stream Mapping (VSM)
- Flowchart
- SIPOC

### Strategy & Analysis
- SWOT Analysis
- PESTLE Analysis
- Porter's Five Forces
- Business Model Canvas
- Balanced Scorecard

### Problem Solving
- Fishbone Diagram (Ishikawa)
- 5 Whys
- Pareto Analysis (80/20 Rule)

### Decision Making
- Decision Matrix (Weighted Scoring)
- Decision Tree
- Cost–Benefit Analysis (CBA)

### Change Management
- Gap Analysis
- Force Field Analysis
- Kotter's 8-Step Change Model

### User Experience
- Customer Journey Map
- Empathy Map
- Persona

### Data & Information
- Entity Relationship Diagram (ERD)
- Data Flow Diagram (DFD)

---

## Sources and References

The descriptions, element definitions, drawing conventions, and "when to use" guidance for each model are based on the following authoritative sources:

### Business Analysis Standards

- **BABOK® Guide v3** — *A Guide to the Business Analysis Body of Knowledge*, International Institute of Business Analysis (IIBA), 2015.
  The primary reference for requirements elicitation, stakeholder analysis, traceability, and core BA techniques including Use Cases, User Stories, RACI, Context Diagrams, and RTM.
  > https://www.iiba.org/career-resources/a-business-analysis-body-of-knowledge/babok/

- **BCS Business Analysis** (3rd ed.) — Debra Paul, Donald Yeates, James Cadle, BCS Learning & Development, 2014.
  Reference for process modelling (BPMN, swimlanes, flowcharts), stakeholder analysis, and gap analysis.

### Process & Lean

- **Learning to See: Value Stream Mapping to Create Value and Eliminate Muda** — Mike Rother & John Shook, Lean Enterprise Institute, 1998.
  Source for Value Stream Mapping notation, VA/NVA classification, and current-state/future-state mapping.
  > https://www.lean.org/store/book/learning-to-see/

- **BPMN 2.0 Specification** — Object Management Group (OMG), 2011.
  Official specification for BPMN notation: pools, lanes, tasks, gateways, events, and sequence flows.
  > https://www.omg.org/spec/BPMN/2.0/

- **SIPOC** methodology drawn from Six Sigma / DMAIC literature:
  - *The Six Sigma Handbook* (4th ed.) — Thomas Pyzdek & Paul Keller, McGraw-Hill, 2014.

### Strategy

- **Competitive Strategy: Techniques for Analyzing Industries and Competitors** — Michael E. Porter, Free Press, 1980.
  Original source for Porter's Five Forces framework.

- **Business Model Generation** — Alexander Osterwalder & Yves Pigneur, Wiley, 2010.
  Source for the Business Model Canvas and its nine building blocks.
  > https://www.strategyzer.com/library/business-model-generation

- **Balanced Scorecard: Translating Strategy into Action** — Robert S. Kaplan & David P. Norton, Harvard Business Review Press, 1996.
  Original source for the Balanced Scorecard and its four perspectives.

- **PESTLE Analysis** — widely documented in strategic management literature; formulated by Francis Aguilar:
  - *Scanning the Business Environment* — Francis Aguilar, Macmillan, 1967.

- **SWOT Analysis** — attributed to Albert Humphrey (SRI International); widely documented across strategic management texts.

### Problem Solving & Quality

- **Root Cause Analysis via Fishbone (Ishikawa) Diagram** — Kaoru Ishikawa, *Guide to Quality Control*, Asian Productivity Organization, 1976.

- **5 Whys** — Taiichi Ohno, Toyota Production System, documented in:
  - *Toyota Production System: Beyond Large-Scale Production* — Taiichi Ohno, Productivity Press, 1988.

- **Pareto Principle (80/20 Rule)** — Vilfredo Pareto (1897); applied to quality management by Joseph M. Juran:
  - *Juran's Quality Handbook* (5th ed.) — Joseph M. Juran & A. Blanton Godfrey, McGraw-Hill, 1999.

### Change Management

- **Lewin's Force Field Analysis** — Kurt Lewin, *Field Theory in Social Science*, Harper & Row, 1951.

- **Leading Change** — John P. Kotter, Harvard Business Review Press, 1996.
  Original source for Kotter's 8-Step Change Model.

- **Gap Analysis** — standard BA and management consulting technique; documented in BABOK® v3 and general management literature.

### Decision Making

- **Decision Matrix / Weighted Scoring** — widely documented; applied in engineering and management:
  - *The Design of Everyday Things* — Don Norman, Basic Books, 1988 (utility/trade-off evaluation).
  - Also referenced in BABOK® v3 under Decision Analysis.

- **Decision Tree** — classical operations research technique; documented in:
  - *Decision Analysis* — Howard Raiffa, McGraw-Hill, 1968.

- **Cost–Benefit Analysis** — standard public policy and project management technique:
  - HM Treasury *Green Book: Central Government Guidance on Appraisal and Evaluation*, UK Government, 2022.
    > https://www.gov.uk/government/publications/the-green-book-appraisal-and-evaluation-in-central-government

### User Experience & Design Thinking

- **Customer Journey Mapping** — documented in service design literature:
  - *This is Service Design Thinking* — Marc Stickdorn & Jakob Schneider, BIS Publishers, 2010.

- **Empathy Map** — Dave Gray, XPLANE / Strategyzer:
  - *Gamestorming: A Playbook for Innovators, Rulebreakers, and Changemakers* — Dave Gray, Sunni Brown, James Macanufo, O'Reilly, 2010.
  - Updated Empathy Map Canvas: > https://medium.com/the-xplane-collection/updated-empathy-map-canvas-46df22df3c8a

- **Persona** — Alan Cooper, *The Inmates Are Running the Asylum*, Sams Publishing, 1999.
  Original formulation of design personas as a UX tool.

### Data Modelling

- **Entity Relationship Diagram (ERD)** — Peter Chen, "The Entity-Relationship Model — Toward a Unified View of Data", *ACM Transactions on Database Systems*, 1976.

- **Data Flow Diagram (DFD)** — Edward Yourdon & Larry Constantine, *Structured Design*, Yourdon Press, 1979.

---

## Project Structure

```
BA_Tools/
├── index.html    # Complete application (HTML + CSS + JS + SVG diagrams)
├── README.md     # Quick-start guide and GitHub Pages setup
└── ABOUT.md      # This file — full project documentation
```

---

## Contributing

To add a new BA model, add an entry to the `BA_MODELS` array in `index.html` following this structure:

```javascript
{
  id: 33,
  name: "Model Name",
  category: "Category Name",
  description: "One or two sentence description.",
  when: "When to use this model.",
  tags: ["tag1", "tag2"],
  keywords: ["search term 1", "search term 2"],
  diagram: `<svg viewBox="0 0 400 260" ...> ... </svg>`,
  steps: ["Step 1 description.", "Step 2 description."],
  elements: [
    { name: "Element name", desc: "What this element represents." }
  ]
}
```

---

## License

MIT — free to use, adapt, and share with attribution.
