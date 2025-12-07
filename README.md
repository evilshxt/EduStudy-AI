# EduStudy AI

An intelligent educational platform that combines interactive learning experiences with AI-powered conversational assistance. Built with modern web technologies to provide personalized education through lessons, quizzes, and real-time chat support.

## 🚀 Features

### Core Learning Features
- **Interactive Lessons**: Dynamic, engaging educational content with multimedia support
- **Smart Quizzes**: Adaptive assessment system with instant feedback
- **Progress Tracking**: Comprehensive learning analytics and progress monitoring
- **Personalized Learning Paths**: AI-driven recommendations based on user performance

### AI-Powered Chat System
- **Voiceflow Integration**: Advanced conversational AI for educational support
- **Real-time Responses**: Instant answers to learning queries
- **Context-Aware Conversations**: Maintains conversation history and learning context
- **Multi-modal Interactions**: Support for text, quizzes, and interactive dialogues

### User Experience
- **Responsive Design**: Optimized for desktop and mobile devices
- **Dark/Light Theme**: Customizable interface with theme persistence
- **Real-time Notifications**: Live updates and typing indicators
- **Secure Authentication**: Firebase-powered user management

## 🛠️ Tech Stack

### Frontend
- **React 19** - Modern React with concurrent features
- **TypeScript** - Type-safe development
- **Vite** - Fast build tool and dev server
- **Tailwind CSS** - Utility-first CSS framework
- **Lucide React** - Beautiful icon library

### State Management
- **Redux Toolkit** - Efficient state management
- **React Redux** - Official React bindings

### Backend & Services
- **Firebase** - Authentication, Firestore database, and hosting
- **Voiceflow** - AI conversation platform

### Development Tools
- **ESLint** - Code linting and formatting
- **TypeScript** - Type checking
- **Vite** - Development server and build tool

## 📋 Prerequisites

- Node.js (v18 or higher)
- npm or yarn
- Firebase project with authentication and Firestore enabled
- Voiceflow account with published project

## 🚀 Installation

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd edustudy-ai
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Environment Setup**
   Create a `.env` file in the root directory with the following variables:
   ```env
   # Firebase Configuration
   VITE_FIREBASE_API_KEY=your_firebase_api_key
   VITE_FIREBASE_AUTH_DOMAIN=your_project.firebaseapp.com
   VITE_FIREBASE_PROJECT_ID=your_project_id
   VITE_FIREBASE_STORAGE_BUCKET=your_project.appspot.com
   VITE_FIREBASE_MESSAGING_SENDER_ID=your_sender_id
   VITE_FIREBASE_APP_ID=your_app_id

   # Voiceflow Configuration
   VITE_VOICEFLOW_API_KEY=your_voiceflow_api_key
   VITE_VOICEFLOW_VERSION_ID=production
   ```

4. **Firebase Setup**
   - Create a Firebase project at [Firebase Console](https://console.firebase.google.com/)
   - Enable Authentication with Email/Password provider
   - Enable Firestore Database
   - Copy your Firebase config to the `.env` file

5. **Voiceflow Setup**
   - Create a Voiceflow account at [Voiceflow](https://www.voiceflow.com/)
   - Create and publish your conversational AI project
   - Generate a Runtime API key
   - Add the API key and version ID to `.env`

## 🏃‍♂️ Running the Application

### Development
```bash
npm run dev
```
Starts the development server at `http://localhost:5173`

### Production Build
```bash
npm run build
```
Builds the application for production in the `dist` directory

### Preview Production Build
```bash
npm run preview
```
Serves the production build locally for testing

## 📁 Project Structure

```
src/
├── components/          # Reusable UI components
│   ├── ChatWindow.tsx   # Main chat interface
│   ├── MessageInput.tsx # Message input component
│   ├── QuizComponent.tsx # Quiz display component
│   └── ...
├── pages/              # Page components
│   └── Chat.tsx        # Main chat page
├── services/           # External service integrations
│   ├── authService.ts  # Firebase authentication
│   ├── chatService.ts  # Chat data management
│   └── voiceflowService.ts # Voiceflow AI integration
├── store/              # Redux state management
│   ├── authSlice.ts    # Authentication state
│   ├── index.ts        # Store configuration
│   └── progressSlice.ts # Learning progress state
├── types/              # TypeScript type definitions
│   ├── auth.ts         # Authentication types
│   ├── chat.ts         # Chat and message types
│   └── progress.ts     # Progress tracking types
├── utils/              # Utility functions
└── firebase.ts         # Firebase configuration
```

## 🎯 Usage

### User Registration & Login
1. Navigate to the application
2. Create an account or sign in with existing credentials
3. Access the chat interface for AI-powered learning assistance

### Learning Experience
1. **Start a Conversation**: Begin chatting with the AI tutor
2. **Access Lessons**: Request specific educational content
3. **Take Quizzes**: Engage with interactive assessments
4. **Track Progress**: Monitor your learning journey

### Chat Features
- Send messages using the input field or Enter key
- View conversation history in the sidebar
- Switch between light and dark themes
- Real-time typing indicators

## 🔧 Configuration

### Firebase Security Rules
Ensure your Firestore security rules allow authenticated users to read/write their data:

```javascript
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    match /chats/{chatId} {
      allow read, write: if request.auth != null && resource.data.userId == request.auth.uid;
    }
  }
}
```

### Voiceflow Project Setup
1. Design your conversational flow in Voiceflow
2. Publish your project to create the 'production' version
3. Ensure your flow handles text, quiz, and lesson interactions
4. Test the API endpoints before deployment

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

### Development Guidelines
- Follow TypeScript best practices
- Write meaningful commit messages
- Test your changes thoroughly
- Update documentation as needed

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙋‍♂️ Support

For support, please:
- Check the [Issues](https://github.com/your-repo/issues) page
- Review the documentation
- Contact the development team

## 🚀 Future Enhancements

- [ ] Mobile application (React Native)
- [ ] Advanced analytics dashboard
- [ ] Multi-language support
- [ ] Voice input/output capabilities
- [ ] Collaborative learning features
- [ ] Integration with additional AI providers

---

Built with ❤️ using React, TypeScript, and modern web technologies.
