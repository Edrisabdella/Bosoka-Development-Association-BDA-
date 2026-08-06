🌳 Bosoka Development Association – Full‑Stack Platform
A complete, production‑ready web application for the Bosoka Development Association (BDA).
This platform manages members, donations, training, meetings, documents, news, events, projects, partners, volunteers, reports, gallery, committee, and more – all in one integrated system.

📌 Table of Contents
Overview

Features

Technology Stack

Project Structure

Installation & Setup

Environment Variables

API Endpoints

Frontend Pages

Deployment

Security

Data Storage

Customization

License

Contact

📖 Overview
The BDA Platform is a full‑stack web application built for the Bosoka Development Association to digitise and streamline its internal operations. It replaces manual record‑keeping with a modern, responsive, and secure digital ecosystem.

Key capabilities:

Member registration & approval workflow – anyone can register; admins approve/reject.

Donation management – record contributions with payment methods and messages.

Document & file upload – store PDFs, images, and other files with categories.

Training & meeting scheduling – schedule sessions and join online meetings via Google Meet.

Live training room – real‑time video sessions using Jitsi.

Content management – publish news, events, projects, and partner information.

Volunteer & committee management – track opportunities and team members.

Reporting & gallery – generate reports and manage image galleries.

Admin dashboard – overview statistics, approve members, export/import data, sync to email.

The application is fully responsive and works on desktops, tablets, and mobile devices. It can also be installed as a Progressive Web App (PWA) for offline access.

✨ Features
👥 Member Management
Register as a member with name, email, phone, type, address, and photo.

Pending approval workflow – admin reviews and approves/rejects.

Search and filter approved members.

Delete members (admin only).

💰 Donation System
Record donations with donor name, amount, payment method, and optional message.

View donation history with running total.

Donation receipts (downloadable PDF – coming soon).

📁 File & Document Management
Upload files (PDF, Word, Excel, images, etc.) with title, category, and description.

Drag‑and‑drop support.

Document library to browse all uploaded files.

Download and delete files.

🎓 Training & Materials
Schedule training sessions with date, duration, and description.

Upload training materials (documents, guides, etc.).

List and delete trainings/materials.

📅 Meeting Room
Schedule meetings with date, time, location, and description.

Each meeting includes a "Join Meeting" button that opens a Google Meet link.

Delete meetings.

📡 Live Room
One‑click "Join Live Room" button that opens a Jitsi video session.

History of past live sessions (automatically recorded).

📰 News & Events
Publish news/announcements with title and content.

Add events with date and description.

Delete news/events.

🏗️ Projects & Partners
Add projects with title, status (Active/Planning/Completed), and description.

Add partner organisations with name and type.

Delete projects/partners.

🤝 Volunteer Opportunities
Add volunteer opportunities with title, location, and description.

Track total volunteers count on dashboard.

📊 Reports & Gallery
Generate reports with title and date.

Add images to the gallery with title and date.

Delete reports/gallery items.

🧑‍💼 Committee Management
Add committee members with name and role.

Delete committee members.

📧 Contact & Messaging
Contact form sends messages to the admin email (via mailto:).

Contact info (address, phone, email, website, Telegram) displayed.

🛠️ Admin Dashboard
Statistics: total members, pending approvals, total donations, documents, volunteers.

Quick Actions: add member, donate, approve, view constitution, upload, live room.

Admin Approvals: dedicated page to review and approve/reject pending members.

Admin Tools: export all data (JSON), import data (JSON), clear all data, sync to email.

Settings: platform name, currency, admin email.

🔒 Security & Data
Data stored in MongoDB Atlas (cloud database).

Environment variables for sensitive credentials.

Optional JWT authentication (ready to enable).

All data can be exported/imported for backup.

📱 PWA Ready
Installable as a mobile application.

Works offline (cached via service worker – coming soon).

🛠️ Technology Stack
Backend
Runtime: Node.js

