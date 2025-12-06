# 🎯 React Quiz Application - Kahoot Clone  

A modern, interactive quiz application inspired by Kahoot, built with React, TypeScript, and Vite. Features a complete CI/CD pipeline, comprehensive end‑to‑end testing with Playwright, real‑time Slack notifications, and Docker deployment.

---

## 📋 Table of Contents
- [✨ Key Features](#-key-features)
- [🏗️ Tech Stack](#%EF%B8%8F-tech-stack)
- [🚀 Quick Start](#-quick-start)
- [🧪 Testing](#-testing)
- [🐳 Docker Deployment](#-docker-deployment)
- [🔗 Integrations & Notifications](#-integrations--notifications)
- [📁 Project Structure](#-project-structure)
- [🤝 Contributing](#-contributing)

---

## ✨ Key Features

- **🎨 Modern UI** – Responsive design with Tailwind CSS & smooth animations  
- **🎮 Interactive Quiz Flow** – Start → Play → Complete with auto‑advance & real‑time feedback  
- **⏱️ Smart Timer** – 30‑second countdown with visual warnings  
- **📊 Live Scoring** – Real‑time score tracking & final performance breakdown  
- **🛡️ Edge‑Case Handling** – Click protection, refresh resilience, and input validation  
- **🧪 Full Test Suite** – 60+ Playwright tests covering UI, timer, scoring, and edge cases  
- **🚀 CI/CD Pipeline** – GitHub Actions with automated testing, linting, and Slack notifications  
- **🐳 Container Ready** – Dockerized for easy deployment

---

## 🏗️ Tech Stack

| Category          | Tools                                                                 |
|-------------------|-----------------------------------------------------------------------|
| **Frontend**      | React 18, TypeScript, Vite 5, Tailwind CSS, Lucide Icons              |
| **Testing**       | Playwright (E2E), ESLint, Prettier                                    |
| **CI/CD & DevOps**| GitHub Actions, Slack Integration, Docker                             |
| **Package Mgmt**  | npm / pnpm                                                            |
| **Runtime**       | Node.js 18+                                                           |

---

## 🚀 Quick Start

### Prerequisites
- Node.js (v18 or newer)
- npm (v8 or newer)
- Git

### Installation
```bash
# Clone repository
git clone https://github.com/Rynorbu/React-Quiz.git
cd React-Quiz

# Install dependencies
npm install

# Start development server
npm run dev
```
App runs at **http://localhost:5173**

### Other Scripts
```bash
npm run build          # Production build
npm run preview        # Preview production build
npm run lint           # Run ESLint
npm run lint:fix       # Auto-fix linting issues
```

---

## 🧪 Testing

### Run Test Suites
```bash
# Start dev server in one terminal
npm run dev

# In another terminal, run:
npm run test           # All tests (headless)
npm run test:ui        # Interactive UI mode
npm run test:debug     # Step‑by‑step debug
npm run test:headed    # With browser UI visible
```

### Generate Reports
```bash
npm run test:report    # HTML report
npm run test:md-report # Markdown summary
npm run test:coverage  # Coverage analysis
```

### Test Categories
| Category               | Coverage                                      |
|------------------------|-----------------------------------------------|
| ✅ Quiz Flow           | Start, answer selection, completion           |
| ⏱️ Timer Tests        | Countdown accuracy, expiry behavior           |
| 🔄 State Management    | Restart, navigation, persistence              |
| 🎨 UI/UX               | Responsiveness, visual feedback               |
| 🛡️ Edge Cases         | Rapid clicks, network interruption, refresh   |
| 📊 Data Validation     | Question integrity, scoring accuracy          |

---

## 🐳 Docker Deployment

### Build and Run
```bash
# Build image
docker build -t react-quiz-app .

# Run container
docker run -p 3000:3000 react-quiz-app
```
Access at **http://localhost:3000**

### Docker Compose (optional)
```yaml
version: '3.8'
services:
  quiz-app:
    build: .
    ports:
      - "3000:3000"
    environment:
      - NODE_ENV=production
```

---

## 🔗 Integrations & Notifications

### Slack Integration
- **🔔 Commit Notifications** – Real‑time alerts for each push  
- **⚙️ Workflow Alerts** – GitHub Actions success/failure notifications  
- **📊 Test Results** – Playwright execution summaries  
- **🎨 Rich Formatting** – Color‑coded messages with direct links to commits/PRs

### CI/CD Pipeline (GitHub Actions)
- Automated Playwright test suite on every push/PR  
- Multi‑browser testing (Chrome, Firefox, Safari)  
- ESLint & TypeScript validation  
- Build verification before merge  
- Parallel execution for faster feedback

---

## 📁 Project Structure
```
React-Quiz/
├── src/                    # React components, types, utils
├── tests/                  # Playwright test suites
│   ├── quiz-flow/         # Main quiz functionality
│   ├── timer/             # Timer tests
│   ├── ui-ux/             # UI/UX validation
│   └── edge-cases/        # Error & edge scenarios
├── .github/workflows/     # CI/CD configurations
├── public/                # Static assets
├── scripts/               # Build/deployment scripts
├── Dockerfile             # Container setup
└── playwright.config.ts   # Test framework config
```

---

## 🤝 Contributing

We welcome contributions! Please follow these steps:

1. **Fork & Clone**  
   ```bash
   git clone https://github.com/YOUR-USERNAME/React-Quiz.git
   cd React-Quiz
   git remote add upstream https://github.com/Rynorbu/React-Quiz.git
   ```

2. **Create a Branch**  
   ```bash
   git checkout -b feature/your-feature-name
   # or bugfix/issue-description
   ```

3. **Follow Code Standards**  
   - Run `npm run lint` and `npm run test` before committing  
   - Use descriptive commit messages: `type(scope): description`  
   - Update documentation for new features

4. **Submit a Pull Request**  
   - Ensure all tests pass  
   - Provide a clear description and screenshots if applicable  
   - Link related issues (e.g., `Closes #123`)

---

## 📄 License
This project is developed for academic purposes as part of **SWE5006 (Autumn 2025)**.  
Source code available under the [MIT License](LICENSE).

---

## 🔗 Links
- **🌐 Live Demo**: [React‑Quiz App](#)  
- **📂 Repository**: [https://github.com/Rynorbu/React‑Quiz](https://github.com/liberationzany/AS_02230300_reactquiz.git)  

Terminal Test Execution Screenshot:
![Terminal Test Execution](src/Screenshot%202025-12-06%20162656.png)

Terminal Output demonstrates:
![Terminal Output](src/Screenshot%20(3).png)

CI/CD Pipeline & GitHub Actions Screenshot:
![CI/CD Pipeline](src/Screenshot%20(2).png)
---

*Built with modern web technologies and a focus on testing, automation, and developer experience.*