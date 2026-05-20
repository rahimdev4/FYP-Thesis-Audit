# 🎓 University of Malakand — FYP Thesis Structure

> **Department:** Computer Science
> **Format:** Based on UoM CS Department standard thesis format (2021-2025 sessions)

---

## Formatting Rules

| Rule | Specification |
|------|--------------|
| **Font** | Times New Roman |
| **Body Size** | 12pt |
| **Heading Size** | 14pt Bold (Chapter titles: ALL-CAPS) |
| **Sub-heading** | 12pt Bold |
| **Line Spacing** | 1.5 |
| **Margins** | 1 inch all sides (Left: 1.5 inch for binding) |
| **Page Numbers** | Bottom center, starting from Chapter 1 |
| **Figures** | Numbered by chapter (e.g., Figure 3.1, Figure 6.5) |
| **Tables** | Numbered by chapter (e.g., Table 4.1) |
| **Citations** | Numeric style: [1], [2], [3] |
| **Paper Size** | A4 |
| **Alignment** | Justified |
| **Total Pages** | 50-70 pages (typical) |

---

## Front Matter (Before Chapter 1)

### 1. Title Page
```
[University Logo]

UNIVERSITY OF MALAKAND
DEPARTMENT OF COMPUTER SCIENCE

[PROJECT TITLE IN ALL-CAPS]

A Final Year Project submitted in partial fulfillment
of the requirements for the degree of
Bachelor of Science in Computer Science

Submitted by:
[Student Name 1] (Roll No: [XXX])
[Student Name 2] (Roll No: [XXX])

Supervised by:
[Supervisor Name]
[Designation]

Session: [2021-2025]
```

### 2. Approval / Certificate Page
```
CERTIFICATE

This is to certify that the project entitled "[PROJECT TITLE]" has been 
completed by [Student Names] under the supervision of [Supervisor Name] 
in partial fulfillment of the requirements for the degree of BS Computer Science.

Supervisor: _______________
[Supervisor Name]

Head of Department: _______________
[HOD Name]

External Examiner: _______________

Date: _______________
```

### 3. Dedication
```
DEDICATION

[Student's personal dedication — 2-3 lines]
Example: "We dedicate this work to our parents, who have always 
supported and encouraged us throughout our academic journey."
```

### 4. Acknowledgment
```
ACKNOWLEDGMENT

[Thank supervisor, HOD, department, family, friends, Allah — 1 page]
```

### 5. Abstract
```
ABSTRACT

[150-250 words summarizing the entire project]
- What problem does it solve?
- What technology was used?
- What are the key features?
- What was the outcome?
```

### 6. Table of Contents
```
TABLE OF CONTENTS

[Auto-generated in Word — use heading styles]
```

### 7. List of Figures
```
LIST OF FIGURES

[Auto-generated — list all Figure X.X entries]
```

### 8. List of Tables
```
LIST OF TABLES

[Auto-generated — list all Table X.X entries]
```

---

## Chapter 1: INTRODUCTION (5-6 pages)

### What to Include:
| Section | Content | Source from Audit |
|---------|---------|-------------------|
| 1.1 Background | General context of the problem domain | Section 1 (Overview) |
| 1.2 Problem Statement | What problem exists, why current solutions fail | Section 16 (Current System) |
| 1.3 Objectives | 4-6 specific, measurable objectives | Section 1 (Objectives) |
| 1.4 Scope | What's included and excluded | Section 1 (Scope) |
| 1.5 Motivation | Why this project matters | Section 1 (Motivation) |
| 1.6 Technologies Used | Brief overview of tech stack | Section 2 (Tech Stack) |
| 1.7 Key Features | High-level feature list | Section 4 (Features) |
| 1.8 Report Organization | One-line summary of each chapter | All sections |

### Writing Style:
- Start broad (education technology / healthcare / whatever domain)
- Narrow down to the specific problem
- Present your project as the solution
- Be formal, academic tone
- Include 1-2 figures (app icon, main screen)

---

## Chapter 2: SYSTEM ANALYSIS (5-6 pages)

