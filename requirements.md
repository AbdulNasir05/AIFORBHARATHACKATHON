# SurakshaAI – Requirements Specification

## 1. Problem Statement

India faces a growing crisis of scam calls and AI-generated voice deepfakes. 
Existing solutions detect caller identity but fail to analyze conversational intent in real time. 
Users, especially senior citizens, need proactive protection during the call.

SurakshaAI aims to provide real-time, multilingual scam detection and voice deepfake identification with explainable alerts.

---

## 2. Objectives

- Detect scam intent during live calls
- Identify potential voice cloning/deepfake anomalies
- Provide explainable, real-time risk alerts
- Support multilingual Indian users
- Enable Family Shield notifications for vulnerable users
- Ensure privacy-first architecture

---

## 3. Functional Requirements

### 3.1 Call Monitoring
- The system shall analyze live call audio with explicit user consent.
- The system shall support Android Accessibility API for call detection.

### 3.2 Speech-to-Text
- The system shall convert speech to text in real time.
- On-device STT shall be used by default.
- Optional cloud STT may be used if user opts in.

### 3.3 Scam Intent Detection
- The system shall classify conversational intent using ML models.
- It shall detect common scam categories:
  - KYC scam
  - Digital arrest scam
  - Bank fraud
  - OTP fraud

### 3.4 Script Similarity Matching
- The system shall compare transcripts against known fraud patterns.
- Scam pattern database shall be stored securely (e.g., DynamoDB).

### 3.5 Voice Deepfake Detection (Optional Cloud)
- The system shall detect synthetic voice anomalies.
- Deepfake detection shall be enabled only when user opts in.

### 3.6 Risk Scoring
- The system shall compute an ensemble confidence score.
- If score exceeds threshold, a high-risk alert shall be triggered.

### 3.7 Alerts
- The system shall display a real-time alert overlay.
- Alert shall include:
  - Risk percentage
  - Reason indicators (urgency, financial request, impersonation)

### 3.8 Family Shield
- The system shall notify trusted contacts when high risk is detected.
- Notifications shall be sent via SMS or push notification.

### 3.9 Feedback Loop
- Users shall be able to report:
  - False positives
  - Missed scams
- System shall log feedback for model improvement.

---

## 4. Non-Functional Requirements

### 4.1 Privacy
- Audio shall remain on device by default.
- No permanent audio recordings shall be stored.
- User shall have kill switch control.

### 4.2 Performance
- Alert latency target: < 3 seconds.
- Basic protection shall work offline.

### 4.3 Scalability
- Cloud services shall scale via AWS Lambda.
- System shall support future expansion to 12+ Indian languages.

### 4.4 Security
- All cloud communication shall use encrypted channels (HTTPS).
- Data shall be anonymized before storage.

---

## 5. Constraints

- iOS live call audio access limitations.
- Deepfake detection requires cloud compute.
- Model accuracy depends on training data quality.

---

## 6. Success Metrics

- Real-time detection accuracy > 80%
- False positive rate < 15%
- Average alert latency < 3 seconds
- User satisfaction > 85%
