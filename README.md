# 🛡️ SurakshaAI  
### Real-Time Conversational Fraud Intelligence for India

SurakshaAI is an AI-powered real-time scam call and voice deepfake detection system designed for India’s multilingual population.  

Unlike traditional spam blockers that only detect caller identity, SurakshaAI analyzes *what is being said* during a call and alerts users before financial harm occurs.

---

## 🚨 Problem

India faces a surge in:

- KYC fraud calls  
- Digital arrest scams  
- OTP fraud  
- AI-generated voice cloning scams  

Existing tools:
- Detect known spam numbers  
- Fail to analyze conversation context  
- Cannot detect voice deepfakes  

Users — especially senior citizens — need protection *during* the call.

---

## 🎯 Solution

SurakshaAI provides:

- 📞 Live call analysis (with user consent)
- 🗣️ Real-time speech-to-text
- 🧠 Scam intent detection using ML
- 🎭 Voice deepfake anomaly detection
- 📊 Ensemble risk scoring
- ⚠️ Explainable in-call alerts
- 👨‍👩‍👧 Family Shield notifications for vulnerable users

---

## 🏗️ System Architecture

**Flow:**  
Call Audio → On-Device STT → ML Analysis → Risk Score → Alert  
(Optional cloud enhancement for deepfake detection)

### Layers:

- **Client Layer** – Android App (Accessibility API)
- **Speech Layer** – On-device STT / Amazon Transcribe
- **Intelligence Layer** –  
  - Amazon Comprehend (Intent Classification)  
  - Amazon Bedrock (LLM Reasoning)  
  - Amazon SageMaker (Voice Deepfake Detection)  
- **Orchestration** – AWS Lambda
- **Data Layer** – DynamoDB + S3
- **Alert Layer** – Amazon SNS

---

## 🔒 Privacy-First Design

- On-device processing by default  
- Cloud enhancement only with explicit opt-in  
- No permanent audio storage  
- User-controlled kill switch  
- Encrypted communication for all cloud services  

---

## ⚡ MVP Scope (Hackathon Build)

- Android-based prototype  
- Hindi + English support  
- 3 scam categories (KYC, Bank Fraud, Digital Arrest)  
- Real-time intent detection  
- Risk threshold alert system  
- Basic offline protection  

---

## 📊 Success Metrics

- Near real-time alert latency (<3 seconds target)
- >80% intent classification accuracy (target)
- Explainable risk breakdown for user trust

---

## 🚀 Future Roadmap

- Support for 12+ Indian languages  
- Advanced voice deepfake fingerprinting  
- Telecom-level integration  
- Adaptive scam script clustering  
- Family dashboard & remote protection  

---

## 🛠️ Tech Stack

- Android (Kotlin)
- Python (ML pipeline)
- PyTorch / TensorFlow
- Amazon Transcribe
- Amazon Comprehend
- Amazon Bedrock
- Amazon SageMaker
- AWS Lambda
- Amazon SNS
- DynamoDB
- Amazon S3

---

## 🏆 Hackathon Submission

Track: AI for Communities, Access & Public Impact  
Event: AI for Bharat Hackathon  

---

## 👥 Team VigilAI

Building intelligent systems that protect users from real-world digital threats.

---

## 📜 License

This project is developed for hackathon evaluation purposes.