### What to Include:
| Section | Content | Source from Audit |
|---------|---------|-------------------|
| 2.1 Introduction | Brief intro to system analysis | — |
| 2.2 Current System | How things are done WITHOUT your app | Section 16 (Current System) |
| 2.3 Problems in Current System | List specific problems | Section 16 |
| 2.4 Proposed System | Your app as the solution | Section 16 (Proposed System) |
| 2.5 Comparison Table | Current vs Proposed (table) | Section 16 |
| 2.6 Feasibility Study | Technical, economic, operational feasibility | Section 2 (Tech Stack) |
| 2.7 User Roles | Types of users and what they can do | Section 13 (Actors) |
| 2.8 System Requirements | Hardware + software requirements | Section 2 |

### Writing Style:
- Compare old vs new clearly
- Use comparison tables
- Be critical of current problems
- Show how your system fixes each problem

---

## Chapter 3: CONCEPTUAL DATABASE DESIGN (5-6 pages)

### What to Include:
| Section | Content | Source from Audit |
|---------|---------|-------------------|
| 3.1 Introduction | What is conceptual design, why it matters | — |
| 3.2 Entity Identification | List all entities | Section 11 (ERD Data) |
| 3.3 Entity-Attribute Description | Table of each entity with attributes | Section 5 (Data Models) |
| 3.4 ER Diagram | Full ERD diagram image | Section 11 |
| 3.5 Relationship Description | Explain each relationship | Section 6.4 (Relationships) |
| 3.6 Data Dictionary | Complete data dictionary table | Section 6.5 |

### Key Figure:
- **Figure 3.1:** Entity Relationship Diagram

### Writing Style:
- Define each entity and WHY it exists
- Explain cardinality (1:1, 1:N) in plain English
- Use formal data dictionary format

---

## Chapter 4: PHYSICAL DATABASE DESIGN (4-5 pages)

### What to Include:
| Section | Content | Source from Audit |
|---------|---------|-------------------|
| 4.1 Introduction | Converting conceptual to physical | — |
| 4.2 Database Technology | Why Hive/Firestore/SQLite was chosen | Section 6 (Database Design) |
| 4.3 Collection/Table Structures | Physical table/collection layouts | Section 6 |
| 4.4 Data Types & Constraints | Field types, PKs, FKs, NOT NULL, etc. | Section 5 (Models) |
| 4.5 Storage Strategy | Local vs cloud, data isolation | Section 6 |
| 4.6 Backup & Recovery | How data is backed up | Section 4 (Backup feature) |

### Tables Format:
```
Table 4.1: [Entity Name] Collection Structure
| Field Name | Data Type | Size | Constraint | Description |
|------------|-----------|------|------------|-------------|
```

### Writing Style:
- Show actual implementation details
- Include code model snippets if relevant
- Explain WHY certain types/constraints were chosen

---

## Chapter 5: FUNCTIONAL MODELLING (5-6 pages)

### What to Include:
| Section | Content | Source from Audit |
|---------|---------|-------------------|
| 5.1 Introduction | What is functional modelling | — |
| 5.2 Context Diagram (DFD Level-0) | System + external entities | Section 12 (DFD Data) |
| 5.3 DFD Level-1 | Detailed sub-processes | Section 12 |
| 5.4 Process Specifications | Description of each process | Section 12 |
| 5.5 Use Case Diagram | UML use case | Section 13 (Use Case Data) |
| 5.6 Use Case Descriptions | Table for each use case | Section 13 |

### Key Figures:
- **Figure 5.1:** Context Diagram (DFD Level-0)
- **Figure 5.2:** DFD Level-1
- **Figure 5.3:** Use Case Diagram

### Writing Style:
- Explain each diagram after showing it
- Describe data flows in text
- Use formal use case description tables:
  ```
  Use Case: [Name]
  Actor: [Primary actor]
  Precondition: [What must be true before]
  Main Flow: [Step by step]
  Postcondition: [What's true after]
  ```

---

## Chapter 6: USER INTERFACE & SYSTEM FEATURES (6-8 pages)

