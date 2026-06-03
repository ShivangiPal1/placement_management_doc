# Product Requirement Document (PRD)
## AI-Powered Placement Management Platform

**Version:** 1.0  
**Date:** June 2026  
**Author:** Devansh  
**Institution:** SRM Institute of Science and Technology  
**Course:** AI-Powered Systems Design  
**Status:** Draft

---

## 1. Purpose

The placement process in most engineering colleges is fragmented, slow, and heavily manual. Students miss job postings, recruiters struggle to filter hundreds of resumes, and the placement cell spends most of its time on coordination rather than strategy.

This platform aims to make the placement process simple, organized, and easier for students, recruiters, and the placement cell — by bringing everything into one AI-powered system that automates screening, tracks applications in real time, and gives every stakeholder a clear view of what's happening.

---

## 2. Users Involved

### 2.1 Students
Students are the primary users of the platform. They create profiles, upload resumes, and apply for jobs posted by recruiters.

**Key needs:**
- Know which jobs they are eligible for without manual checking
- Understand how strong their resume is for a given role
- Track where their application stands at any point in time

### 2.2 Recruiters / Companies
Recruiters register on the platform (after TPO approval) to post job openings and view applications submitted by students.

**Key needs:**
- Post jobs with specific eligibility criteria (branch, CGPA, batch)
- Receive a ranked, AI-screened list of candidates instead of raw resumes
- Manage interview slots and communicate decisions through the platform

### 2.3 Placement Cell / Admin (TPO)
The placement cell manages the overall placement process — approving companies, monitoring student activity, and generating reports for the institution.

**Key needs:**
- Full visibility into every active placement drive
- Ability to manage student eligibility rules centrally
- Data and reports to present to the institution and improve future placement seasons

---

## 3. Product Goals

| Goal | Metric |
|------|--------|
| Reduce manual resume screening effort | Screening time < 10 minutes per drive |
| Improve student–job match quality | AI match score aligns with recruiter selection ≥ 80% of the time |
| Increase student engagement | ≥ 90% of eligible students complete their profiles |
| Give TPO real-time visibility | Dashboard reflects live data with zero manual update needed |

---

## 4. Scope

### In Scope (v1.0)
- Login and profile management for all three user roles
- Resume upload and AI-based parsing and scoring
- Job posting with eligibility filters
- Student job applications with automatic eligibility check
- Candidate shortlisting by recruiters (AI-ranked)
- Application tracking for students and recruiters
- Admin dashboard for placement cell

### Out of Scope (v1.0)
- Video interview integration
- Mobile native app (web-responsive only)
- Multi-institution support
- Alumni tracking post-placement
- Salary negotiation module

---

## 5. Main Features

### 5.1 Login and Profile Management

**Description:**  
All three user types — Students, Recruiters, and Admins — log in through a single portal with role-based access. Each role sees only the screens and data relevant to them.

**Student profile includes:**
- Personal details (name, roll number, branch, batch)
- Academic details (CGPA, backlogs, 10th/12th marks)
- Skills, certifications, projects, and work experience
- Uploaded resume (PDF)
- Profile completion percentage

**Recruiter profile includes:**
- Company name, industry, HR contact details
- Verified status (approved by TPO)

**Admin profile includes:**
- Full platform access
- Ability to manage student and recruiter accounts

**Functional Requirements:**

| ID | Requirement | Priority |
|----|-------------|----------|
| FR-L01 | Students register using college email ID | High |
| FR-L02 | Recruiters register and wait for TPO approval before accessing the platform | High |
| FR-L03 | Role-based login redirects each user to their respective dashboard | High |
| FR-L04 | Students can edit their profile and skills at any time | High |
| FR-L05 | Profile completion percentage is shown to encourage complete profiles | Medium |
| FR-L06 | Password reset via registered email | Medium |

---

### 5.2 Resume Upload

**Description:**  
Students upload their resume as a PDF. The AI engine parses the resume automatically to extract structured data — skills, education, projects, certifications — and stores it in the database. This data is then used to calculate match scores for each job the student applies to.

**Functional Requirements:**

| ID | Requirement | Priority |
|----|-------------|----------|
| FR-R01 | Students can upload resume in PDF format (max 5MB) | High |
| FR-R02 | AI parses the resume and extracts: skills, education, experience, certifications, projects | High |
| FR-R03 | Extracted data is shown to the student for review and manual correction | High |
| FR-R04 | Students can re-upload an updated resume at any time | High |
| FR-R05 | Resume is stored securely and accessible only to the student and approved recruiters | High |
| FR-R06 | AI generates an overall resume quality score (0–100) with a breakdown by category | Medium |

---

### 5.3 Job Posting and Job Applications

**Description:**  
Recruiters post job openings with full details and eligibility criteria. Students can browse all active job postings, see which ones they are eligible for, and apply with one click. The system automatically checks eligibility before allowing an application.

**Job posting includes:**
- Role title, job description, required skills
- Location, CTC / stipend
- Eligibility criteria: minimum CGPA, allowed branches, batch year, backlog policy
- Application deadline
- Number of rounds (online test, technical interview, HR interview, etc.)

