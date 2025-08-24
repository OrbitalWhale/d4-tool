# Diablo 4 Build Tool

A desktop application built with Electron to help Diablo 4 players create, manage, and share character builds. The tool parses JSON data containing game information and provides an intuitive UI for build creation and management.

## 🎯 Features

- **Build Creator**: Create and customize character builds with skill trees and equipment
- **Build Manager**: Save, load, and organize your builds locally
- **Data Parser**: Efficiently parse and validate Diablo 4 game data from JSON files
- **Modern UI**: Clean, responsive interface with dark theme support
- **Cross-Platform**: Works on Windows, macOS, and Linux

## 🚀 Getting Started

### Prerequisites

- Node.js (v16 or higher)
- npm or yarn

### Installation

1. Clone the repository
```bash
git clone https://github.com/orbitalwhale/d4-tool.git
cd d4-tool
```

2. Install dependencies
```bash
npm install
```

3. Start the development server
```bash
npm run dev
```

4. For production build
```bash
npm run build
npm start
```

## 🛠️ Development

### Project Structure

```
d4-tool/
├── docs/                    # Documentation
├── src/                     # Source code
│   ├── main/               # Main process (Electron)
│   ├── renderer/           # Renderer process (UI)
│   └── shared/             # Shared utilities
├── assets/                  # Static assets
├── data/                    # JSON data files
├── dist/                    # Build output
└── package.json
```

### Available Scripts

- `npm start` - Launch the Electron application
- `npm run dev` - Start development mode with hot reload
- `npm run build` - Build the application
- `npm run dist` - Create distribution packages
- `npm test` - Run tests (when implemented)

### Technology Stack

- **Frontend**: HTML, CSS, JavaScript/TypeScript
- **Desktop Framework**: Electron
- **Build Tool**: npm/yarn
- **Data Format**: JSON

## 📚 Documentation

- [Project Plan](./docs/project-plan.md) - High-level project overview and planning
- [Technical Architecture](./docs/technical-architecture.md) - Detailed technical implementation
- [Development Roadmap](./docs/development-roadmap.md) - 12-week development plan
- [Quick Start Guide](./docs/quick-start-guide.md) - Get up and running quickly
- [Team Collaboration Guide](./docs/team-collaboration-guide.md) - Team workflow and best practices
- [Team Onboarding Checklist](./docs/team-onboarding-checklist.md) - New team member setup
- [GitHub Setup Guide](./docs/github-setup-guide.md) - Repository configuration

## 🤝 Contributing

We welcome contributions! Please see our [Contributing Guidelines](./CONTRIBUTING.md) for details.

### Team Collaboration

This project is designed for team development. See our [Team Collaboration Guide](./docs/team-collaboration-guide.md) for detailed workflow and best practices.

### Development Workflow

1. Fork the repository (for external contributors)
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request
6. Get code review from team members
7. Merge after approval

## 📋 Roadmap

This project is currently in active development. See our [Development Roadmap](./docs/development-roadmap.md) for current progress and upcoming features.

### Current Phase
- **Phase 1**: Project Foundation and Environment Setup

### Upcoming Features
- JSON data parsing and validation
- Character class selection interface
- Interactive skill tree visualization
- Equipment management system
- Build saving and loading
- Export and sharing capabilities

## 🐛 Issues

Found a bug or have a feature request? Please [open an issue](../../issues) and we'll get back to you as soon as possible.

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- Built with [Electron](https://www.electronjs.org/)
- Inspired by the Diablo 4 community
- Special thanks to all contributors and testers

## 📞 Support

- **GitHub Issues**: [Report bugs or request features](../../issues)
- **Discussions**: [Join the community discussion](../../discussions)
- **Wiki**: [Check our wiki](../../wiki) for additional documentation

---

**Note**: This tool is not affiliated with Blizzard Entertainment or Diablo 4. It's a community-created utility for educational and personal use.

**Made with ❤️ by the Diablo 4 community**
