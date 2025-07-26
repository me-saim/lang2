# LinguaLink - Multilingual Messaging Platform

<div align="center">
  <img src="https://img.shields.io/badge/Version-1.0.0-blue.svg" alt="Version">
  <img src="https://img.shields.io/badge/License-MIT-green.svg" alt="License">
  <img src="https://img.shields.io/badge/Firebase-9.23.0-orange.svg" alt="Firebase">
  <img src="https://img.shields.io/badge/Tailwind-CSS-38B2AC.svg" alt="TailwindCSS">
</div>

## 🌍 Overview

LinguaLink is a modern, real-time multilingual messaging platform that breaks down language barriers by enabling seamless communication between users speaking different languages. Built with Firebase, WebSockets, and modern web technologies, it provides instant translation and real-time messaging capabilities.

### ✨ Key Features

- **Real-time Messaging** - Instant message delivery with WebSocket technology
- **Multilingual Support** - Built-in support for 8+ languages with automatic translation
- **User Authentication** - Secure sign-up/sign-in with Firebase Auth
- **Online Presence** - Real-time online/offline status tracking
- **Typing Indicators** - See when someone is typing
- **Message Status** - Delivery and read receipts
- **User Search** - Find and connect with users worldwide
- **Responsive Design** - Works seamlessly on desktop and mobile
- **Modern UI** - Beautiful gradient design with smooth animations

## 🚀 Live Demo

Access the application directly by opening the HTML file in your browser. No installation required!

## 🛠️ Technology Stack

- **Frontend**: HTML5, CSS3, JavaScript (ES6+)
- **Styling**: Tailwind CSS
- **Database**: Firebase Firestore
- **Authentication**: Firebase Auth
- **Real-time Communication**: WebSockets
- **Icons**: Font Awesome 6.0
- **Hosting**: Can be deployed to any static hosting service

## 📋 Prerequisites

Before running LinguaLink, ensure you have:

- A modern web browser (Chrome, Firefox, Safari, Edge)
- Internet connection for Firebase services
- Firebase project setup (see configuration section)

## ⚙️ Firebase Configuration

