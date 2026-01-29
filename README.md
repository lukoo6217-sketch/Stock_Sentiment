Start Up Procedure:

Backend:
cd ~\downloads\sentiment_analysis_finviz_app\backend
.\venv\Scripts\Activate
uvicorn main:app --reload --port 8000

Frontend: 
cd ~\documents\sentiment-analysis 
npm start

SentimentPulse - Startup Instructions

 A modern stock news sentiment analysis application with a FastAPI backend and React frontend.

 ---

 ## 📁 Project Structure

 ```
 sentiment_analysis_finviz_app/
 ├── backend/
 │   ├── main.py          	# FastAPI backend server
 │   ├── requirements.txt 	# Python dependencies
 │   └── venv/            	# Python virtual environment
 │
 └── frontend/            	# React application (or your React project folder)
 	├── src/
 	│   ├── App.js
 	│   ├── SentimentPulse.jsx
 	│   ├── index.js
 	│   └── index.css
 	├── package.json
 	├── tailwind.config.js
 	└── postcss.config.js
 ```

 ---

 ## 🚀 Quick Start (Daily Use)

 ### Step 1: Start the Backend (PowerShell Window #1)

 ```powershell
 # Navigate to backend folder
 cd C:\Users\pstri\downloads\sentiment_analysis_finviz_app\backend

 # Activate virtual environment
 .\venv\Scripts\Activate.ps1

 # Start the server
 uvicorn main:app --reload --port 8000
 ```

 You should see:
 ```
 INFO: 	Uvicorn running on http://127.0.0.1:8000
 INFO: 	Application startup complete.
 ```

 ### Step 2: Start the Frontend (PowerShell Window #2)

 ```powershell
 # Navigate to frontend folder
 cd C:\Users\pstri\documents\sentiment-analysis

 # Start React development server
 npm start
 ```

 You should see:
 ```
 Compiled successfully!
 Local: http://localhost:3000
 ```

 ### Step 3: Use the Application

 1. Open your browser to **http://localhost:3000**
 2. Enter a stock ticker symbol (e.g., AAPL, TSLA, NVDA, COST)
 3. Click **Analyze**
 4. View sentiment results, charts, and word clouds

 ---

 ## 🔧 First-Time Setup (One-Time Only)

 ### Backend Setup

 ```powershell
 # 1. Create project folder
 mkdir C:\Users\pstri\downloads\sentiment_analysis_finviz_app\backend
 cd C:\Users\pstri\downloads\sentiment_analysis_finviz_app\backend

 # 2. Create virtual environment
 python -m venv venv

 # 3. Activate virtual environment
 .\venv\Scripts\Activate.ps1

 # 4. If you get an execution policy error, run this first (as Administrator):
 Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser

 # 5. Install dependencies
 pip install fastapi uvicorn httpx beautifulsoup4 pandas nltk pydantic

 # 6. Copy main.py to this folder
 # (Download from the files I provided)
 ```

 ### Frontend Setup

 ```powershell
 # 1. Create React app (if not already created)
 cd C:\Users\pstri\documents
 npx create-react-app sentiment-analysis
 cd sentiment-analysis

 # 2. Install dependencies
 npm install recharts
 npm install -D tailwindcss@3 postcss autoprefixer

 # 3. Initialize Tailwind
 npx tailwindcss init -p

 # 4. Copy these files to your project:
 #	- SentimentPulse.jsx → src/
 #	- App.js → src/ (replace existing)
 #	- Update src/index.css with Tailwind directives

 # 5. Update src/index.css to contain:
 @tailwind base;
 @tailwind components;
 @tailwind utilities;
 ```

 ---

 ## 🛑 Stopping the Application

 ### Stop Backend
 - Press `Ctrl + C` in the backend PowerShell window

 ### Stop Frontend
 - Press `Ctrl + C` in the frontend PowerShell window

 ---

 ## 🔍 Troubleshooting

 ### Backend Issues

 | Problem | Solution |
 |---------|----------|
 | `'venv' is not recognized` | Run `python -m venv venv` first |
 | `Activate.ps1 cannot be loaded` | Run `Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser` |
 | `Module not found` | Activate venv and run `pip install -r requirements.txt` |
 | `Port 8000 already in use` | Use `uvicorn main:app --reload --port 8001` (update frontend API_BASE_URL) |

 ### Frontend Issues

 | Problem | Solution |
 |---------|----------|
 | `npm not recognized` | Install Node.js from https://nodejs.org |
 | `Module not found: recharts` | Run `npm install recharts` |
 | Tailwind styles not working | Check index.css has `@tailwind` directives |
 | `Cannot connect to backend` | Make sure backend is running on port 8000 |

 ### FinViz Scraping Issues

 | Problem | Solution |
 |---------|----------|
 | `No news found for ticker` | Verify ticker symbol is correct |
 | `403 Forbidden` | Wait a few minutes and try again (rate limited) |
 | Timeout errors | Check your internet connection |

 ---

 ## 🌐 API Endpoints

 | Endpoint | Method | Description |
 |----------|--------|-------------|
 | `http://localhost:8000/` | GET | Health check |
 | `http://localhost:8000/analyze` | POST | Analyze sentiment for a ticker |
 | `http://localhost:8000/debug/{ticker}` | GET | Debug scraping for a ticker |

 ### Example API Call (for testing)

 ```powershell
 # Test in browser
 http://localhost:8000/debug/AAPL

 # Or use curl
 curl -X POST "http://localhost:8000/analyze" -H "Content-Type: application/json" -d '{"ticker": "AAPL", "remove_stopwords": true}'
 ```

 ---

 ## 📋 File Checklist

 ### Backend Files (`backend/` folder)
 - [ ] `main.py` - The FastAPI server code
 - [ ] `requirements.txt` - Python dependencies
 - [ ] `venv/` - Virtual environment folder

 ### Frontend Files (`src/` folder)
 - [ ] `SentimentPulse.jsx` - Main React component
 - [ ] `App.js` - App entry point
 - [ ] `index.js` - React DOM render
 - [ ] `index.css` - Tailwind CSS imports

 ### Config Files (project root)
 - [ ] `tailwind.config.js` - Tailwind configuration
 - [ ] `postcss.config.js` - PostCSS configuration
 - [ ] `package.json` - Node.js dependencies

 ---

 ## 💡 Tips

 1. **Keep both terminals open** - Backend and frontend need to run simultaneously

 2. **Backend must start first** - The frontend calls the backend API

 3. **Check the console** - Debug messages appear in the backend PowerShell window

 4. **Valid ticker symbols** - Use standard NYSE/NASDAQ symbols (AAPL, GOOGL, MSFT, etc.)

 5. **Rate limiting** - If FinViz blocks requests, wait 1-2 minutes before retrying

 ---

 ## 🔄 Updating the Application

 ### Update Backend
 ```powershell
 cd backend
 .\venv\Scripts\Activate.ps1
 pip install --upgrade fastapi uvicorn
 ```

 ### Update Frontend
 ```powershell
 cd frontend
 npm update
 ```

 ---

 ## 📞 Support

 If you encounter issues:
 1. Check the Troubleshooting section above
 2. Look at the PowerShell console for error messages
 3. Test the `/debug/{ticker}` endpoint to diagnose scraping issues

 ---

 **Happy Analyzing! 📊**
  

