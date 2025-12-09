---
title: "Week 10 Worklog"
weight: 2
chapter: false
pre: " <b> 1.10. </b> "
---

### Week 10 Objectives:

* Implement Mediapipe Pose Detection for exercise tracking
* Research and develop algorithms based on pose coordinates (skeleton tracking)
* Test and tune algorithms for accuracy
* Learn Amazon Bedrock and integrate AI for health Q&A
* Build the frontend with TypeScript + React
* Integrate real‑time pose tracking into the web app

### Tasks to be carried out this week:
| Day | Task | Start Date | Completion Date |
| --- | ---- | ---------- | --------------- |
| 2   | - Intro to Mediapipe Pose Detection <br>&emsp; + Install Mediapipe <br>&emsp; + Basic pose tracking script <br>&emsp; + Visualize skeleton on video <br> - Learn pose landmarks (x, y, z) | 10/11/2025 | 10/11/2025 |
| 3   | - Research pose‑based algorithms <br>&emsp; + Distances between joints <br>&emsp; + Joint angles <br>&emsp; + Recognize Push‑up, Squat, Plank <br> - **Practice:** <br>&emsp; + Push‑up detection | 11/11/2025 | 11/11/2025 |
| 4   | - Continue algorithm dev <br>&emsp; + Squat, Plank <br>&emsp; + Rep counting <br>&emsp; + Exercise duration <br> - Test and tune accuracy | 12/11/2025 | 12/11/2025 |
| 5   | - Learn Amazon Bedrock <br>&emsp; + Available foundation models <br>&emsp; + Call Bedrock API <br>&emsp; + Prompting for health Q&A <br> - **Practice:** <br>&emsp; + Health Q&A chatbot | 13/11/2025 | 13/11/2025 |
| 6   | - Learn TypeScript + React <br>&emsp; + Setup React TS project <br>&emsp; + Build pose tracking UI components <br>&emsp; + Integrate Mediapipe <br>&emsp; + Forms (register/login) <br>&emsp; + Integrate Bedrock API | 14/11/2025 | 14/11/2025 |


### Week 10 Achievements:

* Monday (10/11/2025):
  * Understood Mediapipe Pose Detection — ML‑based pose tracking
  * Installed Mediapipe: `pip install mediapipe opencv-python`
  * Built a basic pose tracking script (webcam/file)
  * Detected 33 pose landmarks (x, y, z)
  * Visualized skeleton overlays and confidence scores

* Tuesday (11/11/2025):
  * Developed pose‑based algorithms:
    * Distances between joints, joint angles
    * Push‑up recognition via elbow angle thresholds
    * Rep counting via down→up transitions

* Wednesday (12/11/2025):
  * Extended to Squat and Plank; rep counting per exercise
  * Measured exercise duration (frames/FPS; start/end time)
  * Tuned thresholds; smoothed pose data across frames

* Thursday (13/11/2025):
  * Learned Amazon Bedrock
  * Called Bedrock Runtime and built health Q&A prompts
  * Implemented a chatbot with context (calories, goals, exercises)

* Friday (14/11/2025):
  * Set up React + TypeScript
  * Built components: PoseDetectionComponent, WorkoutSummary, ChatBot, Form
  * Integrated Mediapipe in React (useRef/useEffect; realtime state)
  * Added a backend endpoint to call Bedrock; displayed recommendations
  * Built UI: navbar, profile, start workout, chatbot sidebar, dashboard
