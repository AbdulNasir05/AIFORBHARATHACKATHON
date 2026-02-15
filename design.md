# SurakshaAI – System Design Document

## 1. System Overview

SurakshaAI is a real-time conversational fraud detection system 
built on a privacy-first architecture with optional AWS cloud enhancement.

Architecture consists of:
- Client Layer (Android App)
- Speech Layer
- Intelligence Layer
- Orchestration Layer
- Alert Layer
- Data Layer

---

## 2. High-Level Architecture

Call Audio → On-Device STT → ML Analysis → Risk Score → Alert
                           ↓
                  Optional Cloud Enhancement

---

## 3. Component Design

### 3.1 Client Layer (Android App)

- Call detection via Accessibility API
- User consent management
- Alert overlay display
- Kill switch toggle

---

### 3.2 Speech Processing Layer

- On-device Speech-to-Text (default)
- Optional Amazon Transcribe for cloud STT

---

### 3.3 Intelligence Layer

#### Intent Classification
- Model: MuRIL / IndicBERT
- Hosted via Amazon Comprehend or custom model

#### Scam Script Matching
- Pattern database: Amazon DynamoDB
- Matching logic via AWS Lambda

#### LLM Reasoning
- Amazon Bedrock
- Generates explainable reasoning

#### Voice Deepfake Detection
- Custom CNN model
- Hosted on Amazon SageMaker
- Uses mel-spectrogram features

---

### 3.4 Orchestration Layer

- AWS Lambda aggregates:
  - Intent score
  - Script similarity score
  - Voice anomaly score
- Computes ensemble confidence score

---

### 3.5 Alert Layer

- Amazon SNS for:
  - In-app alert triggers
  - Family Shield notifications

---

### 3.6 Data Layer

- DynamoDB: Scam patterns
- S3: Model artifacts
- CloudWatch: Monitoring & logs

---

## 4. Data Flow

1. User receives call
2. Audio captured (with consent)
3. Speech converted to text
4. ML models analyze transcript
5. Risk score calculated
6. Alert triggered if threshold exceeded
7. Optional family notification sent

---

## 5. Privacy Architecture

- On-device processing first
- Cloud enhancement optional
- No permanent audio storage
- Explicit opt-in required

---

## 6. Deployment Architecture

- Serverless backend (Lambda)
- Managed AI services (Comprehend, Bedrock, SageMaker)
- Encrypted APIs via API Gateway

---

## 7. Future Enhancements

- Telecom-level integration
- Cross-device family monitoring dashboard
- Advanced deepfake fingerprinting
- Real-time clustering of emerging scam scripts
