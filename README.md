<p align="center">
  <img src="assets/banner.png" alt="FYP Thesis Audit Banner" width="100%" />
</p>

<h1 align="center">📝 FYP Thesis Audit</h1>

<p align="center">
  <strong>AI-Powered Project Auditor for FYP Thesis Writing</strong><br/>
  Audit any software project step-by-step → Generate thesis-ready documentation → Write your thesis with AI
</p>

<p align="center">
  <a href="#-quick-start"><img src="https://img.shields.io/badge/Get_Started-blue?style=for-the-badge" alt="Get Started" /></a>
  <a href="#-supported-projects"><img src="https://img.shields.io/badge/Flutter-02569B?style=for-the-badge&logo=flutter&logoColor=white" alt="Flutter" /></a>
  <a href="#-supported-projects"><img src="https://img.shields.io/badge/React-61DAFB?style=for-the-badge&logo=react&logoColor=black" alt="React" /></a>
  <a href="#-supported-projects"><img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python" /></a>
  <a href="#-supported-projects"><img src="https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=nodedotjs&logoColor=white" alt="Node.js" /></a>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/University-Malakand-purple?style=flat-square" alt="UoM" />
  <img src="https://img.shields.io/badge/Department-Computer_Science-green?style=flat-square" alt="CS" />
  <img src="https://img.shields.io/badge/License-MIT-yellow?style=flat-square" alt="MIT" />
  <img src="https://img.shields.io/github/stars/rahimdev4/FYP-Thesis-Audit?style=flat-square" alt="Stars" />
</p>

---

## 🤔 What Is This?

Writing a **Final Year Project (FYP) thesis** is hard. You spend weeks analyzing your own project, documenting features, drawing diagrams, and formatting chapters — all manually.

**FYP Thesis Audit** automates the hardest part: **understanding and documenting your project.**

It gives any AI assistant (ChatGPT, Gemini, Claude, Copilot) a structured set of instructions to:

1. 🔍 **Audit** your entire codebase in **5 small steps** (no token limit issues!)
2. 📄 **Generate** 5 focused audit files covering every aspect of your project
3. 📝 **Write** your thesis chapter-by-chapter using the audit data

> **Built for University of Malakand CS Department** thesis format — but works for any university with minor adjustments.

---

## ✨ What You Get

| Output | Description |
|--------|-------------|
| 📊 **5 Audit Files** | Complete project documentation split into manageable parts |
| 🗃️ **ERD Data** | All entities, attributes, relationships — ready for diagrams |
| 📈 **DFD Data** | Level-0 and Level-1 data flow specifications |
| 👤 **Use Case Data** | All actors, use cases, include/extend relationships |
| 📸 **Screenshot Guide** | Exactly which screens to capture and where they go |
| 🧪 **Test Cases** | Pre-built test case table for Chapter 7 |
| 📖 **Thesis Structure** | Complete 8-chapter format with formatting rules |
| 🤖 **AI Prompts** | Ready-to-use prompts to generate each chapter |

---

## 🚀 Quick Start

### Prerequisites
- Any AI coding assistant: **Gemini Code Assist**, **GitHub Copilot**, **Cursor**, **ChatGPT**, **Claude**, etc.
- Your FYP project source code

### Step 1: Clone This Repo

```bash
git clone https://github.com/rahimdev4/FYP-Thesis-Audit.git
```

### Step 2: Copy to Your Project

```bash
# Copy the skill folder into your FYP project
cp -r FYP-Thesis-Audit/skill/ /path/to/your/project/thesis-audit/
```

**Examples:**
```bash
# Flutter app
cp -r FYP-Thesis-Audit/skill/ ~/Desktop/MyFlutterApp/thesis-audit/

# React web app
cp -r FYP-Thesis-Audit/skill/ ~/Desktop/MyWebApp/thesis-audit/

# Python project
cp -r FYP-Thesis-Audit/skill/ ~/Desktop/MyPythonApp/thesis-audit/
```

### Step 3: Run the Audit (5 Steps)

Open your project in any AI coding assistant and run **one step at a time**:

#### 🔹 Step 1 — Project Overview & Tech Stack
```
Read `thesis-audit/audit_prompt.md`.
Run STEP 1 only. Generate `AUDIT_01_overview.md` in the project root.
Scan the full project structure, read dependency files, and document 
the tech stack. Follow the template exactly.
```

#### 🔹 Step 2 — Features & Screens
```
Read `thesis-audit/audit_prompt.md`.
Run STEP 2 only. Generate `AUDIT_02_features.md` in the project root.
Read every screen/page file and document all features, user flows,
and screen-by-screen details.
```

