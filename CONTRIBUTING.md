# Contributing to Smart Task Manager

Thank you for your interest in contributing to Smart Task Manager! This document provides guidelines and information for contributors.

## 🚀 Getting Started

### Prerequisites
- Node.js 18+ 
- npm 8+
- Git
- Modern web browser with notification support

### Development Setup

1. **Fork and Clone**
```bash
git clone https://github.com/yourusername/smart-task-manager.git
cd smart-task-manager
```

2. **Install Dependencies**
```bash
npm install
```

3. **Start Development Server**
```bash
npm run dev
```

4. **Open Browser**
Navigate to `http://localhost:5173`

## 📁 Project Structure

```
src/
├── components/          # React components
│   ├── TaskInput.tsx    # AI-powered task creation
│   ├── TaskCard.tsx     # Individual task display
│   ├── TaskList.tsx     # Task collection display
│   ├── StatsCard.tsx    # Analytics dashboard
│   ├── TabNavigation.tsx # Status filtering
│   ├── ToastContainer.tsx # In-app notifications
│   └── NotificationSettings.tsx # Notification config
├── hooks/               # Custom React hooks
│   ├── useTasks.ts      # Task management logic
│   └── useToast.ts      # Toast notification system
├── services/            # Business logic services
│   ├── aiParser.ts      # Natural language processing
│   ├── taskService.ts   # Task CRUD operations
│   └── notificationService.ts # Web notifications
├── types/               # TypeScript definitions
│   └── index.ts         # Core type definitions
└── App.tsx              # Main application component
```

## 🎯 Development Guidelines

### Code Style
- Use TypeScript for all new code
- Follow React Hooks patterns
- Maintain component modularity (< 200 lines per file)
- Use Tailwind CSS for styling
- Follow ESLint configuration

### Component Guidelines
```typescript
// Good: Functional component with TypeScript
interface TaskCardProps {
  task: Task;
  onStatusChange: (id: string, status: TaskStatus) => void;
}

export function TaskCard({ task, onStatusChange }: TaskCardProps) {
  // Component logic here
}

// Use proper prop types and meaningful names
// Keep components focused on single responsibility
// Extract complex logic into custom hooks
```

### Service Layer Guidelines
```typescript
// Good: Service class with proper error handling
export class TaskService {
  private static STORAGE_KEY = 'smart-tasks';
  
  getAllTasks(): Task[] {
    try {
      const stored = localStorage.getItem(TaskService.STORAGE_KEY);
      return stored ? JSON.parse(stored) : [];
    } catch (error) {
      console.error('Failed to load tasks:', error);
      return [];
    }
  }
}
```

## 🧪 Testing

### Manual Testing Checklist
- [ ] Natural language task creation works with various inputs
- [ ] Priority detection (urgent, important, ASAP, critical)
- [ ] Deadline parsing (today, tomorrow, specific times)
- [ ] Status transitions (pending → in-progress → completed)
- [ ] Notification permissions and display
- [ ] Responsive design on mobile/tablet/desktop
- [ ] Voice input functionality (Chrome/Safari)
- [ ] Offline functionality and PWA features
- [ ] Accessibility with screen readers

### Test Cases for AI Parser
```typescript
// Test natural language inputs
const testCases = [
  {
    input: "Remind me to call dentist tomorrow at 2 PM - urgent",
    expected: {
      title: "Call dentist",
      priority: "high",
      deadline: /* tomorrow at 2 PM */
    }
  },
  {
    input: "Buy groceries this weekend",
    expected: {
      title: "Buy groceries", 
      priority: "medium",
      deadline: /* this weekend */
    }
  }
];
```

## 📱 Browser Support

### Minimum Requirements
- **Chrome**: 90+
- **Firefox**: 88+
- **Safari**: 14+
- **Edge**: 90+

### Progressive Enhancement
- Basic functionality works without notifications
- Voice input gracefully degrades
- PWA features enhance experience but aren't required

## 🔧 Feature Development

### Adding New Features

1. **Create Feature Branch**
```bash
git checkout -b feature/your-feature-name
```

2. **Implement Feature**
- Add TypeScript types first
- Implement service layer logic
- Create/update components
- Add error handling

