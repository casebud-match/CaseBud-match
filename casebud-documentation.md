# CaseBud Platform Documentation

## Project Overview
CaseBud is a comprehensive platform for technical interview preparation, focusing on case study management and interview skill development. The application facilitates matching between interviewers and interviewees, manages availability scheduling, and provides access to a large repository of case studies.

## Key Features
- User authentication with role-based access control
- Interview scheduling with timezone handling
- Partner matching for both practice interviews and case competitions
- Extensive case repository (132 case studies from 7 different business schools)
- Google Calendar integration for scheduling
- Zoom integration for meeting creation
- Email notifications with calendar links and case access

## Technical Stack
- **Frontend**: React with TypeScript, Shadcn UI components, Tailwind CSS
- **Backend**: Node.js with Express
- **Database**: PostgreSQL with Drizzle ORM
- **Authentication**: Passport.js with local strategy
- **External Services**: 
  - Google Calendar API
  - Zoom API
  - Nodemailer for email delivery

## Main Components
1. **Authentication System**
   - Email/password registration and login
   - Session management
   - User profile customization

2. **Matching System**
   - Availability management
   - Automated matching algorithm
   - Role swapping support

3. **Case Competition Features**
   - Team formation functionality
   - Partner search with skill matching
   - Competition registration

4. **Case Repository**
   - Organized by business school source: Kellogg, McCombs, UMKC Bloch, MIT-Sloan, Wharton, ESADE-MBA, Fuqua, Darden
   - Categories for different case types
   - Random case assignment for interviews

5. **Resources**
   - Interactive case frameworks
   - Preparation guides
   - Best practices for interviews

## Key Files
- `server/routes.ts`: Main API endpoints, matching logic, role swapping
- `server/auth.ts`: Authentication setup and user management
- `server/seed-cases.ts`: Case repository data (132 cases)
- `server/emails.ts`: Email notification templates
- `client/src/pages/`: React component pages for different sections
- `client/src/components/`: Reusable UI components
- `shared/schema.ts`: Database schema and type definitions

## Project Status
- Successfully implemented core functionality
- Enhanced UI with modern design elements
- Expanded case repository to 132 cases from 7 business schools
- Created and tested email templates
- Implemented timezone handling for international users
- Added team formation for case competitions

## Case Collections
The platform includes case studies from:
- Kellogg School of Management
- McCombs School of Business
- UMKC Bloch School of Management
- MIT Sloan School of Management
- Wharton School of the University of Pennsylvania
- ESADE Business School MBA
- Fuqua School of Business
- Darden School of Business

## Credits
This platform was developed as a TypeScript/React conversion of an original Python-based system, with significant enhancements to the UI, case repository, and matching functionality.