AI Job Screener

AI-Powered Recruitment Platform | DevOps & Cloud-Native Application

An AI-powered recruitment platform designed to streamline candidate screening, automate CV analysis, and rank applicants based on job requirements.

The project combines a full-stack web application with containerization, CI/CD automation, and Kubernetes deployment capabilities.

Team Project: Developed collaboratively as part of a DevOps & DevSecOps final project.

Key Features

* AI-Powered CV Analysis: Evaluate candidate resumes against job requirements.
* Candidate Ranking: Rank applicants based on AI-generated scores.
* Job Management: Create, view, and delete job postings.
* Analytics Dashboard: Access candidate and recruitment analytics.
* Automated Testing: Execute backend tests using pytest.
* Containerized Deployment: Run the application using Docker Compose.
* CI/CD Automation: Jenkins pipeline supporting automated Kubernetes deployment.
* Monitoring Integration: Application health and metrics endpoints.

Technology Stack

Category	Technologies
Backend	Python, REST API
Frontend	Web Application
Containerization	Docker, Docker Compose
Orchestration	Kubernetes
CI/CD	Jenkins
Testing	pytest
Database	SQLite / PostgreSQL
Monitoring	Health Checks, Metrics Endpoint
AI Integration	Configurable AI API

Architecture

The application consists of:

Frontend: User interface for managing jobs, uploading CVs, and viewing candidate rankings.

Backend: REST API responsible for job management, candidate processing, AI scoring, and analytics.

Database: Persistent storage for jobs, candidates, and scoring results.

AI Integration: Configurable AI scoring service with mock mode for testing.

CI/CD: Jenkins pipeline supporting automated deployment to Kubernetes.

Getting Started

Prerequisites

* Docker
* Docker Compose

Run Locally

From the repository root:

docker compose up --build

Application endpoints:

* Frontend: http://localhost:3000
* Backend: http://localhost:5000
* Health Check: http://localhost:5000/health
* Metrics: http://localhost:5000/metrics

Testing

cd backend
MOCK_AI=1 pytest -q

Mock mode enables deterministic testing without external AI API calls.

Environment Variables

Variable	Default	Description
DATABASE_URL	sqlite:///screener.db	Database connection
MUSE_SPARK_API_KEY	Empty	AI API authentication
MUSE_SPARK_BASE_URL	https://opencode.ai/zen/go/v1	AI service endpoint
AI_MODEL	muse-spark-1.3-contributor	AI model
AI_API	responses	AI API interface
MIN_SCORE	0	Minimum scoring threshold
MAX_CV_SIZE	5242880	Maximum CV upload size
SCORING_WEIGHTS	skills:0.5,experience:0.3,education:0.2	Scoring weights
MOCK_AI	1 in Compose	Enable mock scoring

REST API

Job Management

* POST /api/jobs
* GET /api/jobs
* GET /api/jobs/<id>
* DELETE /api/jobs/<id>

Candidate Management

* POST /api/jobs/<id>/candidates
* GET /api/jobs/<id>/candidates?sort=rank
* GET /api/candidates/<id>
* POST /api/candidates/<id>/rescore

Analytics

* GET /api/jobs/<id>/analytics
* GET /api/analytics/overview

Monitoring

* GET /health
* GET /metrics

Related Repository

Infrastructure and deployment configuration:

CV Analyzer Infrastructure

Project Credits

Developed as a collaborative DevOps & DevSecOps final project.

The repository is maintained as a personal portfolio copy while preserving the original contribution history.
