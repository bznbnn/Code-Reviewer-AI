# AI-Powered Code Reviewer 🤖

[![React](https://img.shields.io/badge/React-18.x-blue)](https://reactjs.org/)
[![Node.js](https://img.shields.io/badge/Node.js-Express-green)](https://nodejs.org/)
[![AI](https://img.shields.io/badge/AI-Gemini-orange)](https://ai.google.dev/)
[![License](https://img.shields.io/badge/License-MIT-yellow)](LICENSE)

A full-stack application that provides automated, AI-driven code reviews using Google's Gemini AI. Submit your code and receive professional, detailed feedback in seconds!

## ✨ Features

- **🖥️ Modern Code Editor**: Syntax-highlighted code editor powered by CodeMirror
- **🤖 AI-Powered Analysis**: Professional code reviews using Google's Gemini AI
- **📊 Comprehensive Feedback**: 
  - Code quality and best practices assessment
  - Potential bugs and security issues
  - Performance optimization suggestions
  - Alternative approaches and improvements
  - Positive reinforcement for well-written code
- **⚡ Real-time Results**: Fast, markdown-formatted reviews
- **🎯 Multi-language Support**: Adaptable for various programming languages

## 🚀 Quick Start

### Prerequisites

- Node.js (v16 or higher)
- npm or yarn
- Google Gemini API key

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/Villwin007/AI-Powered-Code-Reviewer.git
   cd AI-Powered-Code-Reviewer
   ```

2. **Backend Setup**
   ```bash
   cd Backend
   npm install
   ```
   
   Create a `.env` file in the Backend directory:
   ```env
   GOOGLE_GEMINI_KEY=your_gemini_api_key_here
   PORT=3000
   ```

3. **Frontend Setup**
   ```bash
   cd ../frontend
   npm install
   ```

### Running the Application

1. **Start the Backend Server**
   ```bash
   cd Backend
   npx nodemon
   ```
   Server runs on `http://localhost:3000`

2. **Start the Frontend Development Server**
   ```bash
   cd frontend
   npm run dev
   ```
   Frontend runs on `http://localhost:5173`

3. **Open your browser** and navigate to `http://localhost:5173`

## 🏗️ Architecture

### Frontend (React + Vite)
- **Components**: Code editor, review display, loading states
- **Technologies**: 
  - React with Hooks
  - CodeMirror for code editing
  - Axios for API communication
  - ReactMarkdown for rendering reviews
- **Location**: `frontend/src/`

### Backend (Node.js + Express)
- **API Routes**: RESTful endpoints for code review
- **Controllers**: Request handling and validation
- **Services**: AI integration and business logic
- **Technologies**:
  - Express.js framework
  - Google Generative AI SDK
  - CORS for cross-origin requests
- **Location**: `Backend/src/`

### AI Integration
- **Model**: Google Gemini `gemini-2.5-flash-lite`
- **Review Guidelines**: Custom system instructions for professional code review
- **Response Format**: Structured markdown with categorized feedback

## 📁 Project Structure

```
AI-Powered-Code-Reviewer/
├── frontend/
│   ├── src/
│   │   ├── App.jsx          # Main application component
│   │   ├── components/      # React components
│   │   └── utils/          # Utility functions
│   ├── package.json
│   └── vite.config.js
├── Backend/
│   ├── src/
│   │   ├── app.js          # Express application setup
│   │   ├── routes/
│   │   │   └── ai.routes.js # API route definitions
│   │   ├── controllers/
│   │   │   └── ai.controller.js # Request handlers
│   │   └── services/
│   │       └── ai.service.js # AI integration logic
│   ├── server.js           # Server entry point
│   ├── package.json
│   └── .env.example
└── README.md
```

## 🔧 API Endpoints

### POST `/ai/get-review`
Submit code for AI review

**Request Body:**
```json
{
  "code": "function example() { return 'hello world'; }"
}
```

**Response:**
```json
{
  "review": "## Code Review\n\n### Strengths\n- Clean function structure...\n\n### Improvements\n- Consider adding error handling...\n\n### Security\n- No apparent security issues..."
}
```

## 🎯 How It Works

1. **Code Submission**: User writes/pastes code in the web editor
2. **API Request**: Frontend sends code to backend via POST request
3. **AI Analysis**: Backend processes code through Gemini AI with custom review guidelines
4. **Review Generation**: AI provides comprehensive markdown-formatted feedback
5. **Result Display**: Frontend renders the review with proper formatting

## 🛠️ Customization

### Modifying Review Guidelines
Edit the system instructions in `Backend/src/services/ai.service.js`:

```javascript
const systemInstruction = `You are a senior code reviewer. Provide feedback on:
- Code quality and best practices
- Potential bugs and edge cases
- Performance optimizations
- Security concerns
- Alternative approaches
Format your response in markdown with clear sections.`;
```

### Adding Language Support
The AI model can review multiple languages. Update the frontend to support syntax highlighting for additional languages:

```javascript
// In frontend components
import { javascript } from '@codemirror/lang-javascript';
import { python } from '@codemirror/lang-python';
// Add more language support as needed
```

## 🤝 Contributing

We welcome contributions! Please feel free to submit pull requests, report bugs, or suggest new features.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 👨‍💻 Author

**Dhanush Saravanan**

- GitHub: [@Villwin007](https://github.com/Villwin007)
- Email: s.dhanush1106@gmail.com

## 🙏 Acknowledgments

- Google Gemini AI for powering the code reviews
- CodeMirror for the excellent code editor component
- React and Node.js communities for amazing tools and libraries

## 🔮 Future Enhancements

- [ ] Support for multiple programming languages
- [ ] Code review history and saving functionality
- [ ] Integration with GitHub repositories
- [ ] Custom review templates
- [ ] Batch code review capabilities
- [ ] CI/CD pipeline integration

---

**⭐ Star this repo if you found it helpful!**

For questions or support, please open an issue or contact [s.dhanush1106@gmail.com](mailto:s.dhanush1106@gmail.com).
