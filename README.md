# BragDev — Professional Achievements Tracker

Track and showcase your professional achievements with AI-powered insights generated from your GitHub contributions.

## 🚀 Features

- 🔐 **GitHub OAuth Authentication** — Secure sign-in with your GitHub account
- 📊 **GitHub Integration** — Import commits, pull requests, and issues automatically
- 🤖 **AI-Powered Analysis** — Generate smart summaries of your work with customizable prompts
- 📅 **Flexible Time Ranges** — Analyze achievements by day, week, month, or custom ranges
- 📈 **Visual Reports** — Beautiful charts and insights about your contributions
- 🎨 **Modern UI** — Clean, responsive layout with dark theme support

## 🛠️ Tech Stack

### Frontend

- **Angular 21** — Standalone components with signals
- **TypeScript** — Strict type checking
- **PrimeNG** — UI component library
- **RxJS** — Reactive programming
- **Vite** — Fast build tooling

### Best Practices

- ✅ Standalone components (no NgModules)
- ✅ Signals for state management
- ✅ `OnPush` change detection
- ✅ Lazy-loaded feature routes
- ✅ Functional guards and interceptors
- ✅ Modern `provideAppInitializer` usage (no deprecated APIs)
- ✅ Use `inject()` instead of constructor injection where appropriate
- ✅ Reactive forms
- ✅ WCAG AA accessibility compliance

## 📋 Prerequisites

- Node.js 21+ and npm
- Angular CLI 21+
- Backend API running (see the backend repository)

## 🚀 Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/farigab/bragdev-angular.git
cd bragdev-angular
```

### 2. Install dependencies

```bash
npm install
```

### 3. Configure the environment

Create or update `src/environments/environment.ts`:

```typescript
export const environment = {
  production: false,
  apiUrl: 'http://localhost:8080/api'
};
```

For production, update `src/environments/environment.prod.ts`:

```typescript
export const environment = {
  production: true,
  apiUrl: 'https://your-api-domain.com/api'
};
```

### 4. Run the development server

```bash
npm start
```

Open `http://localhost:4200/`

### 5. Build for production

```bash
npm run build
```

Build artifacts will be stored in the `dist/` directory.

## 📁 Project Structure

```text
src/
├── app/
│   ├── components/
│   │   ├── github-import/     # GitHub import assistant
│   │   ├── layout/            # Main layout wrapper
│   │   ├── login/             # Authentication pages
│   │   └── reports/           # Reports and analysis
│   ├── guards/
│   │   └── auth.guard.ts      # Route protection
│   ├── interceptors/
│   │   └── auth.interceptor.ts # HTTP authentication interceptor
│   ├── models/                # TypeScript interfaces
│   ├── pipes/
│   │   └── markdown.pipe.ts   # Markdown rendering
│   ├── services/              # Business logic and API services
│   ├── app.component.ts       # Root component
│   ├── app.config.ts          # Application configuration
│   └── app.routes.ts          # Route definitions
├── assets/                    # Static assets
├── environments/              # Environment configs
└── styles.css                 # Global styles
```

## 🔑 Key Components

### Authentication Flow

1. User clicks "Sign in with GitHub"
2. User is redirected to GitHub OAuth
3. Callback is handled by `AuthCallbackComponent`
4. Session initialization runs via `provideAppInitializer`
5. User data cached in `AuthService`

### GitHub Import Assistant

4-Step import flow:

1. **Connect** — Provide a GitHub personal access token
2. **Repositories** — Choose which repositories to analyze
3. **Time Range** — Pick a date range (preset or custom)
4. **AI Analysis** — Customize the prompt and generate insights

### State Management

- **Signals** for local reactive state
- **Computed signals** for derived state
- **RxJS** for async flows and side effects
- **HTTP interceptor** for session handling

## 🎨 Design System

Custom design system based on CSS custom properties:

```css
:root {
  --primary: #6B5DD3;
  --bg: #1C1B29;
  --surface: #2A273D;
  --text-primary: #E0DAFF;
  /* ... */
}
```

### Spacing Scale (8px base)

- `--spacing-xs: 4px`
- `--spacing-sm: 8px`
- `--spacing-md: 16px`
- `--spacing-lg: 24px`
- `--spacing-xl: 32px`

## 🧪 Tests

```bash
# Run unit tests
npm test

# Run e2e tests
npm run e2e
```

## 🔒 Security

- **HttpOnly cookies** for session management
- **CSRF protection** enforced by the backend
- **Secure OAuth flow** with `state` parameter
- **XSS protection** by sanitizing markdown (e.g., DOMPurify)
- **No sensitive data in localStorage**

## 🌐 Browser Support

- Chrome/Edge (latest 2 versions)
- Firefox (latest 2 versions)
- Safari (latest 2 versions)

## 📝 Environment Variables

| Variable | Description            | Default                      |
|----------|------------------------|------------------------------|
| `apiUrl` | Backend API base URL   | `http://localhost:8080/api`  |

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/awesome-feature`)
3. Follow the Angular style guide and project conventions
4. Ensure tests pass
5. Commit your changes (`git commit -m 'Add awesome feature'`)
6. Push the branch (`git push origin feature/awesome-feature`)
7. Open a Pull Request

### Code Style

- Use `prettier` for formatting
- Follow Angular naming conventions
- Write meaningful commit messages
- Add JSDoc comments for public APIs

## 📄 License

This project is licensed under the MIT License — see the LICENSE file for details.

## 👤 Author

farigab

## 🙏 Acknowledgements

- PrimeNG for excellent UI components
- The Angular team for a great framework
- GitHub for OAuth and its API

---

Built with ❤️ using Angular 21
