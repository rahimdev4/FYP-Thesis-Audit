# 🔍 FYP Project Audit — AI Prompt

> **INSTRUCTIONS FOR AI:** Read this file carefully. You will audit this project in **5 separate steps**. Each step generates ONE file. Do NOT try to do everything at once — this avoids token limits.

---

## ⚠️ CRITICAL: STEP-BY-STEP EXECUTION

**DO NOT** generate the entire audit in one response. You **MUST** work in steps.

### How This Works:
1. The user will ask you to run **one step at a time**
2. Each step creates **one output file** (small, focused)
3. After all 5 steps, the user has a complete audit split across 5 files
4. These 5 files together = full project documentation for thesis writing

---

## STEP 1: Project Overview & Tech Stack
**Output file:** `AUDIT_01_overview.md`
**Token cost:** Low (~200 lines)

Do the following:
1. Read the main entry point file (e.g., `main.dart`, `index.js`, `app.py`)
2. Read the dependency file (e.g., `pubspec.yaml`, `package.json`, `requirements.txt`)
3. Read the project README if it exists
4. List the **full directory tree** (folders only, 2 levels deep)

Then write `AUDIT_01_overview.md` with these sections:

```markdown
# PROJECT AUDIT — Part 1: Overview & Tech Stack

## 1.1 Project Overview
| Field | Details |
|-------|---------|
| Project Name | [name] |
| Type | [Mobile/Web/API] |
| Framework | [Flutter/React/etc] |
| Language | [Dart/JS/Python] |
| Architecture | [MVVM/MVC/etc] |
| State Management | [Riverpod/Redux/etc] |
| Total Source Files | [count] |

## 1.2 Project Description
[2-3 paragraphs — what it does, who it's for, what problem it solves]

## 1.3 Objectives
1. [objective 1]
2. [objective 2]
...

## 1.4 Folder Structure
[directory tree]

## 1.5 Folder Descriptions
| Folder | Purpose |
|--------|---------|
...

## 1.6 Technology Stack — All Packages
| # | Package | Version | Category | Purpose |
|---|---------|---------|----------|---------|
| 1 | [name] | [ver] | [Backend/UI/DB/etc] | [what it does] |
...

## 1.7 Development Tools
| Tool | Purpose |
|------|---------|
...
```

**STOP after writing this file. Wait for user to ask for Step 2.**

---

## STEP 2: Features & Screens
**Output file:** `AUDIT_02_features.md`
**Token cost:** Medium (~300 lines)

Do the following:
1. Go through **every screen/page file** in the project
2. Read each screen's code to understand what it displays and what user can do
3. Read ViewModels/Controllers to understand business logic

Then write `AUDIT_02_features.md` with:

```markdown
# PROJECT AUDIT — Part 2: Features & Screens

## 2.1 Feature Summary
| # | Feature | Screens | Description |
|---|---------|---------|-------------|
| 1 | [Auth] | [Login, SignUp] | [User authentication] |
...

## 2.2 Screen-by-Screen Documentation

### Screen: [Screen Name]
- **File:** `path/to/screen.dart`
- **Route:** `/screen-route`
- **Purpose:** [what this screen does]
- **UI Elements:** [buttons, inputs, cards, lists]
- **User Actions:** [what user can do]
- **Data Used:** [what data is displayed/modified]
- **Navigates To:** [which screens]
- **Screenshot Figure:** Figure 6.X

[Repeat for EVERY screen]

## 2.3 User Flows
### Flow 1: [e.g., Sign Up Flow]
1. User opens app → Splash Screen
2. Taps "Sign Up" → Sign Up Screen
3. Enters details → Profile Setup
4. Completes → Home Screen

[Document 3-5 major flows]

## 2.4 Current vs Proposed System
| Aspect | Without This App | With This App |
|--------|-----------------|---------------|
...
```

**STOP after writing this file. Wait for user to ask for Step 3.**

---

## STEP 3: Data Models & Database Design
**Output file:** `AUDIT_03_database.md`
**Token cost:** Medium (~250 lines)

Do the following:
1. Read ALL model/entity files
2. Read the database service/repository files
3. Read any migration or schema files
4. Identify relationships between entities

Then write `AUDIT_03_database.md` with:

```markdown
# PROJECT AUDIT — Part 3: Database & Data Models

## 3.1 Database Technologies
| Database | Technology | Storage Type | Purpose |
|----------|-----------|-------------|---------|
| Local | [Hive/SQLite] | [NoSQL/SQL] | [what it stores] |
| Cloud | [Firestore/Supabase] | [Document/Relational] | [what it stores] |
| Cloud Storage | [Drive/S3] | [File] | [what it stores] |

## 3.2 Data Models (Complete)

### Model: [Name]
**Storage:** [Hive/Firestore/etc] | **Type ID:** [if applicable]

| Field | Type | Key | Nullable | Description |
|-------|------|-----|----------|-------------|
| id | String | PK | No | Unique identifier |
...

**Model Code:**
```[language]
// paste actual model class (shortened if very long)
```

[Repeat for ALL models]

## 3.3 Entity Relationships (ERD Data)
| Entity A | Relationship | Entity B | Description |
|----------|-------------|----------|-------------|
| User | 1 : N | Subject | A user creates many subjects |
...

## 3.4 Data Dictionary
| Entity | Attribute | Data Type | Constraint | Description |
|--------|-----------|-----------|------------|-------------|
...

## 3.5 Database Operations (CRUD)
| Entity | Create | Read | Update | Delete | Service File |
|--------|--------|------|--------|--------|-------------|
| [Subject] | ✅ | ✅ | ✅ | ✅ | `hive_repo.dart` |
...
```

