WHAT IS INCLUDED
- Frontend: HTML, CSS, JavaScript, Chart.js
- Backend: Python FastAPI REST API
- Demo dataset for six product teams and two clouds
- Cost allocation by team and customer
- Monthly cost trend, budget alerts, idle-compute recommendations
- CSV upload and export

REQUIREMENTS
- Python 3.10 or newer (Python 3.11 recommended)
- VS Code
- Internet connection for installing Python packages and loading Chart.js from CDN

MAC SETUP
1. Unzip the downloaded CloudWise_AI_Full_Project.zip.
2. Open VS Code.
3. Choose File > Open Folder and select CloudWise_AI_Full_Project.
4. In VS Code choose Terminal > New Terminal.

START BACKEND (Terminal 1)
Run:
cd backend
python3 -m venv .venv
source .venv/bin/activate
python -m pip install -r requirements.txt
uvicorn main:app --reload

Keep this terminal open. API docs: http://127.0.0.1:8000/docs

START FRONTEND (Terminal 2)
Open another terminal with the + button in the terminal panel, then run:
cd frontend
python3 -m http.server 5500

Open http://127.0.0.1:5500 in your browser.

WINDOWS NOTES
In backend folder create venv:
python -m venv .venv
.venv\Scripts\activate
python -m pip install -r requirements.txt
uvicorn main:app --reload

In a second terminal:
cd frontend
python -m http.server 5500
Then visit http://127.0.0.1:5500

CSV UPLOAD FORMAT
Required columns:
Month, Cloud, Team, Customer, Workload, Service, Cost_USD
Optional columns:
Budget_USD, Usage_Units, Idle_Percent
Month format should be YYYY-MM; costs are USD.

IMPORTANT LIMITATIONS
This is a hackathon prototype with fictional demo data. CSV upload replaces data in the running backend process only (it resets if the backend restarts). It does not automatically connect to AWS or Azure billing APIs, and it never changes infrastructure. Real deployment needs cloud billing integrations, authentication, persistent storage, and strict access controls. Savings values are estimates, not guarantees.
