# Learn How to crate your own Folder Structure

## Using TypeScript as the folder structure

```bash
bansimplified-folder-structure/
│
├─ public/                 # Static files
│   └── vite.svg           # Vite logo/placeholder image
├─ src/                    # Source code
│   ├─ app/               # Page components for routing (often used with React Router)
│   │   ├─ Terms.tsx
│   │   ├─ admin/
│   │   │   └── Dashboard.tsx
│   │   ├─ auth/
│   │   │   ├─ AuthCallback.tsx
│   │   │   ├─ LoginAccount.tsx
│   │   │   └── SignUpAccount.tsx
│   │   └─ user/
│   │       └── Index.tsx
│   ├─ assets/            # Static assets (images, icons, fonts)
│   │   └── react.svg
│   ├─ components/        # Reusable UI components (Button, Card, Modal, etc.)
│   │   ├─ layout/
│   │   ├─ shared/
│   │   └─ ui/
│   │       ├─ card.tsx
│   │       ├─ skeleton.tsx
│   │       └─ table.tsx
│   ├─ hooks/             # Custom React hooks (useAuth, useLocalStorage, etc.)
│   │   └── useLogout.tsx
│   ├─ lib/               # Library utilities and configurations
│   │   ├─ supebase.ts    # Supabase client configuration
│   │   └── utils.ts       # Library-specific utilities
│   ├─ services/          # API services (fetch/axios calls, API integration)
│   │   └── axios.ts
│   ├─ types/             # Global TypeScript type definitions
│   ├─ utils/             # General utility functions (helpers, formatters)
│   │   ├─ redirectByRole.ts
│   │   └─ utils.ts
│   ├─ App.tsx            # Root React component
│   ├─ index.css          # Global CSS styles (includes Tailwind directives)
│   └─ main.tsx           # Application entry point (renders React to DOM)
├─ .env                   # Environment variables (NOT committed to git)
├─ .env.example           # Template for environment variables with examples
├─ .gitignore            # Git ignore rules
├─ components.json       # UI component registry (often for shadcn/ui)
├─ eslint.config.js      # ESLint configuration
├─ index.html            # HTML entry point
├─ package-lock.json     # NPM dependency lock file
├─ package.json          # Project dependencies and scripts
├─ postcss.config.js     # PostCSS configuration (processes Tailwind CSS)
├─ tailwind.config.js    # Tailwind CSS configuration
├─ tsconfig.app.json     # TypeScript config for application code
├─ tsconfig.json         # Main TypeScript configuration
├─ tsconfig.node.json    # TypeScript config for Node/bundler code
└── vite.config.ts        # Vite build tool configuration
```

