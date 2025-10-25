# 🚀 BizGen - AI-Powered Business Idea Generator

BizGen is an intelligent web application that generates innovative business ideas for the AI agent economy using OpenAI's GPT-5-nano model. Built with modern web technologies, it provides authenticated users with creative, well-formatted business concepts through an elegant streaming interface.

## ✨ Features

- **AI-Powered Idea Generation**: Leverages OpenAI's GPT-5-nano model to generate creative and innovative business ideas
- **Real-time Streaming**: Ideas stream in real-time for an engaging user experience
- **User Authentication**: Secure authentication powered by Clerk
- **Beautiful UI**: Modern, responsive interface with dark mode support
- **Markdown Rendering**: Business ideas are beautifully formatted with headings, bullet points, and rich text
- **User-Specific Tracking**: JWT-based authentication allows for future user-specific features and usage tracking

## 🛠️ Tech Stack

### Frontend
- **Next.js 15.5.6** - React framework for production
- **React 19.1.0** - UI library
- **TypeScript** - Type-safe development
- **Tailwind CSS v4** - Utility-first CSS framework
- **React Markdown** - Markdown rendering with GitHub Flavored Markdown support
- **Clerk** - Authentication and user management

### Backend
- **FastAPI** - Modern Python web framework
- **OpenAI API** - GPT-5-nano model integration
- **Uvicorn** - ASGI server
- **Clerk Auth** - JWT-based authentication validation

### Development Tools
- **ESLint** - Code linting
- **PostCSS** - CSS processing
- **TypeScript** - Static type checking

## 📋 Prerequisites

Before you begin, ensure you have the following installed:
- **Node.js** (v20 or higher)
- **npm** or **yarn** or **pnpm**
- **Python** (v3.8 or higher)
- **pip** (Python package manager)

You'll also need accounts and API keys for:
- **OpenAI API** - For GPT-5-nano access
- **Clerk** - For authentication services

## 🚀 Installation

### 1. Clone the Repository

```bash
git clone https://github.com/mathuranika/BizGen.git
cd BizGen
```

### 2. Install Frontend Dependencies

```bash
npm install
# or
yarn install
# or
pnpm install
```

### 3. Install Backend Dependencies

```bash
pip install -r requirements.txt
```

## 🔐 Environment Variables

Create a `.env.local` file in the root directory with the following variables:

```env
# Clerk Authentication
NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY=your_clerk_publishable_key
CLERK_SECRET_KEY=your_clerk_secret_key
CLERK_JWKS_URL=your_clerk_jwks_url

# OpenAI API
OPENAI_API_KEY=your_openai_api_key
```

### Getting API Keys

1. **Clerk**: 
   - Sign up at [clerk.com](https://clerk.com)
   - Create a new application
   - Copy the publishable key, secret key, and JWKS URL from your Clerk dashboard

2. **OpenAI**:
   - Sign up at [platform.openai.com](https://platform.openai.com)
   - Navigate to API keys section
   - Create a new API key

## 🏃‍♂️ Running the Application

### Development Mode

1. **Start the Backend API**:
```bash
uvicorn api.index:app --reload
```
The API will be available at `http://localhost:8000`

2. **Start the Frontend** (in a new terminal):
```bash
npm run dev
# or
yarn dev
# or
pnpm dev
```
The application will be available at `http://localhost:3000`

### Production Build

```bash
npm run build
npm run start
```

## 📁 Project Structure

```
BizGen/
├── api/
│   └── index.py              # FastAPI backend with OpenAI integration
├── pages/
│   ├── _app.tsx             # Next.js app wrapper
│   ├── _document.tsx        # Custom document
│   ├── index.tsx            # Landing page
│   └── product.tsx          # Main idea generation page
├── public/                  # Static assets
│   ├── favicon.ico
│   └── *.svg               # Icons and images
├── styles/
│   └── globals.css         # Global styles and Tailwind imports
├── next.config.ts          # Next.js configuration
├── tsconfig.json           # TypeScript configuration
├── tailwind.config.js      # Tailwind CSS configuration
├── package.json            # Frontend dependencies
├── requirements.txt        # Python dependencies
└── README.md              # This file
```

## 🎨 How It Was Made

### Development Process

1. **Project Initialization**: Started with Next.js using TypeScript and Tailwind CSS
2. **Authentication Setup**: Integrated Clerk for secure user authentication
3. **Backend Development**: Built a FastAPI server to handle OpenAI API calls
4. **Streaming Implementation**: Implemented Server-Sent Events (SSE) for real-time idea streaming
5. **UI/UX Design**: Created a modern, gradient-based design with dark mode support
6. **Markdown Integration**: Added React Markdown for beautiful idea formatting

### Key Technical Decisions

- **Next.js with TypeScript**: Chosen for type safety and excellent developer experience
- **FastAPI Backend**: Selected for its modern async capabilities and easy integration with Python AI libraries
- **Clerk Authentication**: Provides enterprise-grade auth without the complexity
- **Streaming Architecture**: Enhances user experience by showing ideas as they're generated
- **Tailwind CSS**: Enables rapid UI development with consistent design patterns

## 🌐 Deployment

### Deploying to Vercel (Frontend)

1. Push your code to GitHub
2. Visit [vercel.com](https://vercel.com)
3. Import your GitHub repository
4. Configure environment variables
5. Deploy

### Deploying the API

The FastAPI backend can be deployed to:
- **Vercel** (as serverless functions)
- **Railway**
- **Render**
- **AWS Lambda**
- **Google Cloud Run**

Make sure to set all required environment variables in your deployment platform.

## 📝 Usage

1. Visit the landing page at `http://localhost:3000`
2. Click "Sign In" to authenticate with Clerk
3. Navigate to the "Go to App" or "Generate Ideas Now" button
4. Watch as AI generates creative business ideas in real-time
5. Ideas are formatted with headings, subheadings, and bullet points for easy reading

## 🤝 Contributing

Contributions are welcome! Feel free to:
- Report bugs
- Suggest new features
- Submit pull requests

## 📄 License

This project is open source and available under the MIT License.

## 👨‍💻 Author

Created by [mathuranika](https://github.com/mathuranika)

## 🙏 Acknowledgments

- OpenAI for the GPT-5-nano API
- Clerk for authentication services
- Next.js team for the amazing framework
- FastAPI for the modern Python backend framework