**STOP after writing this file. Wait for user to ask for Step 4.**

---

## STEP 4: Auth, APIs & Backend
**Output file:** `AUDIT_04_backend.md`
**Token cost:** Low-Medium (~200 lines)

Do the following:
1. Read authentication service files
2. Read API integration files
3. Read any backend/cloud function files
4. Read error handling patterns

Then write `AUDIT_04_backend.md` with:

```markdown
# PROJECT AUDIT — Part 4: Authentication, APIs & Backend

## 4.1 Authentication System
### Auth Methods
- [ ] Email/Password
- [ ] Google Sign-In
- [ ] Apple Sign-In
- [ ] Phone Number
- [ ] Other: [specify]

### Auth Provider: [Firebase Auth / Supabase / Custom]

### Sign Up Flow
1. [step 1]
2. [step 2]
...

### Login Flow
1. [step 1]
...

### Password Reset Flow
1. [step 1]
...

## 4.2 API Integrations

### API: [Name — e.g., Google Gemini]
- **Purpose:** [what it does]
- **SDK/Package:** [package name]
- **Auth Method:** [API key / OAuth]
- **Key Functions:**
  | Function | Input | Output | Description |
  |----------|-------|--------|-------------|
  ...

[Repeat for each API]

## 4.3 Key Service Files
| File | Purpose | Key Methods |
|------|---------|-------------|
...

## 4.4 Error Handling
[How errors are handled — try/catch, Result types, etc.]

## 4.5 Security Measures
[Auth guards, data isolation, input validation, etc.]
```

**STOP after writing this file. Wait for user to ask for Step 5.**

---

## STEP 5: UI Design, Diagrams & Testing
**Output file:** `AUDIT_05_ui_diagrams_testing.md`
**Token cost:** Medium (~300 lines)

Do the following:
1. Read theme/styling files
2. Compile DFD and Use Case data from previous steps
3. Create test cases for major features

Then write `AUDIT_05_ui_diagrams_testing.md` with:

```markdown
# PROJECT AUDIT — Part 5: UI Design, Diagrams & Testing

## 5.1 Design System
### Color Palette
| Token | Light Mode | Dark Mode | Usage |
|-------|-----------|-----------|-------|
...

### Typography
- Font: [family name]
- Body: [size]
- Headings: [size, weight]

### Theme Support
- [ ] Light Mode
- [ ] Dark Mode
- Design System: [Material 3 / Cupertino / Custom]

### Animations
| Animation | Screen | Package |
|-----------|--------|---------|
...

## 5.2 Navigation Map
```
App
├── Tab 1: [name] → [sub-screens]
├── Tab 2: [name] → [sub-screens]
...
```

## 5.3 Screenshot Placement Guide
### Chapter 6 Screenshots
| Figure # | Screen | What to Capture |
|----------|--------|-----------------|
| 6.1 | [name] | [description] |
...

### Chapter 7 Screenshots (Test Evidence)
| Figure # | Test | What to Capture |
|----------|------|-----------------|
| 7.1 | [test name] | [description] |
...

## 5.4 DFD Level-0 Data (Context Diagram)
**Central Process:** [Project Name] System
| External Entity | Data In → System | Data Out ← System |
|----------------|-----------------|-------------------|
...

## 5.5 DFD Level-1 Data
| Process # | Name | Description | Data Stores Used |
|-----------|------|-------------|-----------------|
...

| Data Store | Technology | Contents |
|-----------|-----------|----------|
...

## 5.6 Use Case Data
### Actors
| Actor | Type | Description |
|-------|------|-------------|
...

### Use Cases
| Module | Use Case | Actor(s) |
|--------|----------|----------|
...

## 5.7 Test Cases
| # | Module | Test Case | Input | Expected Output | Status |
|---|--------|-----------|-------|-----------------|--------|
| 1 | Login | Valid credentials | email + pass | Home screen | Pass |
...
[Include 15-25 test cases]

## 5.8 Future Work
1. [Enhancement 1]
2. [Enhancement 2]
...

## 5.9 References
| # | Reference |
|---|-----------|
| [1] | [Package/tool — URL] |
...
```

**AUDIT COMPLETE. All 5 files together form the full project documentation.**

---

## RULES FOR EVERY STEP

1. **Read actual code** — don't guess from file names
2. **Be specific** — exact field names, types, package versions
3. **Use tables** — for all structured data
4. **Don't skip sections** — write "N/A" if not applicable
5. **Keep each file focused** — only write what that step requires
6. **STOP after each step** — don't continue to the next step automatically
