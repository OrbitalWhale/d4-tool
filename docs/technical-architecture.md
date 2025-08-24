# Technical Architecture - Diablo 4 Build Tool

## Electron Application Architecture

### Process Model
```
┌─────────────────────────────────────────────────────────────┐
│                    Main Process                            │
│  ┌─────────────────┐  ┌─────────────────┐  ┌─────────────┐ │
│  │   App Lifecycle │  │  File System    │  │   Native    │ │
│  │   Management    │  │   Operations    │  │    APIs     │ │
│  └─────────────────┘  └─────────────────┘  └─────────────┘ │
└─────────────────────────────────────────────────────────────┘
                              │
                    ┌─────────┴─────────┐
                    │     IPC Bridge    │
                    └─────────┬─────────┘
                              │
┌─────────────────────────────────────────────────────────────┐
│                  Renderer Process                          │
│  ┌─────────────────┐  ┌─────────────────┐  ┌─────────────┐ │
│  │   UI Components │  │   Data Display  │  │   User      │ │
│  │   & Rendering   │  │   & Management  │  │  Interactions│ │
│  └─────────────────┘  └─────────────────┘  └─────────────┘ │
└─────────────────────────────────────────────────────────────┘
```

### Main Process Responsibilities
- Application lifecycle management (startup, shutdown, updates)
- File system operations (JSON data loading, build saving)
- Native API integration (system dialogs, file associations)
- Security and permissions management
- IPC message handling and routing

### Renderer Process Responsibilities
- User interface rendering and updates
- User input handling and validation
- Data visualization and manipulation
- Local state management
- IPC communication with main process

## Data Flow Architecture

### JSON Data Processing Pipeline
```
JSON File → Parser → Validator → Cache → UI Components
    ↓           ↓        ↓        ↓         ↓
  Raw Data → Parsed → Validated → Cached → Displayed
```

### Build Data Management
```
User Input → Validation → Processing → Storage → Export
    ↓           ↓           ↓          ↓        ↓
  Build Data → Rules → Calculations → Local → Formats
```

## Component Architecture

### Core Components Structure
```
App
├── Navigation
│   ├── Sidebar
│   └── TopBar
├── Main Content
│   ├── Build Creator
│   │   ├── Class Selector
│   │   ├── Skill Tree
│   │   └── Equipment Manager
│   ├── Build Manager
│   │   ├── Build List
│   │   ├── Build Editor
│   │   └── Build Comparison
│   └── Settings
└── Modals & Overlays
    ├── Build Export
    ├── Import Dialog
    └── Help/About
```

### Data Models

#### Character Class
```typescript
interface CharacterClass {
  id: string;
  name: string;
  description: string;
  baseStats: BaseStats;
  skillTrees: SkillTree[];
  availableEquipment: EquipmentSlot[];
}
```

#### Skill Tree
```typescript
interface SkillTree {
  id: string;
  name: string;
  description: string;
  skills: Skill[];
  requirements: SkillRequirement[];
  maxPoints: number;
}
```

#### Build
```typescript
interface Build {
  id: string;
  name: string;
  characterClass: string;
  skillPoints: SkillPoint[];
  equipment: Equipment[];
  stats: CalculatedStats;
  metadata: BuildMetadata;
}
```

## State Management

### Application State
- **Global State**: User preferences, app settings, current build
- **Component State**: UI component-specific state
- **Data State**: Parsed JSON data, cached information
- **Build State**: Current build being edited, unsaved changes

### State Persistence
- **User Preferences**: Electron store for app settings
- **Build Data**: Local file system with JSON format
- **Cache**: In-memory with periodic persistence
- **Temporary Data**: Session storage for unsaved work

## Performance Considerations

### Data Loading Strategy
- **Lazy Loading**: Load data only when needed
- **Caching**: Cache parsed JSON data in memory
- **Background Processing**: Parse large files in background
- **Progressive Loading**: Load UI components progressively

### Memory Management
- **Data Cleanup**: Remove unused data from memory
- **Component Recycling**: Reuse UI components when possible
- **Garbage Collection**: Monitor and optimize memory usage
- **Resource Limits**: Set reasonable limits for data size

## Security Considerations

### IPC Communication
- **Message Validation**: Validate all IPC messages
- **Input Sanitization**: Sanitize user inputs
- **Permission Checks**: Verify file system access permissions
- **Error Handling**: Secure error messages (no sensitive data)

### File System Security
- **Path Validation**: Validate file paths before access
- **Sandboxing**: Limit file access to necessary directories
- **Input Validation**: Validate all file content before processing
- **Safe Defaults**: Use safe defaults for file operations

## Build and Distribution

### Development Environment
- **Hot Reload**: Fast development iteration
- **Debug Tools**: Integrated debugging for both processes
- **Error Reporting**: Comprehensive error logging
- **Performance Monitoring**: Monitor app performance during development

### Production Build
- **Code Minification**: Minimize bundle size
- **Asset Optimization**: Optimize images and other assets
- **Tree Shaking**: Remove unused code
- **Platform Targeting**: Build for specific platforms

### Distribution
- **Auto-updater**: Handle application updates
- **Code Signing**: Sign application for distribution
- **Installation**: Create installers for target platforms
- **Update Channels**: Manage different update channels

## Testing Strategy

### Unit Testing
- **Data Parsing**: Test JSON parser with various data formats
- **Business Logic**: Test build calculations and validations
- **Utility Functions**: Test helper functions and utilities

### Integration Testing
- **IPC Communication**: Test main-renderer process communication
- **File Operations**: Test file loading and saving
- **Data Flow**: Test complete data processing pipelines

### UI Testing
- **Component Rendering**: Test UI component rendering
- **User Interactions**: Test user input and interactions
- **Responsiveness**: Test UI responsiveness and performance

### End-to-End Testing
- **Complete Workflows**: Test complete user workflows
- **Cross-Platform**: Test on different operating systems
- **Performance**: Test performance under various conditions

## Monitoring and Debugging

### Development Tools
- **DevTools**: Chrome DevTools for renderer process
- **Main Process Debugging**: Node.js debugging tools
- **Performance Profiling**: Built-in performance monitoring
- **Error Tracking**: Comprehensive error logging

### Production Monitoring
- **Crash Reporting**: Collect crash reports from users
- **Performance Metrics**: Monitor app performance
- **Usage Analytics**: Track feature usage (privacy-conscious)
- **Error Logging**: Log errors for debugging

---

*This document will be updated as we implement features and learn more about the specific requirements.*