3. **Test Thoroughly**
- Manual testing across browsers
- Edge cases and error scenarios
- Responsive design verification

4. **Submit Pull Request**
- Clear description of changes
- Screenshots/videos if UI changes
- Link to any related issues

### AI Parser Enhancements

When extending the AI parser:

```typescript
// Add new keywords to detection arrays
private static urgencyKeywords = {
  high: ['urgent', 'asap', 'critical', 'important', 'emergency'],
  medium: ['soon', 'today', 'tomorrow'],
  low: ['eventually', 'sometime', 'later']
};

// Add new time parsing patterns
private static timeKeywords = {
  'end of day': () => {
    const date = new Date();
    date.setHours(17, 0, 0, 0); // 5 PM
    return date;
  }
};
```

### Notification System Extensions

```typescript
// Add new notification types
showCustomNotification(type: 'deadline' | 'reminder' | 'celebration', task: Task): void {
  const configs = {
    deadline: {
      title: '⏰ Deadline Approaching!',
      body: `"${task.title}" is due soon`,
      requireInteraction: true
    },
    celebration: {
      title: '🎉 Great Job!',
      body: `"${task.title}" completed!`,
      requireInteraction: false
    }
  };
  
  this.showNotification(configs[type]);
}
```

## 🎨 UI/UX Guidelines

### Design System
- **Primary Colors**: Blue (#3B82F6) to Purple (#7C3AED) gradients
- **Spacing**: 8px base unit system
- **Typography**: Inter font family
- **Animations**: Smooth 200-300ms transitions
- **Glass Morphism**: backdrop-blur-sm with transparent backgrounds

### Accessibility Requirements
- Proper ARIA labels for all interactive elements
- Keyboard navigation support
- High contrast color ratios (4.5:1 minimum)
- Screen reader compatibility
- Focus indicators for all focusable elements

```jsx
// Good: Accessible button
<button
  aria-label="Mark task as completed"
  className="p-2 bg-green-500 rounded-lg focus:ring-2 focus:ring-green-300"
  onClick={() => onStatusChange(task.id, 'completed')}
>
  <Check className="w-4 h-4" />
</button>
```

## 📦 Build and Deployment

### Production Build
```bash
npm run build
npm run preview  # Test production build locally
```

### Deployment Checklist
- [ ] Build completes without errors
- [ ] All assets load correctly
- [ ] Service worker registers successfully
- [ ] Notifications work in production
- [ ] PWA install prompt appears
- [ ] Responsive design verified

## 🐛 Bug Reports

When reporting bugs, please include:

1. **Environment**
   - Browser and version
   - Operating system
   - Screen resolution (for UI bugs)

2. **Steps to Reproduce**
   - Detailed step-by-step instructions
   - Expected vs actual behavior
   - Screenshots/videos if applicable

3. **Console Errors**
   - Browser console output
   - Network tab errors
   - Service worker issues

## 🤝 Pull Request Process

1. **Before Submitting**
   - Ensure code follows style guidelines
   - Test on multiple browsers
   - Update documentation if needed
   - Verify no breaking changes

2. **PR Description Template**
   ```markdown
   ## Summary
   Brief description of changes
   
   ## Changes Made
   - Feature 1
   - Bug fix 2
   - Enhancement 3
   
   ## Testing
   - [ ] Manual testing completed
   - [ ] Cross-browser verification
   - [ ] Mobile testing done
   
   ## Screenshots
   (If UI changes)
   ```

3. **Review Process**
   - Code review by maintainers
   - Automated checks must pass
   - Manual testing by reviewers
   - Approval required before merge

## 🏆 Recognition

Contributors will be recognized in:
- README.md contributors section
- Release notes for significant contributions
- GitHub contributor graph

## 📞 Getting Help

- **Questions**: Open a GitHub Discussion
- **Bugs**: Create a GitHub Issue
- **Features**: Open a Feature Request issue
- **Security**: Email security@taskmanager.com

## 📄 License

By contributing, you agree that your contributions will be licensed under the MIT License.

---

Thank you for helping make Smart Task Manager better! 🚀