**Functional Requirements:**

| ID | Requirement | Priority |
|----|-------------|----------|
| FR-J01 | Recruiters can create, edit, and close job postings | High |
| FR-J02 | Job postings require TPO approval before becoming visible to students | High |
| FR-J03 | Students see a list of all active jobs with eligibility status clearly marked | High |
| FR-J04 | System automatically checks student profile against eligibility criteria before allowing application | High |
| FR-J05 | Students can apply to a job with a single click (no re-uploading resume) | High |
| FR-J06 | Students can view full job description before applying | High |
| FR-J07 | Students receive a notification when a new eligible job is posted | Medium |
| FR-J08 | Recruiters can set a maximum number of applicants per posting | Low |

---

### 5.4 Candidate Shortlisting

**Description:**  
When a student applies for a job, the AI engine computes a match score by comparing the student's parsed resume against the job description. Recruiters see candidates ranked by this AI score, making shortlisting faster and more objective.

**AI match score is calculated based on:**
- Skills match (does the student have the required skills?)
- Academic performance (CGPA relative to the job's minimum threshold)
- Project and experience relevance (semantic similarity to the JD)
- Certifications relevant to the role

**Functional Requirements:**

| ID | Requirement | Priority |
|----|-------------|----------|
| FR-C01 | AI computes a match score (0–100) for every student–job pair upon application | High |
| FR-C02 | Recruiter sees all applicants ranked by AI match score | High |
| FR-C03 | Recruiter can view a score breakdown (skills, academics, projects, certifications) for each candidate | High |
| FR-C04 | Recruiter can shortlist or reject candidates individually or in bulk | High |
| FR-C05 | Rejected candidates receive an automated notification | Medium |
| FR-C06 | Shortlisted candidates receive an automated notification with next steps | Medium |
| FR-C07 | Recruiter can add internal notes on a candidate (not visible to student) | Low |

---

### 5.5 Application Tracking

**Description:**  
Students can track the status of every application they have submitted. Recruiters can see the full pipeline of candidates for each job. The placement cell can monitor all active drives from a single dashboard.

**Application statuses:**
- Applied → Under Review → Shortlisted → Interview Scheduled → Selected / Rejected → Offer Sent

**Functional Requirements:**

| ID | Requirement | Priority |
|----|-------------|----------|
| FR-T01 | Students see a list of all applications with current status | High |
| FR-T02 | Status updates trigger automatic in-app and email notifications to the student | High |
| FR-T03 | Recruiters see a pipeline view of all candidates per job posting | High |
| FR-T04 | TPO can view status of all applications across all active drives | High |
| FR-T05 | Application history is preserved even after a drive closes | Medium |
| FR-T06 | Students can withdraw an application before the deadline | Medium |

---

## 6. Non-Functional Requirements

| Category | Requirement |
|----------|-------------|
| Performance | Page load < 2 seconds; AI resume scoring < 5 seconds per resume |
| Scalability | Support up to 10,000 concurrent users during peak placement season |
| Security | Role-based access control; data encrypted at rest and in transit (HTTPS/TLS) |
| Availability | 99.5% uptime during active placement season |
| Accessibility | Web-responsive; works on mobile browsers without a native app |
| Compatibility | Supports Chrome, Firefox, and Edge (latest 2 versions) |

---

## 7. Recommended Tech Stack

| Layer | Technology | Reason |
|-------|------------|--------|
| Frontend | React.js + Tailwind CSS | Component-based UI; fast development |
| Backend | FastAPI (Python) | Compatible with ML/AI libraries |
| Database | PostgreSQL via Supabase | Reliable; supports row-level security |
| AI / NLP | spaCy + sentence-transformers | Resume parsing and semantic job matching |
| Authentication | Supabase Auth (JWT) | Built-in role management |
| File Storage | Supabase Storage | Secure PDF storage for resumes |
| Hosting | Vercel (frontend) + Railway (backend) | Easy deployment; free tiers available |

---

## 8. Assumptions and Constraints

- Students must have a valid college email ID to register
- Recruiters must be approved by the TPO before they can post jobs or view resumes
- All users are expected to have internet access
- Initial deployment is for a single institution (SRM); multi-college support is planned for v2.0
- Resume uploads are PDF only in v1.0

---

## 9. Risks

| Risk | Likelihood | Impact | Mitigation |
|------|------------|--------|------------|
| AI scores are biased against certain student profiles | Medium | High | Regular audits; show score breakdown so recruiters can override |
| Students submit incomplete or poorly formatted resumes | High | Medium | AI-guided resume tips shown during upload |
| Low recruiter adoption of the platform | Medium | High | TPO assists companies during onboarding; simple UI for recruiters |
| Data privacy concerns from students | Low | High | GDPR-aligned data handling; students control who sees their resume |

---

## 10. Future Scope (v2.0)

- Interview scheduling with calendar integration
- Offer letter upload and digital acceptance
- Multi-institution (multi-tenant) support
- AI skill gap analysis with course recommendations
- Native mobile app (Android + iOS)
- Alumni placement tracking

