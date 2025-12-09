---
title: "Week 9 Worklog"
weight: 1
chapter: false
pre: " <b> 1.9. </b> "
---

### Week 9 Objectives:

* Kick off the team project: AI‑powered fitness tracking app
* Finalize idea and project direction
* Learn health metrics (BMR, TDEE, MET, PF)
* Understand calorie formulas and goal‑based adjustments
* Research applicable AI models (Amazon Bedrock) for personalized recommendations
* Draft the project architecture using AWS services

### Tasks to be carried out this week:
| Day | Task | Start Date | Completion Date |
| --- | ---- | ---------- | --------------- |
| 2   | - Project kickoff <br>&emsp; + Discuss idea: Fitness + AI app <br>&emsp; + Define objectives <br>&emsp; + Split workstreams <br> - Learn BMR and formulas | 03/11/2025 | 03/11/2025 |
| 3   | - Learn TDEE (Total Daily Energy Expenditure) <br>&emsp; + Activity multipliers by activity level <br>&emsp; + Set user goals (cut, bulk, maintain) <br> - **Practice:** <br>&emsp; + Calculate TDEE for profiles | 04/11/2025 | 04/11/2025 |
| 4   | - Learn MET (Metabolic Equivalent of Task) <br>&emsp; + Calories from workouts <br>&emsp; + Common exercises and MET values <br> - Learn goal‑based adjustments | 05/11/2025 | 05/11/2025 |
| 5   | - Learn PF (Physical Fitness) <br>&emsp; + PF formula from height, weight, level, age, gender <br>&emsp; + Adjust workouts based on PF <br> - Learn progression rate | 06/11/2025 | 06/11/2025 |
| 6   | - **Integrated practice:** <br>&emsp; + Full calculation for one profile (BMR, TDEE, MET, PF) <br>&emsp; + Build spreadsheet/docs for health metrics <br>&emsp; + Draft AWS architecture <br>&emsp; + Explore Amazon Bedrock for AI recommendations | 07/11/2025 | 07/11/2025 |


### Week 9 Achievements:

* Monday (03/11/2025):
  * Finalized the project idea: AI‑powered fitness app
  * Key features:
    * Track daily calorie expenditure
    * Recommend workouts based on goals (cut/bulk/maintain)
    * Generate optimal meal plans with Amazon Bedrock AI
    * Track fitness progress via metrics
  * Split workstreams: Backend, Frontend, AI/ML, DevOps
  * Learned BMR (Basal Metabolic Rate):
    * BMR = energy expenditure at rest
    * Male: BMR = 10×weight(kg) + 6.25×height(cm) − 5×age + 5
    * Female: BMR = 10×weight(kg) + 6.25×height(cm) − 5×age − 161

* Tuesday (04/11/2025):
  * Understood TDEE (Total Daily Energy Expenditure): TDEE = BMR × Activity Multiplier
  * Activity multipliers by activity level:
    * Sedentary: 1.2
    * Light (1–3 workouts/week): 1.375
    * Moderate (3–5 workouts/week): 1.55
    * Heavy (6–7 workouts/week): 1.725
    * Athlete: 1.9
  * Goal‑based calorie adjustments:
    * Cut: TDEE − 500 kcal/day
    * Bulk: TDEE + 300–500 kcal/day
    * Maintain: TDEE
  * Practiced TDEE calculations for multiple profiles

* Wednesday (05/11/2025):
  * Understood MET (Metabolic Equivalent of Task) and formula: Calories = MET × Weight(kg) × Time(min)
  * Common exercises and MET values:
    * Push‑up: 8.0
    * Squat: 5.0
    * Jumping Jack: 9.0
    * Plank: 3.3
  * Remaining calories = Adjusted TDEE − Exercise calories
  * Goal‑based workout adjustments:
    * Cut: +10% cardio reps
    * Bulk: +10% strength reps
    * Maintain: keep baseline plan

* Thursday (06/11/2025):
  * Understood PF (Physical Fitness): PF = (height − 100) / weight × L × A × G; range ≈ 0.4–1.5
  * Parameters:
    * L (Level): Beginner=0.6, Intermediate=1.0, Advanced=1.3
    * A (Age): ≤30=1.0, 31–45=0.9, 46–60=0.8, >60=0.7
    * G (Gender): Male=1.0, Female=0.85
  * PF‑based reps:
    * Push‑up: 25 × PF
    * Squat: 35 × (PF + 0.1)
    * Jumping Jack: 100 × (PF + 0.2)
    * Plank: 40 × (PF + 0.1)
  * Progression: Sd = S1 × (1 + k)^(d−1); k depends on level and plan duration (7/14/21/30/60/90 days)

* Friday (07/11/2025):
  * Full profile computation:
    * Step 1: BMR from weight, height, age, gender
    * Step 2: TDEE from BMR × Activity Multiplier
    * Step 3: Adjust calories by goal
    * Step 4: PF from height, weight, level, age, gender
    * Step 5: Build workout plan with PF‑adjusted reps
    * Step 6: Apply progression over time
  * Built spreadsheet/docs for metrics
  * Drafted AWS architecture:
    * Frontend: React/Vue (web app)
    * Backend: Node.js/Python + Amazon RDS (user data)
    * AI/ML: Amazon Bedrock for meal recommendations
    * Storage: S3 for workout plans
    * Monitoring: CloudWatch for tracking
  * Explored Amazon Bedrock:
    * Use pre‑trained models
    * Generate personalized meal plans from remaining calories
    * Fine‑tune recommendations to health goals