Framework: Express.js

Database: MongoDB (Mongoose ODM)

Authentication: JWT + bcrypt (optional, ready to use)

File Handling: Multer (base64 storage)

Environment: dotenv

Security: cors, helmet (optional)

Frontend
Language: HTML5, CSS3, JavaScript (Vanilla)

Icons: Font Awesome 6

Fonts: Google Fonts (Inter)

PWA: Manifest + Service Worker (basic)

API Communication: fetch() with async/await

Deployment
Hosting: Render, Vercel, Netlify, or any Node.js host.

Database: MongoDB Atlas.

📁 Project Structure
text
bda-platform/
├── server.js                 # Main Express server
├── package.json              # Dependencies & scripts
├── .env                      # Environment variables (create yourself)
├── models/                   # Mongoose models (15 files)
│   ├── Member.js
│   ├── Donation.js
│   ├── File.js
│   ├── Training.js
│   ├── Material.js
│   ├── Meeting.js
│   ├── News.js
│   ├── Event.js
│   ├── Project.js
│   ├── Partner.js
│   ├── Volunteer.js
│   ├── Report.js
│   ├── Gallery.js
│   ├── Committee.js
│   └── Contact.js
├── routes/                   # Express route handlers (15 files)
│   ├── members.js
│   ├── donations.js
│   ├── files.js
│   ├── trainings.js
│   ├── materials.js
│   ├── meetings.js
│   ├── news.js
│   ├── events.js
│   ├── projects.js
│   ├── partners.js
│   ├── volunteers.js
│   ├── reports.js
│   ├── gallery.js
│   ├── committee.js
│   └── contacts.js
└── public/                   # Static frontend
    └── index.html            # Single‑page application (full UI + API integration)
⚙️ Installation & Setup
1. Clone the repository
bash
git clone https://github.com/yourusername/bda-platform.git
cd bda-platform
2. Install dependencies
bash
npm install
3. Create .env file (see below)
4. Start MongoDB (local or use Atlas)
If using MongoDB Atlas, get your connection string.

If using local MongoDB, ensure it's running and set MONGODB_URI=mongodb://localhost:27017/bda.

5. Run the application
bash
npm start
For development with auto‑reload:

bash
npm run dev
The app will be available at http://localhost:10000.

🔐 Environment Variables
Create a .env file in the root directory with the following:

env
PORT=10000
MONGODB_URI=mongodb+srv://<username>:<password>@cluster.mongodb.net/bda?retryWrites=true&w=majority
JWT_SECRET=your_super_secret_key_change_this
PORT – the port the server listens on (Render sets this automatically).

MONGODB_URI – your MongoDB connection string (use Atlas for production).

JWT_SECRET – used for signing JWTs (optional but recommended for authentication).

📡 API Endpoints
All endpoints are prefixed with /api/. Each follows standard REST conventions.

Resource	Methods	Description
/members	GET, POST, PUT /:id, DELETE /:id	Manage members
/donations	GET, POST, DELETE /:id	Manage donations
/files	GET, POST, DELETE /:id	Manage uploaded files
/trainings	GET, POST, DELETE /:id	Manage training sessions
/materials	GET, POST, DELETE /:id	Manage training materials
/meetings	GET, POST, DELETE /:id	Manage meetings
/news	GET, POST, DELETE /:id	Manage news/announcements
/events	GET, POST, DELETE /:id	Manage events
/projects	GET, POST, DELETE /:id	Manage projects
/partners	GET, POST, DELETE /:id	Manage partners
/volunteers	GET, POST, DELETE /:id	Manage volunteer opportunities
/reports	GET, POST, DELETE /:id	Manage reports
/gallery	GET, POST, DELETE /:id	Manage gallery images
/committee	GET, POST, DELETE /:id	Manage committee members
/contacts	GET, POST, DELETE /:id	Manage contact messages
Example request:

http
POST /api/members
Content-Type: application/json

