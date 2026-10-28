# ScholarDesk • Multi-Agent AI Research Lab

An autonomous, multi-agent academic research laboratory built specifically for **research scholars, Master's students, and PhD candidates**. The platform deconstructs complex topics into ground-truth problem statements, literature extraction matrices, experimental methodologies, and complete publication-grade research papers.

---

## 📁 Complete File System Tree

```text
C:\Users\Kaleem\.gemini\antigravity\scratch\multi_agent_ai_research_lab/
│
├── workflows/                                       # n8n Automation Engine Workflows
│   ├── multi_agent_ai_research_lab.json             # Original manual-trigger workflow
│   └── multi_agent_ai_research_lab_webhook.json     # Webhook-enabled workflow (POST /webhook/research-task)
│
├── frontend/                                        # ScholarDesk Research Studio Frontend
│   ├── index.html                                   # Instant-launch standalone web application (Zero install!)
│   ├── package.json                                 # Vite + React 18 dependencies & scripts
│   ├── vite.config.js                               # Vite bundler configuration (port 3000)
│   ├── tailwind.config.js                           # Tailwind typography & theme configuration
│   ├── postcss.config.js                            # PostCSS autprefixer configuration
│   └── src/
│       ├── main.jsx                                 # React application entry point
│       ├── index.css                                # Global styling & custom academic scrollbars
│       ├── App.jsx                                  # Complete ScholarDesk workspace component
│       └── components/                              # Modular sub-components directory
│
└── README.md                                        # System documentation & setup guide
```

---

## 📄 File Inventory & Detailed Descriptions

### 1. `workflows/` (n8n Multi-Agent Workflow Engine)
* **[`multi_agent_ai_research_lab.json`](file:///C:/Users/Kaleem/.gemini/antigravity/scratch/multi_agent_ai_research_lab/workflows/multi_agent_ai_research_lab.json)**
  * The exact workflow you provided. Uses a manual trigger to run inside n8n canvas for testing and debugging.
* **[`multi_agent_ai_research_lab_webhook.json`](file:///C:/Users/Kaleem/.gemini/antigravity/scratch/multi_agent_ai_research_lab/workflows/multi_agent_ai_research_lab_webhook.json)**
  * Production webhook version. Replaces manual trigger with `POST /webhook/research-task` and appends a `Respond to Webhook` node with CORS headers (`Access-Control-Allow-Origin: *`) to communicate directly with the frontend.
  * Coordinates 4 cognitive agents:
    - **Agent 1:** Problem Formulation & Research Planner
    - **Agent 2:** Literature & Gap Analyst (queries Tavily Search)
    - **Agent 3:** Feasibility & Fact Auditor
    - **Agent 4:** Research Paper & Proposal Author

### 2. `frontend/` (ScholarDesk Academic Workspace)
* **[`index.html`](file:///C:/Users/Kaleem/.gemini/antigravity/scratch/multi_agent_ai_research_lab/frontend/index.html)**
  * The active, standalone ScholarDesk workspace running live on `http://localhost:3000`.
  * Features the left Obsidian workspace sidebar, top breadcrumb toolbar, 4 KPI metric cards, and 4 dedicated tabs:
    1. **📄 Complete Research Paper:** Generates full-length academic preprint with Abstract, 1. Intro, 2. Related Work, 3. Problem Formulation, 4. Methodology, 5. Evaluation with benchmark tables, 6. Discussion, 7. Conclusion, and References.
    2. **Overview & Problem Statement:** Validated industry bottleneck, core hypothesis, and dissertation research questions (`RQ1..RQ3`).
    3. **Literature Matrix:** Standardized empirical comparison table with venue badges, datasets, outcomes, and limitations.
    4. **BibTeX & Citations:** Syntax-highlighted `.bib` library with one-click export.
  * Instant export actions: **Download `.tex`** (LaTeX for Overleaf), **Download `.md`**, **Copy BibTeX**, and **Print / PDF**.
* **[`src/App.jsx`](file:///C:/Users/Kaleem/.gemini/antigravity/scratch/multi_agent_ai_research_lab/frontend/src/App.jsx)**
  * Modular React 18 component source matching `index.html`.
* **[`package.json`](file:///C:/Users/Kaleem/.gemini/antigravity/scratch/multi_agent_ai_research_lab/frontend/package.json)**
  * Contains project metadata, dependencies (React 18, Tailwind CSS, Lucide), and scripts (`npm run dev`, `npm run build`).
* **[`vite.config.js`](file:///C:/Users/Kaleem/.gemini/antigravity/scratch/multi_agent_ai_research_lab/frontend/vite.config.js)**
  * Vite development server configuration set to port 3000.
* **[`tailwind.config.js`](file:///C:/Users/Kaleem/.gemini/antigravity/scratch/multi_agent_ai_research_lab/frontend/tailwind.config.js)** & **[`postcss.config.js`](file:///C:/Users/Kaleem/.gemini/antigravity/scratch/multi_agent_ai_research_lab/frontend/postcss.config.js)**
  * Styling pipeline with Plus Jakarta Sans and Newsreader editorial serif typography.

---

## 🚀 How to Run

### Live URL (Currently Running)
The workspace is actively hosted by Python's HTTP server in the background:
👉 **[http://localhost:3000](http://localhost:3000)**

### Option A: Direct Browser Launch
Open `frontend/index.html` in any browser. It runs immediately with zero dependencies.

### Option B: Run via Vite
```bash
cd frontend
npm install
npm run dev
```
