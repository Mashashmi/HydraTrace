HydraTrace: Oil Consumption Analytics

A professional industrial dashboard designed for mechanical engineers to monitor hydraulic oil consumption, inventory forecasting, and power pack diagnostics across production lines. By MASHASHMI.

Repository Architecture

This application uses a decoupled modern architecture so the frontend can be hosted statically (like on GitHub Pages), while data is securely managed by a cloud backend.

index.html: The complete React frontend built into a single file for easy hosting.

backend/: Contains the Python Flask REST API and JSON file database.

Step 1: Host the Frontend (GitHub Pages)

Upload this repository to GitHub.

In your repository, go to Settings > Pages.

Under "Build and deployment", set the Branch to main and click Save.

Within a few minutes, GitHub will give you a live URL for your dashboard.

Step 2: Host the Backend Server (Render / Heroku)

GitHub Pages only hosts static visual files. It cannot run Python code. To make the backend work 24/7, you need to host the backend folder on a free server.

Create a free account on Render.com.

Click New > Web Service.

Connect your GitHub repository.

Set the Root Directory to backend/.

Set the Build Command to: pip install -r requirements.txt

Set the Start Command to: gunicorn server:app

Click Create Web Service.

Step 3: Connect the Two

Render will give you a live URL (e.g., https://hydratrace-api.onrender.com).

Open your index.html file in GitHub.

Find line 39: const API_URL = 'http://127.0.0.1:5000/api/data';

Change that to your new Render URL: const API_URL = 'https://hydratrace-api.onrender.com/api/data';

Commit the change.

Your dashboard is now fully live on the cloud, and data can be accessed and modified from any device in the plant!