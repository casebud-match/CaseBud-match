# CaseBud Platform

## Overview
CaseBud is a comprehensive interview preparation platform designed to match interviewers with interviewees for practice case interviews. The platform includes availability management, timezone handling, role-specific access, and case competition partner matching functionality.

## Key Features

### User Authentication
- Secure registration and login
- Role selection (interviewer/interviewee)
- Session management with persistent logins

### Availability Management
- Set multiple time slots for interview availability
- Timezone-aware scheduling
- Visual calendar interface

### Match Making
- Automated matching based on availability
- Zoom integration for video interviews
- Google Calendar integration for scheduling

### Case Repository
- Extensive library of 132 case studies from 7 business schools:
  - Kellogg
  - McCombs
  - UMKC Bloch
  - MIT-Sloan
  - Wharton
  - ESADE-MBA
  - Fuqua
  - Darden

### Case Competition Features
- Partner matching based on skills and preferences
- Team formation capabilities (teams of 3-5 people)
- Support for PYPC Case Competition 2025

### Resources
- Interactive case frameworks
- Preparation guides and templates
- Industry-specific case approaches

## Technical Stack
- Frontend: React + TypeScript with shadcn/ui components
- Backend: Node.js + Express
- Database: PostgreSQL with Drizzle ORM
- Authentication: Passport.js with session-based auth
- Integrations: Zoom API, Google Calendar API, email system

## Deployment
This application is designed to be deployed on Replit and can be easily adapted for other hosting environments.

## Getting Started
1. Clone this repository
2. Install dependencies with `npm install`
3. Start the development server with `npm run dev`
4. Visit the application at the provided URL

## Environment Variables
The following environment variables are required:
- `SESSION_SECRET`: Secret for session management
- `ZOOM_CLIENT_ID`: Zoom API client ID
- `ZOOM_CLIENT_SECRET`: Zoom API client secret
- `GOOGLE_SERVICE_ACCOUNT_KEY`: Google service account key (for Calendar API)