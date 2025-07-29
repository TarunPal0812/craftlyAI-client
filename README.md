# CraftlyAI Frontend

This is the frontend for CraftlyAI, an AI-powered content and image generation platform. The frontend is built with **React** and **Vite**, and uses **Clerk** for authentication. It communicates with the CraftlyAI backend via REST APIs.

---

## Features

- User authentication (Clerk)
- Generate AI articles and blog titles
- Generate and publish AI images
- Remove backgrounds or objects from images
- Resume review (PDF upload)
- View, like, and publish creations
- Free and premium usage plans

---

## Tech Stack

- React (Vite)
- Clerk (Authentication)
- Axios (API requests)
- Tailwind CSS (Styling)
- React Router

---

## Getting Started

1. **Clone the repository:**

   ```bash
   git clone https://github.com/TarunPal0812/craftlyAI-client.git
   cd craftlyAI
   ```

2. **Install dependencies:**

   ```bash
   npm install
   ```

3. **Configure environment variables:**  
   Create a `.env` file in `/frontend` with the following:

   ```
   VITE_CLERK_PUBLISHABLE_KEY=your_clerk_publishable_key
   VITE_BASE_URL=https://craftlyai-server.onrender.com
   ```

4. **Run the development server:**
   ```bash
   npm run dev
   ```

---

## Environment Variables

| Variable                   | Description                    |
| -------------------------- | ------------------------------ |
| VITE_CLERK_PUBLISHABLE_KEY | Clerk frontend publishable key |
| VITE_BASE_URL              | Backend API base URL           |

---

## API Usage Example

All requests must include the Clerk session token in the `Authorization` header.

### Example: Generate Article

```js
import axios from "axios";
const res = await axios.post(
  `${import.meta.env.VITE_BASE_URL}/api/ai/generate-article`,
  { prompt: "Write about the future of AI.", length: 500 },
  { headers: { Authorization: `Bearer ${sessionToken}` } }
);
```

---

## Folder Structure

```
src/
  components/      // Reusable UI components
  pages/           // Route pages (Home, Dashboard, etc.)
  api/             // API utility functions
  hooks/           // Custom React hooks
  App.jsx
  main.jsx
```

---

## Authentication

- Uses [Clerk React SDK](https://clerk.com/docs/reference/clerk-react)
- Protect routes with `<SignedIn>` and `<SignedOut>` components
- Access user info and session tokens via Clerk hooks

---

## Live Frontend

🌐 [https://craftlyai-client.netlify.app/](https://craftlyai-client.netlify.app/)

---
