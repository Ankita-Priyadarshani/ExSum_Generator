# Contributing to ExSum Generator

Thank you for your interest in contributing to the ExSum Generator! We welcome contributions from the community to help improve this project.

---

## Table of Contents

- [Code of Conduct](#code-of-conduct)
- [How Can I Contribute?](#how-can-i-contribute)
  - [Reporting Bugs](#reporting-bugs)
  - [Suggesting Enhancements](#suggesting-enhancements)
  - [Pull Requests](#pull-requests)
- [Development Workflow](#development-workflow)
- [Coding Standards](#coding-standards)
- [Commit Guidelines](#commit-guidelines)
- [Testing](#testing)
- [Documentation](#documentation)

---

## Code of Conduct

This project is developed for the Defense Health Agency and all contributors are expected to maintain professional conduct. By participating, you agree to:

- Be respectful and inclusive in all interactions
- Accept constructive criticism gracefully
- Focus on what is best for the project and the DHA
- Show empathy towards other community members

---

## How Can I Contribute?

### Reporting Bugs

Before creating a bug report, please check existing issues to avoid duplicates.

When filing a bug report, include:

- **Clear title**: Describe the issue concisely
- **Steps to reproduce**: Provide detailed steps to reproduce the bug
- **Expected behavior**: What you expected to happen
- **Actual behavior**: What actually happened
- **Environment**: Browser, OS, versions of dependencies
- **Screenshots**: If applicable
- **Error messages**: Full error messages and stack traces

**Example:**
```
Title: ExSum Generator fails to upload PDF files larger than 10MB

Steps to reproduce:
1. Navigate to /exsum/new
2. Attempt to upload a PDF file larger than 10MB
3. Click "Generate"

Expected: File uploads successfully
Actual: Upload fails with "File too large" error

Environment: Chrome 119, Windows 11, React 17
```

### Suggesting Enhancements

Enhancement suggestions are welcome! Please provide:

- **Clear description**: What enhancement you'd like to see
- **Use case**: Why this enhancement would be valuable
- **Proposed solution**: Your ideas on how to implement it
- **Alternatives considered**: Other approaches you've thought about

### Pull Requests

Pull requests are the best way to contribute code. Please follow these steps:

1. **Create an issue first**: Discuss your proposed changes
2. **Fork the repository**: Create your own fork
3. **Create a branch**: Use a descriptive branch name
4. **Make your changes**: Follow our coding standards
5. **Test thoroughly**: Ensure all tests pass
6. **Update documentation**: If needed
7. **Submit the PR**: With a clear description

---

## Development Workflow

### 1. Fork and Clone

```bash
# Fork the repository on GitHub, then clone your fork
git clone https://github.com/your-username/exsum-generator.git
cd exsum-generator
```

### 2. Create a Branch

```bash
# Create a new branch for your feature or fix
git checkout -b feature/your-feature-name

# Or for bug fixes
git checkout -b fix/bug-description
```

### 3. Set Up Development Environment

```bash
# Install frontend dependencies
cd assets/client
pnpm install

# Install backend dependencies
cd ../exsum-generator-be
mvn clean install

# Install Python dependencies
pip install Dataset
pip install text_generation
```

### 4. Make Your Changes

- Write clean, readable code
- Follow existing code structure and patterns
- Add comments for complex logic
- Keep changes focused and atomic

### 5. Test Your Changes

```bash
# Run linter
pnpm lint

# Run type checking
pnpm type-check

# Build the project
pnpm build

# Test the backend
cd ../exsum-generator-be
mvn test
```

### 6. Commit Your Changes

```bash
# Stage your changes
git add .

# Commit with a meaningful message
git commit -m "feat: Add support for DOCX file uploads"
```

### 7. Push and Create Pull Request

```bash
# Push to your fork
git push origin feature/your-feature-name

# Create a Pull Request on GitHub
```

---

## Coding Standards

### TypeScript/JavaScript

- Use TypeScript for type safety
- Follow ESLint and Prettier configurations
- Use meaningful variable and function names
- Avoid any types; use proper typing
- Keep functions small and focused
- Use async/await over promises

**Example:**
```typescript
// Good
async function generateSummary(documentId: string, modelId: string): Promise<Summary> {
    const document = await fetchDocument(documentId);
    const result = await insight.runPixel(`LLM(model=["${modelId}"])`);
    return parseSummary(result);
}

// Bad
function generateSummary(documentId, modelId) {
    // Complex nested callbacks
}
```

### React Components

- Use functional components with hooks
- Keep components small and reusable
- Use proper prop types
- Extract complex logic into custom hooks
- Use Material UI components consistently

**Example:**
```typescript
interface DocumentUploaderProps {
    onUpload: (file: File) => void;
    acceptedFormats: string[];
}

const DocumentUploader: React.FC<DocumentUploaderProps> = ({ onUpload, acceptedFormats }) => {
    // Component logic
    return <div>...</div>;
};
```

### Java

- Follow Java 8 conventions
- Use meaningful class and method names
- Add Javadoc comments for public methods
- Keep methods focused on single responsibility
- Handle exceptions appropriately

### Code Formatting

- Use 4 spaces for indentation (Java)
- Use 2 spaces for indentation (TypeScript/JavaScript)
- Maximum line length: 100 characters
- Use single quotes for strings in JavaScript/TypeScript
- Run `pnpm format` before committing

---

## Commit Guidelines

Follow the [Conventional Commits](https://www.conventionalcommits.org/) specification:

### Format

```
<type>(<scope>): <subject>

<body>

<footer>
```

### Types

- **feat**: New feature
- **fix**: Bug fix
- **docs**: Documentation changes
- **style**: Code style changes (formatting, no logic change)
- **refactor**: Code refactoring
- **test**: Adding or updating tests
- **chore**: Build process or auxiliary tool changes

### Examples

```bash
feat(upload): Add support for DOCX file uploads

Added DOCX parsing capability to the document uploader.
Files up to 50MB are now supported.

Closes #123

---

fix(generation): Fix summary generation timeout

Increased timeout for LLM requests from 30s to 60s
to handle larger documents.

Fixes #456

---

docs(readme): Update installation instructions

Added detailed steps for Windows users and
troubleshooting section for common errors.
```

---

## Testing

### Before Submitting

Ensure your code passes all checks:

```bash
# Lint your code
pnpm lint

# Check types
pnpm type-check

# Build the project
pnpm build

# Test backend
cd assets/exsum-generator-be
mvn test
mvn package
```

### Testing Guidelines

- Test on multiple browsers (Chrome, Firefox, Edge)
- Test with different file types and sizes
- Test error scenarios
- Verify backward compatibility
- Test the full workflow end-to-end

---

## Documentation

### Update Documentation

When making changes that affect usage:

- Update README.md if necessary
- Update code comments
- Update `_PMO_Documentation.pptx` for major features
- Add JSDoc comments for new functions/components

### Documentation Style

- Use clear, concise language
- Provide examples where helpful
- Keep documentation up to date with code changes
- Use proper Markdown formatting

**Example:**
```typescript
/**
 * Uploads a document and initiates summary generation
 * 
 * @param file - The document file to upload (PDF, DOCX, or TXT)
 * @param modelId - The ID of the LLM model to use
 * @param vectorDBId - The ID of the vector database for RAG
 * @returns Promise resolving to the generated summary
 * @throws {Error} If file format is not supported or upload fails
 */
async function uploadAndGenerate(
    file: File, 
    modelId: string, 
    vectorDBId: string
): Promise<Summary> {
    // Implementation
}
```

---

## Pull Request Process

### Before Submitting

1. ✅ Branch is up to date with main
2. ✅ All tests pass
3. ✅ Code is linted and formatted
4. ✅ Documentation is updated
5. ✅ Commit messages follow guidelines
6. ✅ Changes are focused and atomic

### PR Description Template

```markdown
## Description
Brief description of changes

## Type of Change
- [ ] Bug fix
- [ ] New feature
- [ ] Documentation update
- [ ] Refactoring

## Testing
How has this been tested?

## Checklist
- [ ] Code follows style guidelines
- [ ] Self-review completed
- [ ] Comments added for complex code
- [ ] Documentation updated
- [ ] No new warnings generated
- [ ] Tests added/updated
- [ ] All tests passing

## Screenshots (if applicable)

## Related Issues
Closes #issue_number
```

### Review Process

- PRs require review from at least one maintainer
- Address all review comments
- Keep the PR updated with the main branch
- Be responsive to feedback
- Squash commits if requested

---

## Questions?

If you have questions about contributing:

1. Check existing documentation in `_PMO_Documentation.pptx`
2. Review closed issues and PRs for similar discussions
3. Contact the development team
4. Open a discussion issue for general questions

---

## Recognition

Contributors will be acknowledged in:
- Release notes for their contributions
- The project documentation
- Special recognition for significant contributions

---

Thank you for contributing to ExSum Generator! Your efforts help improve this tool for the Defense Health Agency.

**Built for the Defense Health Agency**
