# BA Model Recommender

A single-page web tool that recommends the right Business Analysis framework or model based on the problem you're trying to solve or the outcome you need.

## Live Demo

> _Add your GitHub Pages URL here once enabled_

## What it does

Type a challenge or outcome into the search bar — for example "manage stakeholders" or "prioritise requirements" — and the tool instantly surfaces the most relevant BA models, ranked by relevance, with a description and guidance on when to use each one.

**Quick-pick chips** let you explore common BA scenarios with one click.  
**Category filters** let you browse by discipline.

## Models covered (32 total)

| Category | Models |
|---|---|
| Stakeholder Management | RACI Chart, Stakeholder Onion Diagram, Power/Interest Grid |
| Requirements | MoSCoW Prioritisation, Use Case Diagram, User Stories, RTM, Context Diagram |
| Process & Workflow | BPMN, Swimlane Diagram, Value Stream Mapping, Flowchart, SIPOC |
| Strategy & Analysis | SWOT, PESTLE, Porter's Five Forces, Business Model Canvas, Balanced Scorecard |
| Problem Solving | Fishbone Diagram, 5 Whys, Pareto Analysis |
| Decision Making | Decision Matrix, Decision Tree, Cost–Benefit Analysis |
| Change Management | Gap Analysis, Force Field Analysis, Kotter's 8-Step Model |
| User Experience | Customer Journey Map, Empathy Map, Persona |
| Data & Information | ERD, Data Flow Diagram |

## Usage

No installation or server needed. Just open `index.html` in any modern browser.

```
git clone https://github.com/<your-username>/BA_Tools.git
cd BA_Tools
# open index.html in your browser
```

## Hosting on GitHub Pages

1. Go to your repository on GitHub
2. Click **Settings → Pages**
3. Under **Source**, select **Deploy from a branch**
4. Choose `main` branch and `/ (root)` folder, then click **Save**
5. Your site will be live at `https://<your-username>.github.io/BA_Tools`

## Tech stack

- Plain HTML, CSS, and JavaScript — no frameworks, no build step, no dependencies
- Fully self-contained in a single file (`index.html`)

## Contributing

Pull requests are welcome. To add a new model, add an entry to the `BA_MODELS` array in `index.html` following the existing structure.

## License

MIT
