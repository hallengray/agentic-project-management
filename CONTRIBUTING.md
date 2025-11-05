# Contributing to Agentic Project Management (APM)

Thank you for your interest in contributing to APM! This document provides guidelines for contributing to both the original APM and the Enhanced Edition.

## Project Information

**Original APM:** Created by [sdi2200262 - CobuterMan](https://github.com/sdi2200262)  
**Enhanced Edition:** Maintained by [hallengray](https://github.com/hallengray)  
**License:** Mozilla Public License 2.0 (MPL-2.0)

## Enhanced Edition (v0.5.2)

This fork includes production-ready enhancements:

- Infrastructure Automation (MCP server auto-configuration)
- Smart Model Selection (cost optimization)
- Version-Aware Best Practices (Context7 integration)
- Payment Provider Automation (Stripe, PayPal, Square, Paddle)

## How to Contribute

We welcome contributions in the following areas:

### 1. Bug Reports & Feature Requests

**Before submitting:**

- Search existing [issues](https://github.com/hallengray/agentic-project-management/issues) to avoid duplicates
- Check if the issue exists in the original APM or only in the Enhanced Edition

**When submitting:**

- Use a clear, descriptive title
- Include your APM version (`apm --version`)
- Provide steps to reproduce (for bugs)
- Include relevant logs or screenshots
- Tag appropriately: `bug`, `enhancement`, `question`, `documentation`

### 2. Documentation Improvements

**Areas needing documentation:**

- Clarifying existing guides
- Adding examples for complex workflows
- Translating documentation
- Creating video tutorials
- Improving error messages

**Process:**

1. Fork the repository
2. Make your changes in the `docs/` directory
3. Test with a real workflow if applicable
4. Submit a pull request

### 3. Code Contributions

**What we're looking for:**

- Bug fixes
- Performance improvements
- New features (discuss in an issue first)
- Test coverage improvements
- Code refactoring for maintainability

**Contribution Areas:**

#### Core Framework

- Agent coordination improvements
- Memory system enhancements
- Handover procedure optimizations
- Context retention techniques

#### Enhanced Features (v0.5.2)

- Additional MCP server integrations
- More payment provider support (Coinbase Commerce, Razorpay, etc.)
- Analytics automation (PostHog, Mixpanel, Google Analytics)
- Error tracking automation (Sentry, Rollbar)
- Email provider automation (SendGrid, Resend, Mailgun)

#### Ad-Hoc Delegation Guides

- Testing automation guides
- Security analysis guides
- Data extraction guides
- Performance optimization guides

#### AI Assistant Support

- New IDE/CLI integrations
- Command format adaptations
- Platform-specific optimizations

### 4. Development Setup

**Prerequisites:**

- Node.js 18+
- NPM or Yarn
- Git

**Setup:**

```bash
# Fork and clone the repository
git clone https://github.com/YOUR_USERNAME/agentic-project-management.git
cd agentic-project-management

# Install dependencies
npm install

# Run tests
npm test

# Build
npm run build
```

### 5. Pull Request Process

**Before submitting:**

1. **Create an issue** first to discuss significant changes
2. **Fork the repository** (don't work directly on main)
3. **Create a feature branch:** `git checkout -b feature/your-feature-name`
4. **Follow code style:** Match existing conventions
5. **Write tests** for new functionality
6. **Update documentation** if needed
7. **Test thoroughly** with real workflows

**When submitting:**

1. **Clear PR title:** Summarize the change in one line
2. **Description:** Explain what, why, and how
3. **Link to issue:** Reference related issues
4. **Screenshots/logs:** Include if relevant
5. **Checklist:** Confirm all requirements met

**PR Template:**

```markdown
## Description

[Brief description of changes]

## Related Issue

Closes #[issue_number]

## Type of Change

- [ ] Bug fix
- [ ] New feature
- [ ] Documentation update
- [ ] Performance improvement
- [ ] Code refactoring

## Testing

- [ ] Tested manually with [describe scenario]
- [ ] Added/updated unit tests
- [ ] All tests pass (`npm test`)

## Checklist

- [ ] Code follows project style
- [ ] Documentation updated
- [ ] No breaking changes (or documented if unavoidable)
- [ ] Commits are clear and descriptive
```

### 6. Code Style Guidelines

**General:**

- Use clear, descriptive variable names
- Comment complex logic
- Keep functions focused and small
- Prefer readability over cleverness

**Markdown (Guides/Documentation):**

- Use proper headers (`##`, `###`)
- Include code blocks with syntax highlighting
- Add examples for complex concepts
- Keep lines under 100 characters when possible

**JavaScript/Node.js:**

- Follow existing code style
- Use ES6+ features
- Avoid unnecessary dependencies
- Handle errors gracefully

**Templates/Prompts:**

- Clear, actionable instructions
- Structured format (YAML frontmatter + sections)
- Include examples where helpful
- Test with actual AI agents

### 7. License & Attribution

**Important:** By contributing, you agree that your contributions will be licensed under the **Mozilla Public License 2.0 (MPL-2.0)**.

**What this means:**

- Your code must be open source
- Modifications to APM core files must be shared
- You retain copyright of your contributions
- Commercial use is allowed
- Attribution is required

**Attribution:**

- Add your name to `package.json` contributors if making significant changes
- Document your contributions in commit messages
- Original authors must remain credited

### 8. Areas Particularly Seeking Contributions

**High Priority:**

- **Assistant Support:** New IDE/CLI integrations (Windsurf, Roo Code, etc.)
- **Ad-Hoc Guides:** Testing, security, data extraction delegation guides
- **Payment Providers:** Additional integrations (Coinbase Commerce, Razorpay)
- **Analytics Automation:** PostHog, Mixpanel, Google Analytics setup

**Medium Priority:**

- **Error Tracking:** Sentry, Rollbar automation
- **Email Providers:** SendGrid, Resend integration
- **Documentation:** Video tutorials, more examples
- **Testing:** Increased test coverage

**Community Contributions:**

- Domain-specific customizations (e-commerce, SaaS, etc.)
- Internationalization (translations)
- Performance benchmarks
- Use case studies

### 9. Community Guidelines

**Be respectful:**

- Constructive feedback only
- No harassment or discrimination
- Assume good intentions
- Help newcomers

**Be collaborative:**

- Discuss before major changes
- Review others' PRs thoughtfully
- Share knowledge and resources
- Credit others' work

**Be patient:**

- Maintainers review PRs as time allows
- Some discussions take time to resolve
- Complex features need careful consideration

### 10. Getting Help

**Questions?**

- Check [Documentation](docs/README.md) first
- Search [GitHub Issues](https://github.com/hallengray/agentic-project-management/issues)
- Ask in [GitHub Discussions](https://github.com/hallengray/agentic-project-management/discussions)
- Reference [original APM](https://github.com/Vontive/cursor-apm) for core concepts

**Found a security issue?**

- **DO NOT** open a public issue
- Email hallengray directly (see GitHub profile)
- Include detailed description and steps to reproduce

---

## Recognition

Contributors will be:

- Listed in `package.json` contributors
- Mentioned in release notes for significant contributions
- Credited in documentation they create/improve

Thank you for contributing to APM! 🎉

---

**Enhanced Edition by:** [hallengray](https://github.com/hallengray)  
**Original by:** [CobuterMan](https://github.com/sdi2200262)  
**License:** MPL-2.0  
**Last Updated:** November 2025
