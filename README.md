 Riffinity.ai

A full-stack AI-powered chat application built with:

Backend: Node.js, Express, TypeScript, OpenAI API, MongoDB

Frontend: React, Vite, TypeScript, CSS

Database: MongoDB

This project allows users to chat with an AI assistant, manage multiple chat threads, view chat history, and delete conversations.

🚀 Features

🔐 Secure API key management with .env

💬 Chat with AI using OpenAI’s GPT-4o mini model

🗂️ Thread-based conversation storage in MongoDB

📝 Sidebar with chat history (view, create, delete threads)

⏳ Loader while waiting for AI responses

🎨 Syntax highlighting for AI code responses (React Markdown + highlight.js)

📂 Project Structure
Backend (/backend)
backend/
 ├── src/
 │    ├── models/        # Mongoose schemas & models
 │    │     └── Thread.ts
 │    ├── routes/        # Express routes
 │    │     └── chat.ts
 │    ├── utils/         # Utility files
 │    │     └── openai.ts
 │    └── server.ts      # Main server entry
 ├── dist/               # Compiled JS files (after tsc)
 ├── .env                # API keys & config
 ├── tsconfig.json
 ├── package.json

Frontend (/frontend)
frontend/
 ├── src/
 │    ├── components/
 │    │     ├── Sidebar.tsx
 │    │     ├── ChatWindow.tsx
 │    │     └── Chat.tsx
 │    └── App.tsx
 ├── public/
 ├── package.json

⚙️ Setup Instructions
1. Clone the Repository
git clone https://github.com/your-username/ai-chat-app.git
cd ai-chat-app

2. Backend Setup
cd backend
npm init -y
tsc --init
npm install express @types/express cors nodemon openai mongoose dotenv


Update tsconfig.json:

"rootDir": "./src",
"outDir": "./dist"


Add scripts in package.json:

"scripts": {
  "dev": "npx tsc -b && node dist/server.js"
}


Create .env:

OPENAI_API_KEY=your_api_key_here
MONGO_URI=your_mongo_connection_string
PORT=5000


Run backend:

npm run dev

3. Frontend Setup
cd frontend
npm create vite@latest . -- --template react-ts
npm install react-markdown rehype-highlight highlight.js react-spinners axios


Start frontend:

npm run dev

🔑 API Routes
Thread Routes

GET /thread → Get all threads

GET /thread/:threadId → Get specific thread

DELETE /thread/:threadId → Delete a thread

Chat Routes

POST /chat → Send a message

✅ If threadId exists → continue conversation

✅ If threadId does not exist → create new thread

🖼️ Frontend Components

Sidebar → Displays history, create/delete chat

ChatWindow → Navbar, Chat display, Input box

Chat → Renders AI and user messages (with markdown + syntax highlighting)

🛠️ Tech Stack

Backend: Node.js, Express, TypeScript, MongoDB, Mongoose, OpenAI API

Frontend: React, Vite, TypeScript, React Markdown, Highlight.js, CSS

Other: dotenv, cors, nodemon, axios
