# ExSum Generator

An AI-powered executive summary generator designed to streamline document analysis and summary creation for the Defense Health Agency (DHA). Part of the SEMOSS PMO Portal suite.

---

## 📋 Table of Contents

- [Overview](#overview)
- [Key Features](#key-features)
- [Technology Stack](#technology-stack)
- [Installation](#installation)
- [Configuration](#configuration)
- [Usage](#usage)
- [Deployment](#deployment)
- [Contributing](#contributing)
- [Documentation](#documentation)
- [License](#license)
- [Acknowledgments](#acknowledgments)

---

## Overview

The ExSum Generator automates the creation of executive summaries from uploaded documents using AI-powered analysis. It provides an intuitive interface for document upload, AI-generated summary creation, iterative refinement, and professional document export.

Built as part of the SEMOSS PMO Portal, this application leverages advanced language models and vector databases to deliver context-aware, high-quality executive summaries that reduce manual effort and enhance productivity.

---

## Key Features
- **Document Upload**: Support for PDF, DOCX, and TXT formats via drag-and-drop or file selection
- **AI-Powered Generation**: Utilizes Large Language Models (LLMs) to create concise executive summaries
- **Version Control**: Track multiple versions of generated summaries with side-by-side comparison
- **Iterative Refinement**: Provide feedback to improve generated content through multiple iterations
- **Draft Management**: Save and manage multiple drafts with sidebar navigation
- **Export Capability**: Generate professional Word documents from summaries
- **Vector Database Integration**: Leverage RAG (Retrieval-Augmented Generation) for context-aware summaries

---

## Technology Stack
- **Frontend**: React 17, TypeScript, Material UI v5
- **State Management**: MobX with persistence support
- **Backend**: Java 8 with Maven
- **AI Integration**: SEMOSS SDK (v1.0.0-beta.14) and SEMOSS SDK React (v1.0.0-beta.15)
- **Markdown Support**: React Markdown (v8.0.7), @uiw/react-md-editor (v4.0.5)
- **File Upload**: React Dropzone (v14.2.3)
- **Styling**: Styled Components (v5.3.11), Material UI
- **Backend Processing**: SEMOSS Reactors, CommonMark (v0.21.0)
- **Build Tool**: Webpack 5

---

## Installation

### Frontend Setup
```bash
# Navigate to client directory
cd assets/client

# Install dependencies using pnpm
pnpm install
```

### Backend Setup
```bash
# Navigate to backend directory
cd assets/exsum-generator-be

# Clean and install Maven dependencies
mvn clean install
```

---

## Configuration

Create a `.env` file in the `assets/client` directory:
```env
# SEMOSS Configuration
MODULE=your-module-name
ACCESS_KEY=your-access-key
SECRET_KEY=your-secret-key
APP=your-app-id

# Optional: Development settings
NODE_ENV=development
PORT=3000
```

---

## Usage

### Starting Development Server
```bash
# In assets/client directory
pnpm dev

# Application will be available at http://localhost:3000
```

### Workflow

1. **Upload Document** - Navigate to `/exsum/new` and upload your file (PDF, DOCX, TXT)
2. **Select AI Model and Vector Database** - Choose your preferred LLM model and vector database
3. **Generate Summary** - Click "Generate" to create the executive summary
4. **Refine with Feedback** - Provide feedback and regenerate to improve the summary
5. **Save and Manage Drafts** - Drafts are automatically saved with full version history
6. **Export Document** - Download the summary as a Word document

### Building for Production
```bash
# Build frontend
cd assets/client
pnpm build

# Build backend
cd assets/exsum-generator-be
mvn clean package

# Output: target/exsum-generator-be-0.0.1-SNAPSHOT.jar
```

---

## Deployment

### Build the Application
```bash
cd assets/client
pnpm build

cd ../exsum-generator-be
mvn clean package
```

### Deploy to Govconnect.ai

1. Log in to Govconnect.ai portal
2. Navigate to "Create New App"
3. Upload the compressed deployment package
4. Configure environment variables (MODULE, ACCESS_KEY, SECRET_KEY, APP)
5. Set app permissions and access controls
6. Test the application in staging environment
7. Publish to production

---

## Contributing

We welcome contributions to improve the ExSum Generator! Please see [CONTRIBUTING.md](CONTRIBUTING.md) for details on the development workflow and coding standards.

---

## Documentation

- **SEMOSS SDK Documentation**: [https://semoss.org/docs](https://semoss.org/docs)
- **Material UI Documentation**: [https://mui.com](https://mui.com)
- **React Documentation**: [https://react.dev](https://react.dev)
- **TypeScript Documentation**: [https://www.typescriptlang.org/docs](https://www.typescriptlang.org/docs)

---

## License

This project is proprietary software developed for the Defense Health Agency (DHA). All rights reserved.

**Authorized Use Only**: This software is for official use by authorized DHA personnel and contractors only. Unauthorized access, use, or distribution is strictly prohibited.

---

## Acknowledgments

This project is built using the following technologies:

- **[React](https://react.dev)** - UI framework
- **[Material UI](https://mui.com)** - Component library
- **[MobX](https://mobx.js.org)** - State management
- **[SEMOSS](https://semoss.org)** - AI and analytics platform
- **[TypeScript](https://www.typescriptlang.org)** - Type-safe JavaScript
- **[Webpack](https://webpack.js.org)** - Module bundler
- **[pnpm](https://pnpm.io)** - Package manager

---

