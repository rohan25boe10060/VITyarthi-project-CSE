# VITyarthi-project-CSE
Cattle health, symptom checker
Cattle Health Symptom Checker
A simple Python command-line tool that helps rural households and small farmers identify possible cattle illnesses based on observed symptoms — and decide whether to call a veterinarian.
---
The Problem
In rural India, millions of households depend on cattle for their livelihood. When an animal falls ill, farmers often:
Cannot quickly identify the illness
Don't know whether it's an emergency or can wait
Lack easy access to veterinary advice
This tool bridges that gap with a simple symptom-based checker that runs entirely offline — no internet needed.
---
Features
Select from 25+ common cattle symptoms via a numbered menu
Matches symptoms against a knowledge base of 10 common cattle illnesses
Displays severity level (🔴 HIGH / 🟡 MEDIUM / 🟢 LOW) for each possible condition
Gives actionable veterinary advice and home care tips
Logs every consultation to a CSV file for future reference
View past consultation history from within the app
---
Requirements
Python 3.6 or higher
No external libraries needed — uses only Python standard library (`csv`, `os`, `datetime`)
---
How to Run
1. Clone the repository
```bash
git clone https://github.com/YOUR_USERNAME/cattle-health-checker.git
cd cattle-health-checker
```
2. Run the program
```bash
python cattle_health.py
```
That's it. No installation, no pip install, no setup.
---
Usage Walkthrough
When you run the program, you'll see:
```
==========================================================
       🐄  CATTLE HEALTH SYMPTOM CHECKER  🐄
==========================================================
 Helping rural households identify cattle illnesses
 and decide when to call a veterinarian.
==========================================================

What would you like to do?
  1. Check cattle symptoms
  2. View past consultations
  3. Exit
```
Step 1 — Enter animal details
```
Animal name / ID (e.g., Gauri, Cow-1): Gauri
Type (cow / buffalo / calf / bull): cow
Approximate age (e.g., 4 years): 5 years
```
Step 2 — Select symptoms from the numbered list
```
  1. blisters on feet        2. blisters on mouth
  3. cold ears               4. coughing
  5. dehydration             ...

Enter the numbers: 4, 9, 14
```
Step 3 — View results
```
RESULTS FOR: GAURI (cow, 5 years)
Symptoms reported: coughing, fever, nasal discharge

1. 🟡 Bovine Respiratory Disease (BRD)  [MEDIUM SEVERITY]
   Matched symptoms (3): coughing, fever, nasal discharge
   ➤ Advice    : Consult a vet for antibiotic treatment.
   ➤ Home care : Keep in dry, ventilated area. Ensure fresh water.
```
All consultations are automatically saved to `consultation_log.csv`.
---
Project Structure
```
cattle-health-checker/
│
├── cattle_health.py        # Main program
├── consultation_log.csv    # Auto-generated log of past checks
└── README.md               # This file
```
---
How It Works
The program uses a rule-based knowledge base — a Python list of dictionaries, each representing a cattle illness with:
A list of associated symptoms
A minimum symptom match threshold
Severity level
Veterinary advice and home care tips
When the user selects symptoms, the program:
Compares selected symptoms against every illness in the knowledge base
Counts how many symptoms match
Returns all illnesses that meet the minimum match threshold
Sorts results by severity (HIGH first), then by match score
---
Illnesses Covered
Illness	Severity
Foot and Mouth Disease (FMD)	🔴 HIGH
Bloat (Rumen Tympany)	🔴 HIGH
Tick Fever (Theileriosis)	🔴 HIGH
Milk Fever (Hypocalcaemia)	🔴 HIGH
Bovine Respiratory Disease	🟡 MEDIUM
Mastitis	🟡 MEDIUM
Diarrhoea / Calf Scours	🟡 MEDIUM
External Parasites	🟢 LOW
Conjunctivitis (Pinkeye)	🟢 LOW
General Weakness	🟢 LOW
---
Emergency Contact
If a HIGH severity condition is detected, the tool displays:
> 📞 National Livestock Helpline (India): **1962**
---
Limitations
This tool is for initial guidance only — it is not a substitute for professional veterinary diagnosis
The knowledge base covers common illnesses; rare conditions may not be detected
Symptom matching is based on presence/absence, not clinical examination
---
License
This project is submitted as part of a Python/Data Science course (BYOP assignment). Free to use and modify for educational purposes.