### What to Include:
| Section | Content | Source from Audit |
|---------|---------|-------------------|
| 6.1 Introduction | Overview of the app UI | Section 9 (UI/UX) |
| 6.2 - 6.N | One section per screen/feature | Section 10 (Screen docs) + Section 14 (Screenshots) |

### Format for Each Screen:
```
6.X [Screen Name]

Figure 6.X shows the [screen name] of the NoteNest application. 
This screen allows the user to [describe what user can do].

[INSERT SCREENSHOT — Figure 6.X: Screen Name]

Key features of this screen include:
- [Feature 1]
- [Feature 2]
- [Feature 3]
```

### Writing Style:
- This is the MOST visual chapter
- Every screen gets a screenshot + description
- Describe what user sees and can do
- Reference figures properly ("As shown in Figure 6.3...")

---

## Chapter 7: SYSTEM TESTING (3-4 pages)

### What to Include:
| Section | Content | Source from Audit |
|---------|---------|-------------------|
| 7.1 Introduction | Why testing matters | — |
| 7.2 Testing Strategy | Types of testing performed | — |
| 7.3 Test Environment | Device, OS, tools used | Section 2 (Tech Stack) |
| 7.4 Test Cases | Detailed test case table | Section 15 (Test Cases) |
| 7.5 Test Results | Summary of outcomes | Section 15 |

### Test Case Table Format:
```
Table 7.1: Test Cases
| # | Module | Test Case | Input | Expected Output | Actual Output | Status |
|---|--------|-----------|-------|-----------------|---------------|--------|
| 1 | Login  | Valid login | email + pass | Home screen | Home screen | Pass |
```

### Writing Style:
- Include 15-25 test cases covering all major features
- Include 3-5 screenshot evidence for key tests
- Mention testing types: Unit, Integration, System, UAT

---

## Chapter 8: CONCLUSION & FUTURE WORK (2-3 pages)

### What to Include:
| Section | Content | Source from Audit |
|---------|---------|-------------------|
| 8.1 Conclusion | Summary of what was achieved | Section 1 (Overview) |
| 8.2 Objectives Achieved | Map each objective to achievement | Section 1 (Objectives) |
| 8.3 Challenges Faced | Technical/practical difficulties | — |
| 8.4 Social Impact | How the app benefits society/students | — |
| 8.5 Future Work | 5-7 planned enhancements | Section 17 (Future Work) |

### Writing Style:
- Reflect on the journey
- Be honest about challenges
- Future work should be realistic and specific
- End on a positive, forward-looking note

---

## Back Matter

### References
```
REFERENCES

[1] Flutter Framework — https://flutter.dev
[2] Firebase — https://firebase.google.com
[3] Google Gemini API — https://ai.google.dev
[4] Hive Database — https://pub.dev/packages/hive
...
```
Use numbered citation style [1], [2], etc. throughout the thesis.

### Appendices (Optional)
- **Appendix A:** Key source code snippets
- **Appendix B:** Additional screenshots
- **Appendix C:** User manual

---

## Chapter-by-Chapter AI Prompts

Use these prompts to generate each chapter from your `PROJECT_AUDIT.md`:

### Prompt Template:
```
You are a thesis writer for University of Malakand, CS Department.

Read the attached PROJECT_AUDIT.md file for complete project details.

Write Chapter [X]: [CHAPTER TITLE] of the FYP thesis.

Formatting rules:
- Times New Roman, 12pt body, 14pt bold headings
- 1.5 line spacing, justified alignment
- Figures numbered as Figure X.Y (chapter.sequence)
- Tables numbered as Table X.Y
- Citations as [1], [2] numeric style
- Formal academic tone, third person
- [X] pages target length

Include these sections:
[List sections from the chapter structure above]

Use ONLY the data from PROJECT_AUDIT.md. Do not make up features or details.
Mark screenshot locations as [INSERT SCREENSHOT — Figure X.Y: Description].
```

---

> **This structure file is your thesis blueprint. The audit file is your data source. Together, they give any AI everything needed to write your complete thesis.**
