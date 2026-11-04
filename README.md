# ai-interview-prep
InterviewAI is an AI-powered interview preparation platform featuring HR and technical mock interviews, coding practice, resume analysis, personalized feedback, and performance analytics. Built with React, Tailwind CSS, Node.js, and Express.
# InterviewAI - AI Interview Preparation Platform

**Practice interviews, review your resume, solve coding problems, and track your preparation in one application.**

InterviewAI is a full-stack interview preparation project built with React, Tailwind CSS, Node.js, and Express. It combines HR and technical question banks, text and voice practice, AI-assisted answer evaluation, PDF resume analysis, coding practice, progress dashboards, and administrator tools.

The application supports a persistent local JSON database for development and a MongoDB/Mongoose data path. It also includes demo responses when configured AI providers are unavailable.

**Project type:** Advanced MCA Final Year Project | **Domain:** AI / EdTech / Interview Preparation | **Year:** 2026

## Contents

- [Overview](#overview)
- [Features](#features)
- [Technology Stack](#technology-stack)
- [System Architecture](#system-architecture)
- [Application Workflows](#application-workflows)
- [AI Integration](#ai-integration)
- [Data Architecture](#data-architecture)
- [Resume Analysis Pipeline](#resume-analysis-pipeline)
- [Coding and Voice Practice](#coding-and-voice-practice)
- [Project Structure](#project-structure)
- [Installation and Setup](#installation-and-setup)
- [Running the Application](#running-the-application)
- [Environment Variables](#environment-variables)
- [API Reference](#api-reference)
- [Frontend Routes](#frontend-routes)
- [Password Recovery and OTP](#password-recovery-and-otp)
- [Administrator Access](#administrator-access)
- [Build and Deployment](#build-and-deployment)
- [Verification](#verification)
- [Troubleshooting](#troubleshooting)
- [Security and Data Handling](#security-and-data-handling)
- [Current Limitations](#current-limitations)
- [Future Enhancements](#future-enhancements)
- [Contributing](#contributing)
- [License](#license)

## Overview

Interview preparation often involves separate tools for questions, coding, resume feedback, and progress tracking. InterviewAI brings those activities into a shared account and dashboard.

| Area | Implementation |
|---|---|
| Frontend | React single-page application |
| Backend | Express REST API |
| Authentication | JWT bearer tokens and bcrypt password hashes |
| Development storage | Persistent JSON file under `server/data/` |
| Database integration | MongoDB through Mongoose |
| AI integration | OpenAI, Google Gemini fallback, and structured demo responses |
| Interview input | Typed answers or browser speech-recognition transcripts |
| Resume input | Text-based PDF, maximum 5 MB |
| Coding languages | JavaScript and Python editor modes |
| Default addresses | Frontend `http://localhost:3000`; backend `http://localhost:5000` |

### Current Account Flow

**Signup does not require OTP.** A user registers with a name, email, password, and optional phone number. The account is created immediately, and the user signs in separately.

OTP remains part of **forgot-password recovery** by registered email or phone number. Real delivery requires provider credentials; local development can display a development code.

## Features

### Mock Interviews

- HR, technical, and mixed interview configurations.
- Built-in question banks for Java, Python, web development, data science, cybersecurity, HR, DSA, and general preparation.
- Expanded behavioral/HR questions covering teamwork, feedback, leadership, motivation, conflict, and career goals.
- Configurable difficulty, question count, and text/voice mode.
- Per-question answer submission and elapsed-answer timing.
- Completed interview history and detailed result pages.

Questions are currently selected from server-side banks. Selecting a difficulty sets session metadata and evaluation context; it does not dynamically generate or independently calibrate the question bank.

### Answer Evaluation and Feedback

- Per-question scores and an overall score out of 100.
- Breakdowns for confidence, technical correctness, communication clarity, grammar, relevance, and problem solving.
- Feedback, sample answers, strengths, weaknesses, and suggested improvements.
- Overall readiness labels, recommended topics, and next steps.

The confidence and communication scores are derived from submitted text or speech transcripts. They are not measurements of facial expression, vocal tone, or other biometric signals.

### Resume Analyzer

- Upload a text-based PDF resume.
- Extract readable text and identify contact information and technical keywords.
- Review skills, strengths, weaknesses, missing keywords, target roles, and suggestions.
- Display an overall resume score and an ATS-style compatibility estimate.
- Keep the latest analysis available from the account.
- Fall back to local text analysis when the provider response is unavailable or unsuitable.

### Coding Practice

- Monaco editor with JavaScript and Python modes.
- Problem descriptions, examples, constraints, and starter code.
