# Contributing to Diablo 4 Build Tool

Thank you for your interest in contributing to the Diablo 4 Build Tool! This document provides guidelines and information for contributors.

## 🤝 How to Contribute

### Types of Contributions

We welcome various types of contributions:

- **Bug Reports**: Report bugs or issues you encounter
- **Feature Requests**: Suggest new features or improvements
- **Code Contributions**: Submit code changes, improvements, or new features
- **Documentation**: Improve or add documentation
- **Testing**: Help test the application and report issues
- **Design**: Contribute to UI/UX improvements
- **Community**: Help other users and contribute to discussions

### Before You Start

1. **Check existing issues**: Look for existing issues or discussions about your idea
2. **Read the documentation**: Familiarize yourself with the project structure and goals
3. **Join discussions**: Participate in GitHub Discussions to understand community needs

## 🚀 Development Setup

### Prerequisites

- Node.js (v16 or higher)
- npm or yarn
- Git
- A code editor (VS Code recommended)

### Local Development Setup

1. **Fork the repository**
   ```bash
   # Fork on GitHub, then clone your fork
   git clone https://github.com/yourusername/d4-tool.git
   cd d4-tool
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Set up development environment**
   ```bash
   npm run dev
   ```

4. **Create a feature branch**
   ```bash
   git checkout -b feature/your-feature-name
   ```

## 📝 Development Guidelines

### Code Style

- **JavaScript/TypeScript**: Follow modern ES6+ practices
- **HTML**: Use semantic HTML5 elements
- **CSS**: Follow BEM methodology for class naming
- **Comments**: Add clear, helpful comments for complex logic
- **Formatting**: Use consistent indentation (2 spaces)

### Commit Messages

Follow conventional commit format:

```
type(scope): description

[optional body]

[optional footer]
```

Examples:
- `feat(ui): add character class selector component`
- `fix(parser): resolve JSON validation error`
- `docs(readme): update installation instructions`
- `refactor(core): simplify build validation logic`

### Pull Request Process

1. **Create a feature branch** from `main`
2. **Make your changes** following the coding guidelines
3. **Test your changes** thoroughly
4. **Update documentation** if needed
5. **Submit a pull request** with a clear description

### Pull Request Guidelines

- **Title**: Clear, descriptive title
- **Description**: Explain what the PR does and why
- **Related Issues**: Link to any related issues
- **Testing**: Describe how you tested the changes
- **Screenshots**: Include screenshots for UI changes

## 🧪 Testing

### Testing Requirements

- **Unit Tests**: Write tests for new functionality
- **Integration Tests**: Test component interactions
- **Manual Testing**: Test the application manually
- **Cross-Platform**: Test on different operating systems if possible

### Running Tests

```bash
# Run all tests
npm test

# Run tests in watch mode
npm run test:watch

# Run tests with coverage
npm run test:coverage
```

## 📚 Documentation

### Documentation Standards

- **README**: Keep the main README up to date
- **Code Comments**: Add JSDoc comments for functions and classes
- **API Documentation**: Document any new APIs or interfaces
- **User Guides**: Create guides for new features

### Updating Documentation

- Update relevant documentation when adding new features
- Include examples and usage instructions
- Keep documentation in sync with code changes

## 🐛 Bug Reports

### Bug Report Template

When reporting bugs, please include:

1. **Description**: Clear description of the bug
2. **Steps to Reproduce**: Step-by-step instructions
3. **Expected Behavior**: What you expected to happen
4. **Actual Behavior**: What actually happened
5. **Environment**: OS, Node.js version, Electron version
6. **Screenshots**: Visual evidence if applicable
7. **Console Logs**: Any error messages or logs

### Example Bug Report

```markdown
## Bug Description
The skill tree doesn't display correctly when switching character classes.

## Steps to Reproduce
1. Open the application
2. Select "Barbarian" class
3. Switch to "Sorcerer" class
4. Observe skill tree display

## Expected Behavior
Skill tree should update to show Sorcerer skills

## Actual Behavior
Skill tree still shows Barbarian skills

## Environment
- OS: Windows 10
- Node.js: v18.0.0
- Electron: v25.0.0
```

## 💡 Feature Requests

### Feature Request Guidelines

- **Clear Description**: Explain what you want to achieve
- **Use Case**: Describe how it would be useful
- **Mockups**: Include mockups or sketches if applicable
- **Alternatives**: Consider if existing features could be extended

## 🔒 Security

### Security Guidelines

- **Never commit sensitive data** (API keys, passwords, etc.)
- **Report security issues** privately to maintainers
- **Follow security best practices** in your code
- **Validate user input** to prevent injection attacks

## 📞 Getting Help

### Communication Channels

- **GitHub Issues**: For bugs and feature requests
- **GitHub Discussions**: For questions and community discussion
- **Pull Requests**: For code contributions
- **Wiki**: For detailed documentation

### Code of Conduct

- **Be respectful** and inclusive
- **Help others** learn and contribute
- **Give constructive feedback**
- **Focus on the code**, not the person

## 🎉 Recognition

### Contributor Recognition

- **Contributors**: All contributors will be listed in the README
- **Special Thanks**: Significant contributions will be acknowledged
- **Maintainer Status**: Active contributors may be invited to become maintainers

## 📋 Checklist for Contributors

Before submitting your contribution, ensure you have:

- [ ] Read and understood the contributing guidelines
- [ ] Set up the development environment
- [ ] Created a feature branch from `main`
- [ ] Made your changes following the coding guidelines
- [ ] Added appropriate tests
- [ ] Updated documentation if needed
- [ ] Tested your changes thoroughly
- [ ] Written a clear commit message
- [ ] Created a descriptive pull request

## 🚀 Quick Start for New Contributors

1. **Fork and clone** the repository
2. **Set up** the development environment
3. **Pick an issue** labeled "good first issue" or "help wanted"
4. **Make your changes** following the guidelines
5. **Submit a pull request**
6. **Get feedback** and iterate if needed

## 📞 Questions?

If you have questions about contributing:

- Check the [documentation](./docs/)
- Search existing [issues](../../issues) and [discussions](../../discussions)
- Open a new [discussion](../../discussions) for general questions
- Open an [issue](../../issues) for specific problems

Thank you for contributing to the Diablo 4 Build Tool! 🎮✨
