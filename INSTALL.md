# CaseBud Platform Installation Guide

## Prerequisites
Before you begin, ensure you have the following installed:
- Node.js (v18 or higher) and npm
- PostgreSQL (if using persistent database)

## Environment Setup

### 1. Clone the Repository
```bash
git clone https://github.com/casebud-match/casebud-replit.git
cd casebud-replit
```

### 2. Install Dependencies
```bash
npm install
```

### 3. Environment Variables
Create a `.env` file in the root directory with the following variables:

```
# Required for session management
SESSION_SECRET=your_session_secret_here

# Required for Zoom integration
ZOOM_CLIENT_ID=your_zoom_client_id
ZOOM_CLIENT_SECRET=your_zoom_client_secret

# Required for Google Calendar integration
GOOGLE_SERVICE_ACCOUNT_KEY=your_base64_encoded_service_account_key

# Optional for email notifications
EMAIL_USER=your_email_address
EMAIL_PASS=your_email_password

# Optional for PostgreSQL (if using persistent storage)
DATABASE_URL=postgres://username:password@localhost:5432/casebud
```

### 4. Database Setup (Optional - for persistent storage)
If using PostgreSQL instead of in-memory storage:

1. Create a PostgreSQL database:
   ```bash
   createdb casebud
   ```

2. Update the `DATABASE_URL` in your `.env` file

3. Modify `server/storage.ts` to use the `DatabaseStorage` implementation instead of `MemStorage`

4. Run database migrations:
   ```bash
   npm run db:migrate
   ```

### 5. Run the Application
```bash
npm run dev
```

The application will start on http://localhost:5000.

## External Service Setup

### Google Calendar Integration
1. Create a Google Cloud project
2. Enable the Google Calendar API
3. Create a service account with appropriate permissions
4. Download the service account key JSON file
5. Base64 encode the contents of the key file:
   ```bash
   cat your-key-file.json | base64
   ```
6. Add the encoded string to `GOOGLE_SERVICE_ACCOUNT_KEY` in your `.env` file

### Zoom Integration
1. Create a Zoom Developer account
2. Create a new OAuth app in the Zoom Marketplace
3. Set the redirect URL to `http://localhost:5000/api/zoom/callback`
4. Add the Client ID and Client Secret to your `.env` file

## Common Issues and Troubleshooting

### Timezone Handling
Make sure your server's timezone is properly configured. The application uses date-fns-tz for timezone conversion.

### Email Sending
If emails aren't being sent:
1. Check your email provider's security settings (may need to allow "less secure apps")
2. Verify your `EMAIL_USER` and `EMAIL_PASS` environment variables
3. For Gmail, consider using an app-specific password instead of your account password

### Case Files
The case PDFs should be placed in the `public/cases/` directory.

## Deployment

### On Replit
1. Create a new Replit from GitHub
2. Add all necessary secrets in the Replit secrets manager
3. Hit the "Run" button

### On Other Platforms
1. Build the client:
   ```bash
   npm run build
   ```
2. Start the server in production mode:
   ```bash
   npm start
   ```

## Maintenance
- Run `npm update` periodically to keep dependencies up to date
- Check for security vulnerabilities with `npm audit`
- Update case repository by adding new PDFs to `public/cases/` and updating `server/seed-cases.ts`