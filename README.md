# Time-limited-secure-file-sharer
It is a lightweight, ephemeral file-sharing web application. Built with a focus on privacy and simplicity, it allows you to upload files that "self-destruct" based on time or download count. No server-side setup required—just your browser and a Supabase instance.

✨ Key Features

⏱️ Auto-Expiration: Set links to vanish after a specific duration (1 hour to 1 week).

🔢 Download Thresholds: Enforce a "One-Time Read" or a specific download limit.

🔒 Encrypted Storage: Leverages Supabase Storage with expiring Signed URLs.

🔑 Optional Passkeys: Add a password layer to prevent unauthorized access to sensitive links.

📱 Mobile-First: A fully responsive UI styled with Tailwind CSS.


🛠️ The Tech Stack

Frontend: Vanilla JavaScript (ES6+) & HTML5

Styling: Tailwind CSS (Modern utility-first CSS)

Backend & DB: Supabase (PostgreSQL)

Storage: Supabase Storage Buckets

Because this app is a standalone HTML project, there is zero installation required.

1. Local Setup
Download the source code to your local machine.

Open index.html in your favorite code editor (we recommend VS Code).

Configure API Keys: Update the configuration block near the bottom of the script tag:

// --- CONFIGURATION ---

const supabaseUrl = "https://your-project-id.supabase.co";

const supabaseKey = "your-anon-key";

const BUCKET_NAME = "uploads";

const TABLE_NAME = "files";

2. Running the App
For the best experience (and to prevent CORS errors), use a local development server.
VS Code: Install the Live Server extension and click "Go Live."

🗄️ Supabase Configuration
To enable the "self-destruct" logic, configure your Supabase backend as follows:

1. Storage
Create a Public Bucket named uploads.

2. Database Schema
Run snippet in your Supabase SQL Editor to create the necessary table.

3. Security (RLS)
Ensure Row Level Security is enabled on the files table with policies allowing:

INSERT: Public access (for uploads).

SELECT: Public access (to verify expiration and download limits).

🤝 Contributing

Contributions are welcome!

Fork the project

Create your Feature Branch

Commit your Changes

Push to the Branch

Open a Pull Request

📄 License

Distributed under the MIT License. Use it, tweak it, and share securely!