#### 🔹 Step 3 — Data Models & Database
```
Read `thesis-audit/audit_prompt.md`.
Run STEP 3 only. Generate `AUDIT_03_database.md` in the project root.
Read all model files, database services, and document the complete
database design with entity relationships.
```

#### 🔹 Step 4 — Auth, APIs & Backend
```
Read `thesis-audit/audit_prompt.md`.
Run STEP 4 only. Generate `AUDIT_04_backend.md` in the project root.
Read authentication and API service files. Document all auth flows,
API integrations, and backend services.
```

#### 🔹 Step 5 — UI Design, Diagrams & Testing
```
Read `thesis-audit/audit_prompt.md`.
Run STEP 5 only. Generate `AUDIT_05_ui_diagrams_testing.md` in the project root.
Read theme files, compile diagram data from previous audit files,
and create test cases. Reference AUDIT_01 through AUDIT_04 for context.
```

> ✅ After all 5 steps, you'll have **5 audit files** with complete project documentation!

### Step 4: Generate Your Thesis

Use these prompts to write each chapter (one at a time):

```
Read all 5 audit files (AUDIT_01 through AUDIT_05) for project details.
Read `thesis-audit/thesis_structure.md` for the thesis format.

Write Chapter [X]: [CHAPTER TITLE] of my FYP thesis.
Follow University of Malakand CS Department formatting.
Use only data from the audit files. Do not make up features.
Target: [X] pages.
```

| Chapter | Prompt | Audit Files to Reference |
|---------|--------|------------------------|
| Chapter 1: Introduction | Write background, objectives, scope | AUDIT_01, AUDIT_02 |
| Chapter 2: System Analysis | Write current vs proposed system | AUDIT_02, AUDIT_05 |
| Chapter 3: Conceptual DB Design | Write ERD, entity descriptions | AUDIT_03 |
| Chapter 4: Physical DB Design | Write table structures, types | AUDIT_03 |
| Chapter 5: Functional Modelling | Write DFD, Use Case diagrams | AUDIT_05 |
| Chapter 6: UI & Features | Write screen descriptions | AUDIT_02, AUDIT_05 |
| Chapter 7: System Testing | Write test cases | AUDIT_05 |
| Chapter 8: Conclusion | Write summary, future work | AUDIT_01, AUDIT_05 |

---

## 📁 Repository Structure

```
FYP-Thesis-Audit/
├── README.md                          # This file
├── LICENSE                            # MIT License
├── skill/                             # ← Copy this folder to your project
│   ├── audit_prompt.md                # AI instructions (5-step audit)
│   ├── audit_template.md              # Full template reference
│   └── thesis_structure.md            # UoM thesis format + chapter guides
└── examples/
    └── NoteNest_PROJECT_AUDIT.md      # Real example audit (NoteNest app)
```

### What Gets Generated in Your Project
```
your-project/
├── thesis-audit/                      # (copied from this repo)
│   ├── audit_prompt.md
│   ├── audit_template.md
│   └── thesis_structure.md
├── AUDIT_01_overview.md               # ← Generated: Overview & Tech Stack
├── AUDIT_02_features.md               # ← Generated: Features & Screens
├── AUDIT_03_database.md               # ← Generated: Data Models & Database
├── AUDIT_04_backend.md                # ← Generated: Auth, APIs & Backend
└── AUDIT_05_ui_diagrams_testing.md    # ← Generated: UI, Diagrams & Testing
```

---

## ❓ Why 5 Steps Instead of 1?

| Problem with 1-Step | Solution with 5 Steps |
|---------------------|----------------------|
| ❌ AI hits **token limits** on large projects | ✅ Each step is small (~200-300 lines) |
| ❌ AI **skips details** to fit everything | ✅ Each step is focused and thorough |
| ❌ If it fails, you **lose everything** | ✅ If one step fails, retry just that step |
| ❌ Takes 10+ minutes in one go | ✅ Each step takes 2-3 minutes |
| ❌ Can't review as you go | ✅ Review each part before continuing |

---

## 📋 Thesis Chapters (UoM Format)

| Chapter | Title | Pages | Key Content |
|---------|-------|-------|-------------|
| **1** | Introduction | 5-6 | Background, problem statement, objectives, scope |
| **2** | System Analysis | 5-6 | Current vs proposed system, feasibility, requirements |
| **3** | Conceptual Database Design | 5-6 | ER Diagram, entity-attribute descriptions, data dictionary |
| **4** | Physical Database Design | 4-5 | Table structures, data types, constraints |
| **5** | Functional Modelling | 5-6 | DFD Level-0, DFD Level-1, Use Case Diagram |
| **6** | User Interface & Features | 6-8 | Screenshots + description of every screen |
| **7** | System Testing | 3-4 | Test strategy, test cases table, evidence |
| **8** | Conclusion & Future Work | 2-3 | Summary, challenges, future enhancements |

