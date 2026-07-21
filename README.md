# Bosoka-Development-Association-BDA-
Waldaa Misooma Bosoqaa, Bosoka Development Association (BDA) Motto: Working Together for Sustainable Development
BDA Platform – Bosoka Development Association
Full‑featured internal management platform for the Bosoka Development Association (BDA).
A single‑file HTML5 application that combines membership management, donation tracking, document libraries, training/meeting scheduling, online meeting rooms, and much more – all in one modern, responsive dashboard.

🚀 Overview
The BDA Platform is built as a self‑contained, client‑side application that runs entirely in your browser. It is designed to help the association manage its day‑to‑day operations efficiently, with a clean interface and a comprehensive set of tools.

Key highlights:

30+ pages covering every aspect of association management.

Member registration & admin approval workflow – new members are added with a "pending" status; administrators approve or reject them.

Donation recording & history – track contributions with amounts, methods, and optional messages.

File upload & document library – upload files (any type) with titles, categories, and descriptions; all stored locally.

Training room – schedule training sessions with dates, durations, and descriptions.

Training materials – upload and organize learning resources.

Meeting room – schedule meetings with a "Join Meeting" button that opens a free Jitsi video call (no account required).

News, Events, Projects, Partners, Volunteers, Reports, Gallery, Committee – manage all engagement and reporting content.

Constitution viewer – browse all 82 chapters of the BDA constitution with summaries and article references.

Admin tools – export/import all data (JSON) for backup or migration, and clear all data when needed.

Fully responsive – works on desktops, tablets, and mobile devices.

✨ Features at a Glance
Section	Capabilities
Dashboard	Stats (members, approvals, donations, document count), quick‑action buttons, hero slideshow with association images.
About	Vision, mission, core values, motto.
Constitution	Browse 82 chapters with titles and summary content.
Members	Add new members (pending), search/filter approved members, delete members.
Admin Approvals	Review pending members, approve or reject.
Donations	Record donations with amount, method, message; view donation history.
Training Room	Schedule trainings with date, duration, description.
Training Materials	Upload and list training resources (title, category, description).
Meeting Room	Schedule meetings with date, time, location; each meeting includes a "Join Meeting" button that starts a free Jitsi video call.
File Upload	Upload files (any type) with title, category, description; drag‑and‑drop support.
Document Library	Browse all uploaded files.
News	Publish news/announcements with title and content.
Events	Add events with date and description.
Projects	Manage projects with title, status (Active/Planning/Completed), description.
Partners	Add partner organisations with name and type.
Volunteer	Add volunteer opportunities with title, location, description.
Reports	Generate (add) reports with title and date.
Gallery	Add image entries with title and date (placeholder for future image upload).
Committee	Manage committee members with name and role.
Resources	Quick links to important documents (constitution, forms, etc.).
FAQ	Frequently asked questions.
Contact	Address, phone, email, and a contact form (messages stored locally).
Settings	Platform name and currency (saved locally).
🛠️ Technology Stack
Frontend: HTML5, CSS3, Vanilla JavaScript

Icons: Font Awesome 6

Fonts: Google Fonts (Inter)

Data persistence: localStorage (all data stays in your browser)

Online meetings: Jitsi Meet (free, no registration) – embedded via window.open

Deployment: Any static web host (Render, Netlify, Vercel, GitHub Pages, etc.)

📦 Deployment
Because the application is a single HTML file with no server‑side dependencies, you can deploy it to any static hosting service.

Deploy on Render (recommended)
Create a new Web Service on Render.

Connect your repository (if using Git) or upload the HTML file directly.

Set the build command to nothing (or echo "Static site").

Set the publish directory to the folder containing the HTML file (e.g., .).

Environment variables: none required.

Deploy – Render will serve the file as a static site.

Alternatively, you can simply drag‑and‑drop the index.html file to any web server or use services like Netlify Drop or Vercel with a similar approach.

Local Testing
Just open the index.html file in any modern browser – it works offline (except for external icons/fonts, which load via CDN).

📂 Data Storage & Backup
All data (members, donations, files, etc.) is stored in your browser's localStorage.
Important: Clearing browser data will erase all information. Use the Export feature (under Admin) to download a JSON backup regularly.

Export: Downloads a complete JSON snapshot of all data.

Import: Upload a previously exported JSON file to restore data.

Clear All: Permanently deletes all stored data (confirmation required).

🔧 Customization
Constitution Content
The constitution data (82 chapters) is defined inside the JavaScript CONSTITUTION array.
You can replace the articleSamples object with the full text of your association's constitution to display the complete content.

Hero Slideshow Images
The homepage hero uses five placeholder images from provided URLs. You can change the style="background-image:url('...')" on each .slide element to your own images.

Branding
Logo: The sidebar logo can be changed by editing the .logo text or adding an image.

Colours: The CSS variables (--primary, --gold, etc.) allow easy rebranding.

Adding/Removing Pages
The sidebar navigation and corresponding page sections (<section class="page" id="page-...">) can be extended or removed as needed.

📖 Usage Guide
1. Member Registration & Approval
Go to Members → fill in the form and click Add Member.

The member appears with a Pending status.

Go to Admin Approvals → review the list and click Approve or Reject.

Approved members appear in the member list and contribute to the dashboard stats.

2. Making a Donation
Go to Donations → fill in donor details, amount, method, and optional message.

Click Donate Now – the donation is recorded and added to the history.

The total donation amount updates automatically on the dashboard.

3. Uploading Files
Go to File Upload → enter a title, select a category, add a description (optional).

Click the upload area or drag‑and‑drop a file.

Click Upload File – the file is stored (base64 encoded in localStorage) and appears in the Document Library and Dashboard count.

4. Scheduling Training / Meeting
Use the Training Room or Meeting Room pages.

Fill in the form (title, date, time, etc.) and submit.

For meetings, each entry includes a "Join Meeting" button – clicking it opens a new Jitsi Meet room with a unique name, allowing instant video conferencing.

5. Managing News, Events, Projects, etc.
Each content page has an "Add …" button that opens a modal form.

Fill in the required fields and submit – the item appears in the list immediately.

6. Export/Import Data
Go to Admin → under Admin Tools use Export to download a JSON file.

Use Import to upload a previously exported JSON file – all data will be replaced with the imported data.

Clear All resets everything (use with caution).

🧩 Online Meeting Integration
The Meeting Room uses Jitsi Meet – a free, open‑source video conferencing service.
When you click "Join Meeting" on a scheduled meeting, the platform opens a new tab with a Jitsi room named after the meeting title (plus a random suffix to avoid collisions).
No accounts or setup are required – participants can join immediately.

📄 License
This project is provided as a custom solution for the Bosoka Development Association.
You are free to use, modify, and distribute it for non‑commercial purposes.
Attribution to the original developer is appreciated but not required.

🤝 Support & Contributions
For issues, feature requests, or contributions, please contact the association directly via the contact form on the platform or email bosokadevtassociation@gmail.com.

🙏 Acknowledgements
Font Awesome for icons.

Google Fonts for the Inter typeface.

Jitsi for the free video conferencing service.

All founding members and contributors of the Bosoka Development Association.

Built with dedication for the community of Bosoka.
Misooma Itti Fufiinsa Qabuuf Waliin Hojjenna – Working Together for Sustainable Development