1. **Create a Firebase Project**
   - Go to [Firebase Console](https://console.firebase.google.com/)
   - Create a new project
   - Enable Authentication and Firestore

2. **Enable Authentication Providers**
   - Navigate to Authentication > Sign-in method
   - Enable Email/Password authentication
   - Optionally enable Google sign-in

3. **Configure Firestore Database**
   - Create a Firestore database
   - Set up the following collections:
     - `users` - User profiles and settings
     - `chats` - Chat metadata and participants
     - `chats/{chatId}/messages` - Individual chat messages

4. **Update Firebase Config**
   Replace the Firebase configuration in the HTML file:
   ```javascript
   const firebaseConfig = {
     apiKey: "your-api-key",
     authDomain: "your-project.firebaseapp.com",
     projectId: "your-project-id",
     storageBucket: "your-project.firebasestorage.app",
     messagingSenderId: "your-sender-id",
     appId: "your-app-id",
     measurementId: "your-measurement-id"
   };
   ```

## 🔧 Installation & Setup

1. **Clone or Download**
   ```bash
   git clone https://github.com/yourusername/lingualink.git
   cd lingualink
   ```

2. **Configure Firebase**
   - Update the Firebase configuration in the HTML file
   - Set up Firestore security rules

3. **Optional: WebSocket Server**
   - The app uses a demo WebSocket server by default
   - For production, set up your own WebSocket server
   - Update the `wsUrl` variable in the settings

4. **Open the Application**
   - Simply open `index.html` in your web browser
   - Or serve it using a local server:
     ```bash
     python -m http.server 8000
     # Then visit http://localhost:8000
     ```

## 📖 Usage Guide

### Getting Started

1. **Sign Up/Sign In**
   - Create a new account with email and password
   - Choose your preferred language
   - Or sign in with existing credentials

2. **Find Users**
   - Use the search bar to find other users
   - Click on a user to start a conversation

3. **Messaging**
   - Type your message in the input field
   - Press Enter or click send
   - Messages are automatically translated based on recipient's language preference

4. **Settings**
   - Click the settings icon to update your profile
   - Change language preferences
   - Update display name

### Features Overview

#### Real-time Communication
- Messages appear instantly for all participants
- Typing indicators show when someone is composing
- Online/offline status is updated in real-time

#### Multilingual Support
Languages supported:
- English
- Hindi (हिन्दी)
- Spanish (Español)
- French (Français)
- German (Deutsch)
- Chinese (中文)
- Japanese (日本語)
- Arabic (العربية)

#### Message Status
- ⏰ Sending
- ✓ Sent
- ✓✓ Delivered
- ✓✓ Read (blue checkmarks)

## 🏗️ Project Structure

```
lingualink/
├── index.html              # Main application file
├── README.md              # Project documentation
├── screenshots/           # Application screenshots
└── docs/                 # Additional documentation
```

## 🔐 Security Features

- **Firebase Authentication** - Secure user authentication
- **Firestore Security Rules** - Database access control
- **Input Validation** - Client-side input sanitization
- **WebSocket Security** - Secure WebSocket connections

## 🎨 Customization

### Themes and Colors
The app uses CSS custom properties for easy theming:
```css
:root {
  --primary-gradient: linear-gradient(45deg, #667eea 0%, #764ba2 100%);
  --secondary-gradient: linear-gradient(45deg, #f093fb 0%, #f5576c 100%);
}
```

### Adding Languages
To add new languages:
1. Update the `languageNames` object
2. Add language options to select elements
3. Implement translation service integration

### WebSocket Server
For production deployment, implement your own WebSocket server with:
- User authentication
- Message routing
- Presence management
- Message persistence

## 🚀 Deployment

### Static Hosting (Recommended)
Deploy to any static hosting service:

**Netlify:**
1. Drag and drop the HTML file to Netlify
2. Configure custom domain if needed

**Vercel:**
```bash
npx vercel --prod
```

**GitHub Pages:**
1. Push to GitHub repository
2. Enable GitHub Pages in repository settings

**Firebase Hosting:**
```bash
npm install -g firebase-tools
firebase init hosting
firebase deploy
```

## 🧪 Testing

### Manual Testing Checklist
- [ ] User registration and login
- [ ] Sending and receiving messages
- [ ] Real-time message delivery
- [ ] Typing indicators
- [ ] Online/offline status
- [ ] Search functionality
- [ ] Settings updates
- [ ] Mobile responsiveness

### Browser Compatibility
- ✅ Chrome 80+
- ✅ Firefox 75+
- ✅ Safari 13+
- ✅ Edge 80+

## 🤝 Contributing

We welcome contributions! Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

### Development Guidelines
- Follow existing code style and conventions
- Add comments for complex functionality
- Test thoroughly across different browsers
- Update documentation as needed

## 📝 API Reference

### WebSocket Message Types

```javascript
// Authentication
{
  type: 'auth',
  userId: 'user-id',
  userData: { name: 'User Name', language: 'en' }
}

// Send Message
{
  type: 'message',
  chatId: 'chat-id',
  message: { /* message object */ },
  recipientId: 'recipient-id'  
}

// Typing Indicator
{
  type: 'typing',
  chatId: 'chat-id',
  userId: 'user-id',
  userName: 'User Name',
  isTyping: true/false
}
```

### Firestore Collections

#### Users Collection
```javascript
{
  name: "User Name",
  email: "user@example.com", 
  language: "en",
  online: true,
  createdAt: timestamp,
  lastSeen: timestamp
}
```

#### Chats Collection
```javascript
{
  participants: ["userId1", "userId2"],
  lastMessage: "Hello world",
  lastMessageTime: timestamp,
  unreadCounts: {
    "userId1": 0,
    "userId2": 2
  }
}
```

## 🐛 Troubleshooting

### Common Issues

**WebSocket Connection Failed**
- Check if the WebSocket URL is accessible
- Verify firewall settings
- Try using the demo server: `wss://echo.websocket.org`

**Firebase Authentication Error**
- Verify Firebase configuration
- Check if authentication is enabled in Firebase Console
- Ensure correct API keys

**Messages Not Sending**
- Check internet connection
- Verify Firestore permissions
- Check browser console for errors

**App Not Loading**
- Ensure all CDN resources are accessible
- Check browser compatibility
- Clear browser cache and cookies

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Credits

- **Firebase** - Backend services and authentication
- **Tailwind CSS** - UI styling framework
- **Font Awesome** - Icons and symbols
- **WebSocket API** - Real-time communication

## 📞 Support

For support and questions:
- 📧 Email: support@lingualink.com
- 💬 Discord: [LinguaLink Community](https://discord.gg/lingualink)
- 🐛 Issues: [GitHub Issues](https://github.com/yourusername/lingualink/issues)

## 🔮 Roadmap

### Upcoming Features
- [ ] Voice messages
- [ ] File sharing
- [ ] Group chats
- [ ] Message encryption
- [ ] Push notifications
- [ ] Desktop application
- [ ] Mobile app (React Native)
- [ ] Advanced translation options
- [ ] Message search
- [ ] Chat themes

---

<div align="center">
  <p>Made with ❤️ for global communication</p>
  <p>🌍 Connect Languages, Connect Hearts 🌍</p>
</div>