### Formatting Rules

| Rule | Specification |
|------|--------------|
| Font | Times New Roman, 12pt body |
| Headings | 14pt Bold, chapter titles ALL-CAPS |
| Spacing | 1.5 line spacing |
| Margins | 1 inch (Left: 1.5 inch for binding) |
| Figures | Numbered by chapter: Figure 3.1, Figure 6.5 |
| Tables | Numbered by chapter: Table 4.1, Table 7.1 |
| Citations | Numeric style: [1], [2], [3] |
| Total Pages | 50-70 pages |

---

## 🔧 Supported Projects

| Framework | Language | Type |
|-----------|----------|------|
| **Flutter** | Dart | Mobile Apps (Android/iOS) |
| **React / Next.js** | JavaScript/TypeScript | Web Apps |
| **React Native** | JavaScript | Mobile Apps |
| **Node.js / Express** | JavaScript | Backend APIs |
| **Django / Flask** | Python | Web Apps / APIs |
| **Laravel** | PHP | Web Apps |
| **Spring Boot** | Java/Kotlin | Backend APIs |
| **SwiftUI** | Swift | iOS Apps |
| **Android Native** | Kotlin/Java | Android Apps |
| **ASP.NET** | C# | Web Apps / APIs |

---

## 💡 Pro Tips

### For Better Results
- ✅ Make sure your project **builds** before auditing
- ✅ Run **one step at a time** — don't ask for multiple steps together
- ✅ **Review each audit file** before moving to the next step
- ✅ If a step fails or is incomplete, just **retry that step**

### For Thesis Writing
- 📖 Write **one chapter at a time** — don't ask for all 8 at once
- 📸 Take **screenshots** yourself for Chapter 6
- 📊 Ask AI to **generate diagrams** (ERD, DFD, Use Case) from the audit data
- ✏️ **Review and edit** — AI writes the draft, you polish it
- 📝 Fill in **placeholders** manually (student name, supervisor, roll numbers)

### For Diagrams
After the audit, ask:
```
Using the ERD data from AUDIT_03_database.md, 
generate an Entity Relationship Diagram for my project.
```
```
Using the DFD data from AUDIT_05_ui_diagrams_testing.md,
generate a DFD Level-0 and DFD Level-1 diagram.
```

Free diagram tools: [draw.io](https://app.diagrams.net) | [Lucidchart](https://lucid.app) | [Mermaid Live](https://mermaid.live)

---

## 📖 Complete Workflow

```
Your FYP Project (e.g., MyApp/)
         │
         ▼
    ┌─────────────────┐
    │  Copy skill/     │  ← Clone repo, copy skill folder
    │  to your project │
    └──────┬──────────┘
           │
     ┌─────┴─────┐
     ▼           ▼
 Step 1       Step 2       Step 3       Step 4       Step 5
 Overview     Features     Database     Backend      UI/Testing
    │            │            │            │            │
    ▼            ▼            ▼            ▼            ▼
 AUDIT_01     AUDIT_02     AUDIT_03     AUDIT_04     AUDIT_05
    │            │            │            │            │
    └────────────┴────────────┴────────────┴────────────┘
                              │
                              ▼
                 ┌───────────────────────┐
                 │  AI reads all 5 files  │
                 │  + thesis_structure    │
                 └───────────┬───────────┘
                             │
                    ┌────────┴────────┐
                    ▼                 ▼
              Chapter 1          Chapter 2  ...  Chapter 8
                    │                 │              │
                    └────────┬────────┘              │
                             ▼                       │
                   Complete FYP Thesis ◄─────────────┘
                      (50-70 pages)
```

---

## 🤝 Contributing

Contributions welcome! Ideas:
- Add thesis formats for other Pakistani universities (COMSATS, NUST, FAST, etc.)
- Add thesis formats for international universities
- Improve audit prompts for specific frameworks
- Add more example audits
- Translate to Urdu

1. Fork → 2. Branch → 3. Add your format → 4. Pull Request

---

## 📄 License

**MIT License** — free to use, modify, and share. If it helps, give it a ⭐!

---

## 👨‍💻 Author

**Rahim Dev** — [@rahimdev4](https://github.com/rahimdev4)

> Built from experience writing the NoteNest FYP thesis at University of Malakand, CS Department.

---

<p align="center">
  <strong>If this saves you time on your thesis, please ⭐ star this repo!</strong><br/>
  <sub>Made with ❤️ for CS students at University of Malakand and beyond</sub>
</p>
