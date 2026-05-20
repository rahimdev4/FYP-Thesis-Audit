# 🔍 FYP Project Audit — AI Prompt

> **INSTRUCTIONS FOR AI:** Read this entire file carefully, then audit the project and generate the output file.

---

## YOUR TASK

You are a **Final Year Project (FYP) Thesis Auditor**. Your job is to deeply analyze a software project and produce a comprehensive audit document that captures EVERY detail needed to write a university thesis.

**Output file:** Create `PROJECT_AUDIT.md` in the project root using the template from `uom-thesis-audit/audit_template.md`.

---

## AUDIT PROCESS — Follow These Steps in Order

### Phase 1: Project Discovery
1. List the **entire directory structure** (all folders and files)
2. Identify the **framework/language** (Flutter, React, Node.js, Python, etc.)
3. Read the **main entry point** file (e.g., `main.dart`, `index.js`, `app.py`)
4. Read **package/dependency files** (e.g., `pubspec.yaml`, `package.json`, `requirements.txt`)
5. Read **configuration files** (e.g., `firebase.json`, `.env.example`, `config/`)
6. Read the **README** if one exists

### Phase 2: Architecture Analysis
1. Identify the **architecture pattern** (MVVM, MVC, Clean Architecture, etc.)
2. Map out the **folder structure** and what each folder/module does
3. Identify **state management** approach (Riverpod, Provider, Redux, Context, etc.)
4. Identify **navigation/routing** system
5. Count total source files and lines of code (approximate)

### Phase 3: Feature Audit
1. Go through **every screen/page** in the app
2. Document **what each screen does** — every button, input, action
3. Identify **user flows** (e.g., sign up flow, create item flow, etc.)
4. List ALL **CRUD operations** (Create, Read, Update, Delete) in the app
5. Document **special features** (AI, camera, file handling, etc.)

### Phase 4: Data & Database Analysis
1. Read ALL **model/entity files** — document every field, type, relationship
2. Identify **local database** (Hive, SQLite, SharedPreferences, etc.)
3. Identify **cloud database** (Firestore, Supabase, MongoDB, etc.)
4. Document **database schema** — tables/collections, fields, data types
5. Map **entity relationships** (1:1, 1:N, N:N) for ERD
6. Document **data flow** — how data moves through the system

### Phase 5: Backend & API Analysis
1. List ALL **external APIs** used (Firebase Auth, Google APIs, REST endpoints, etc.)
2. Document **authentication system** — methods, flows, tokens
3. Document **cloud storage** usage (Google Drive, S3, Firebase Storage, etc.)
4. List ALL **API endpoints** or **service functions** with their purpose
5. Document **error handling** approach

### Phase 6: UI/UX Analysis
1. Document the **design system** — colors, fonts, spacing, themes
2. List **light/dark mode** support details
3. Document **animations and transitions**
4. Identify **third-party UI packages** used
5. Map out **navigation flow** (which screen leads where)

### Phase 7: Testing & Deployment
1. Check for **unit tests, widget tests, integration tests**
2. Document **build configurations** (Android, iOS, web)
3. Note **deployment targets** (Play Store, App Store, web hosting)

### Phase 8: Thesis-Specific Mapping
1. Create **ERD entity list** with all attributes and relationships
2. Create **DFD process list** — all major processes and data stores
3. Create **Use Case list** — all actors and their use cases
4. Map **screenshots needed** — which screens need screenshots and for which chapter
5. Create a **test case table** — feature, input, expected output, result

---

## RULES

1. **Be exhaustive** — document EVERYTHING, not just the main features
2. **Read actual code** — don't guess from file names alone
3. **Include code snippets** — for models, key functions, and configurations
4. **Use tables** — for structured data (models, packages, test cases)
5. **Be specific** — write exact field names, types, package versions
6. **Count things** — total files, total screens, total packages, total models
7. **Follow the template** — use `audit_template.md` structure exactly
8. **Don't skip sections** — if something doesn't apply, write "N/A — [reason]"

---

## OUTPUT QUALITY CHECKLIST

Before finalizing, verify your audit covers:
- [ ] Project overview (name, type, framework, purpose)
- [ ] Complete folder structure with explanations
- [ ] Every feature/screen documented
- [ ] All data models with fields and types
- [ ] All packages/dependencies listed with purpose
- [ ] Database design (local + cloud)
- [ ] Authentication system details
- [ ] API integrations documented
- [ ] UI/UX design system details
- [ ] ERD entities and relationships ready
- [ ] DFD processes and data stores ready
- [ ] Use cases with actors ready
- [ ] Screenshot placement guide
- [ ] Test cases table
- [ ] Technology stack summary table
