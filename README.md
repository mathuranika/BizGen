# BizGen 🚀

**AI-Powered Business Idea Generator for the AI Agent Economy**

BizGen is an innovative web application that harnesses the power of artificial intelligence to generate creative and actionable business ideas specifically tailored for the emerging AI agent economy. Built with modern web technologies and secure authentication, it provides users with instant, AI-generated business concepts formatted with clear headings, subheadings, and bullet points.

## 🌐 Live Demo

The application is currently deployed and accessible at:
**[https://bizgen-1dqntzasr-mathuranikas-projects.vercel.app](https://bizgen-1dqntzasr-mathuranikas-projects.vercel.app)**

> **Note:** This is a Vercel deployment URL. For production use, consider setting up a custom domain.

## ✨ Features

- **AI-Powered Generation**: Leverages OpenAI's GPT models to generate innovative business ideas focused on AI agents
- **Real-time Streaming**: Server-Sent Events (SSE) provide a smooth, real-time streaming experience as ideas are generated
- **Secure Authentication**: Integrated with Clerk for robust user authentication and authorization
- **Beautiful UI**: Modern, responsive design with gradient backgrounds and smooth animations
- **Dark Mode Support**: Automatically adapts to user's system preferences
- **Markdown Rendering**: Ideas are formatted with Markdown for clear, structured presentation

## 🛠️ Tech Stack

### Frontend
- **[Next.js 15](https://nextjs.org/)** - React framework with Pages Router
- **[React 19](https://react.dev/)** - UI library
- **[TypeScript](https://www.typescriptlang.org/)** - Type-safe JavaScript
- **[Tailwind CSS v4](https://tailwindcss.com/)** - Utility-first CSS framework
- **[Clerk](https://clerk.com/)** - Authentication and user management
- **[React Markdown](https://github.com/remarkjs/react-markdown)** - Markdown rendering with GFM support

### Backend
- **[FastAPI](https://fastapi.tiangolo.com/)** - Modern Python web framework
- **[OpenAI API](https://openai.com/api/)** - AI model integration
- **[Uvicorn](https://www.uvicorn.org/)** - ASGI server
- **[fastapi-clerk-auth](https://pypi.org/project/fastapi-clerk-auth/)** - Clerk authentication for FastAPI

## 📋 Prerequisites

Before you begin, ensure you have the following installed:
- **Node.js** (v18 or higher)
- **npm** or **yarn** or **pnpm**
- **Python** (v3.8 or higher)
- **pip** (Python package manager)

## 🚀 Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/mathuranika/BizGen.git
   cd BizGen
   ```

2. **Install Node.js dependencies**
   ```bash
   npm install
   # or
   yarn install
   # or
   pnpm install
   ```

3. **Install Python dependencies**
   ```bash
   pip install -r requirements.txt
   ```

## 🔑 Environment Variables

Create a `.env.local` file in the root directory and add the following environment variables:

### Required for Frontend (Clerk Authentication)
```env
NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY=your_clerk_publishable_key
CLERK_SECRET_KEY=your_clerk_secret_key
```

### Required for Backend (API)
```env
CLERK_JWKS_URL=your_clerk_jwks_url
OPENAI_API_KEY=your_openai_api_key
```

### How to get these values:
- **Clerk Keys**: Sign up at [clerk.com](https://clerk.com), create an application, and get your keys from the dashboard
- **CLERK_JWKS_URL**: Found in your Clerk dashboard under API Keys. The format is typically `https://<your-clerk-domain>.clerk.accounts.dev/.well-known/jwks.json` where `<your-clerk-domain>` is your specific Clerk instance domain shown in your dashboard
- **OPENAI_API_KEY**: Get your API key from [OpenAI Platform](https://platform.openai.com/api-keys)

## 💻 Running the Application

### Development Mode

1. **Start the Next.js development server**
   ```bash
   npm run dev
   # or
   yarn dev
   # or
   pnpm dev
   ```

2. **Start the FastAPI backend server** (in a separate terminal)
   ```bash
   cd api
   uvicorn index:app --reload
   ```

3. **Open your browser**
   Navigate to [http://localhost:3000](http://localhost:3000)

### Production Build

1. **Build the Next.js application**
   ```bash
   npm run build
   npm run start
   ```

2. **Run the FastAPI server**
   ```bash
   cd api
   uvicorn index:app --host 0.0.0.0 --port 8000
   ```

## 📁 Project Structure

```
BizGen/
├── api/                      # Backend FastAPI application
│   └── index.py             # Main API endpoint with SSE streaming
├── pages/                   # Next.js pages
│   ├── _app.tsx            # App wrapper with Clerk provider
│   ├── _document.tsx       # Custom document structure
│   ├── index.tsx           # Landing page
│   └── product.tsx         # Main app page with idea generator
├── public/                  # Static assets
│   ├── favicon.ico
│   └── *.svg               # Various SVG icons
├── styles/                  # Global styles
│   └── globals.css
├── package.json            # Node.js dependencies
├── requirements.txt        # Python dependencies
├── next.config.ts          # Next.js configuration
├── tsconfig.json           # TypeScript configuration
├── tailwind.config.js      # Tailwind CSS configuration
└── eslint.config.mjs       # ESLint configuration
```

## 🔌 API Endpoints

### `GET /api`
Generates a new business idea for AI agents using OpenAI's GPT model.

**Authentication**: Required (Clerk JWT token)

**Response**: Server-Sent Events (SSE) stream

**Headers**:
```
Authorization: Bearer <clerk_jwt_token>
```

**Response Format**:
```
data: Generated
data:  
data: text
data:  
data: chunk
```

## 🌍 Deployment

This application is deployed on [Vercel](https://vercel.com). To deploy your own instance:

1. **Fork this repository**

2. **Connect to Vercel**
   - Go to [vercel.com](https://vercel.com)
   - Import your forked repository
   - Configure environment variables in the Vercel dashboard

3. **Set up the Python API**
   - Vercel automatically detects the `api/` directory
   - Ensure all environment variables are set

4. **Deploy**
   - Vercel will automatically deploy on every push to main branch

### Environment Variables on Vercel
Add all the environment variables mentioned in the [Environment Variables](#-environment-variables) section to your Vercel project settings.

## 🧪 Linting

Run ESLint to check code quality:
```bash
npm run lint
```

## 🤝 Contributing

Contributions are welcome! Here's how you can help:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

### Development Guidelines
- Follow the existing code style
- Write meaningful commit messages
- Test your changes thoroughly
- Update documentation as needed

## 📄 License

This project is available for use under standard terms. Please contact the repository owner for specific licensing information.

