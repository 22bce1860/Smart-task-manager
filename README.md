# Smart Task Manager 🧠

A beautiful, AI-powered task management application with natural language processing capabilities. Create, organize, and track your tasks using intelligent assistance and modern web technologies.

![Smart Task Manager](https://images.pexels.com/photos/3183150/pexels-photo-3183150.jpeg)

## ✨ Features

### 🧠 AI-Powered Natural Language Processing
- Create tasks using natural language like "Remind me to call dentist tomorrow at 2 PM - urgent"
- Intelligent parsing of priority levels, deadlines, and descriptions
- Smart detection of urgency indicators and time expressions

### 📋 Complete Task Management
- Full CRUD operations for tasks
- Status workflow: Pending → In Progress → Completed
- Priority levels: Low, Medium, High
- Real-time statistics and completion tracking
- Task filtering by status with intuitive tabs

### 🔔 Advanced Notification System
- **Web Notifications**: Browser notifications for task events
- **Toast Notifications**: In-app feedback for user actions
- **Smart Reminders**: Automatic deadline notifications (1 hour before due)
- **Notification Settings**: Customizable notification preferences

### 🎨 Modern UI/UX
- **Glass Morphism Design**: Beautiful translucent elements with backdrop blur
- **Responsive Layout**: Works perfectly on desktop, tablet, and mobile
- **Smooth Animations**: Micro-interactions and hover effects
- **Professional Typography**: Inter font with proper hierarchy
- **Real-time Updates**: Instant feedback and state management

### ⚡ Performance & PWA Features
- **Service Worker**: Offline caching and background sync
- **Progressive Web App**: Installable on devices
- **Fast Loading**: Optimized assets and lazy loading
- **Accessibility**: WCAG compliant with proper ARIA labels

## 🚀 Getting Started

### Prerequisites
- Node.js 16+ 
- npm or yarn

### Installation

1. **Clone the repository**
```bash
git clone https://github.com/yourusername/smart-task-manager.git
cd smart-task-manager
```

2. **Install dependencies**
```bash
npm install
```

3. **Start development server**
```bash
npm run dev
```

4. **Open your browser**
Navigate to `http://localhost:5173`

### Building for Production

```bash
npm run build
npm run preview
```

## 🏗️ Architecture

### Frontend Stack
- **React 18** - Modern React with hooks and concurrent features
- **TypeScript** - Type-safe development
- **Tailwind CSS** - Utility-first styling
- **Vite** - Fast build tool and dev server
- **Lucide React** - Beautiful SVG icons

### Core Services
- **AITaskParser** - Simulated LLM for natural language processing
- **TaskService** - Task CRUD operations and data management
- **NotificationService** - Web notifications and permission handling
- **Local Storage** - Client-side data persistence

### Key Components
- **TaskInput** - AI-powered task creation with voice input
- **TaskCard** - Individual task display with status management
- **StatsCard** - Real-time analytics and progress tracking
- **ToastContainer** - In-app notification system
- **NotificationSettings** - Notification preference management

## 🎯 Usage Examples

### Creating Tasks with Natural Language

```
"Remind me to call dentist tomorrow at 2 PM - urgent"
→ Creates: High priority task due tomorrow at 2 PM

"Buy groceries this weekend"  
→ Creates: Medium priority task due this weekend

"Finish project report by Friday - important"
→ Creates: High priority task due Friday

"Schedule team meeting for next week"
→ Creates: Medium priority task due next week
```

### Task Management Workflow

1. **Create** - Use natural language input
2. **Start** - Change status from Pending to In Progress  
3. **Complete** - Mark task as completed
4. **Track** - Monitor progress with real-time stats

## 🔧 Configuration

### Notification Settings
- Enable/disable browser notifications
- Test notification functionality
- Automatic deadline reminders
- Completion celebrations

### Customization
- Modify priority detection keywords in `aiParser.ts`
- Adjust deadline parsing patterns
- Customize notification timing in `taskService.ts`
- Update UI colors in Tailwind config

## 📱 Progressive Web App

The app includes PWA features:
- **Installable**: Add to home screen on mobile/desktop
- **Offline Support**: Works without internet connection
- **Background Sync**: Syncs data when connection restored
- **Push Notifications**: Server-sent notifications (configurable)

## 🎨 Design System

### Color Palette
- **Primary**: Blue (#3B82F6) to Purple (#7C3AED) gradient
- **Secondary**: Teal (#14B8A6) 
- **Accent**: Orange (#F97316)
- **Success**: Green (#22C55E)
- **Warning**: Yellow (#EAB308)
- **Error**: Red (#EF4444)

### Typography
- **Font**: Inter (400, 500, 600, 700 weights)
- **Scale**: Consistent 8px spacing system
- **Hierarchy**: Clear visual hierarchy with proper contrast

## 🧪 Testing

### Manual Testing Checklist
- [ ] Natural language task creation
- [ ] Priority detection (urgent, important, ASAP)
- [ ] Deadline parsing (today, tomorrow, specific times)
- [ ] Status transitions (pending → in-progress → completed)
- [ ] Notification permissions and functionality
- [ ] Responsive design on different screen sizes
- [ ] Voice input (if supported by browser)
- [ ] Offline functionality
- [ ] PWA installation

### Browser Support
- Chrome 90+
- Firefox 88+
- Safari 14+
- Edge 90+

## 🚀 Deployment

### GitHub Pages
```bash
npm run build
# Deploy dist/ folder to GitHub Pages
```

### Netlify/Vercel
```bash
# Build command: npm run build
# Publish directory: dist
```

### Docker
```dockerfile
FROM node:18-alpine
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
RUN npm run build
EXPOSE 3000
CMD ["npm", "run", "preview"]
```

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

### Development Guidelines
- Follow TypeScript best practices
- Maintain component modularity (max 200 lines per file)
- Use meaningful commit messages
- Add proper error handling
- Test on multiple browsers

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- **Lucide Icons** - Beautiful icon set
- **Pexels** - Stock photos for documentation
- **Inter Font** - Professional typography
- **Tailwind CSS** - Utility-first styling system

## 🔮 Future Enhancements

- [ ] Real LLM integration (OpenAI, Claude, etc.)
- [ ] Cloud synchronization with backend
- [ ] Collaboration features
- [ ] Advanced analytics dashboard
- [ ] Calendar integration
- [ ] Recurring tasks
- [ ] Team workspaces
- [ ] Dark mode theme
- [ ] Export/import functionality
- [ ] Voice commands for task management

---

**Made with ❤️ by [Your Name]**

⭐ If you found this project helpful, please give it a star on GitHub!