{
  "name": "Edris Abdella",
  "email": "edris@example.com",
  "phone": "+251905131051",
  "type": "Full Member",
  "address": "Dire Dawa",
  "status": "pending",
}
Example response:

json
{
  "_id": "60f7c5c5e6b3c3b4d4e5f6a7",
  "name": "Edris Abdella",
  "email": "edris@example.com",
  "phone": "+251905131051",
  "type": "Full Member",
  "address": "Dire Dawa",
  "status": "pending",
  "createdAt": "2026-08-07T12:00:00.000Z"
}
🖥️ Frontend Pages
The frontend is a single‑page application with over 40 pages/sections, all accessible via the sidebar navigation.

Public Pages
Home (Dashboard)

About

Constitution (82 chapters)

Members (Registration & List)

Admin Approvals

Donations (Make & History)

Training Room (Schedule & List)

Training Materials (Upload & List)

Meeting Room (Schedule & Join)

Live Room (Join & History)

File Upload

Document Library

News

Events

Projects

Partners

Volunteer Opportunities

Reports

Gallery

Committee

Resources

FAQ

Contact

Settings

Interactive Features
Search – filter members by name or email.

Modals – all add/edit forms use clean modals.

Toast notifications – feedback for every action.

Slideshow – rotating hero images on the dashboard.

Statistics – live counters on the dashboard.

🚀 Deployment (Render)
Push all code to a GitHub repository.

Create a new Web Service on Render.

Connect your GitHub repo.

Set environment variables (PORT, MONGODB_URI, JWT_SECRET).

Build command: npm install

Start command: npm start

Deploy – Render will build and run your app.

Your app will be live at https://your-app-name.onrender.com.

Note: Render provides a free MongoDB Atlas tier – you can also host your database there.

🔒 Security
Environment variables – all secrets are kept outside the codebase.

CORS – enabled for cross‑origin requests.

Input validation – basic validation on required fields.

JWT ready – you can add authentication middleware to protect routes.

Rate limiting – can be added via express-rate-limit.

HTTPS – enforced by Render (and other hosts) automatically.

💾 Data Storage
MongoDB Atlas – all data is stored in the cloud.

Backup – use the Export feature to download a JSON backup.

Import – restore data from a JSON backup.

Clear All – delete all data (use with caution).

🧩 Customization
Replace Constitution Content
The constitution data (82 chapters) is defined in the frontend articleSamples object. You can replace it with the full text of your association's constitution.

Change Branding
Logo – replace the text/icon in the sidebar.

Colors – modify CSS variables (--primary, --gold, etc.).

Motto – update the text in the hero-slideshow and about pages.

Add/Remove Pages
Add a new page by creating a <section class="page" id="page-..."> and adding a link in the sidebar.

The navigation and page loading are handled automatically.

Enable Authentication
The backend includes JWT and bcrypt but they are not enforced. To add authentication:

Create a User model.

Add login/register endpoints.

Add a middleware to protect routes.

Modify the frontend to send a JWT token in the Authorization header.

📄 License
This project is proprietary to the Bosoka Development Association.
All rights reserved. Unauthorized distribution or commercial use is prohibited.

For educational and non‑commercial use, you may view and modify the code for personal learning.

📞 Contact
Bosoka Development Association
📍 Chiro, Harargee Lixaa, Oromiyaa, Ethiopia
📧 bosokadevtassociation@gmail.com
📞 +251967568888
🌐 https://bosoka-development-association.onrender.com
📱 Telegram Channel

🙏 Acknowledgements
Font Awesome – for icons.

Google Fonts – for the Inter typeface.

Jitsi Meet – for the live room integration.

Google Meet – for meeting links.

MongoDB Atlas – for cloud database hosting.

Render – for deployment.

Built with dedication for the community of Bosoka.
Misooma Itti Fufiinsa Qabuuf Waliin Hojjenna – Working Together for Sustainable Development.