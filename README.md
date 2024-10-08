# Next.js Template

Welcome to the Next.js Template project! This template is designed to be the ideal starting point for your modern NextJS applications, streamlining the development process right from the get-go. This is currently still a work in progress, so there are some expected changes. If you want to propose a change or have any issues with the template, you can open an issue [here](https://github.com/AFLabsOfficial/nextjs-template/issues/new/choose).

## 🚀 Quick Start

Getting started with this Next.js template is straightforward. Follow these steps to create your new project using this template:

1. **Create a new Next.js app using this template**:

   Run the following command in your terminal to create a new project with this template:

   ```bash
   npx create-next-app@latest your-project-name --example https://github.com/AFLabsOfficial/nextjs-template
   ```

2. **Navigate into your new project folder**:

   ```bash
   cd your-project-name
   ```

3. **Install dependencies**:

   ```bash
   pnpm i
   ```

4. **Run the development server**:

   ```bash
   pnpm dev
   ```

## 🧐 What's Included?

- Next.js 14 with [App router](https://nextjs.org/docs/app/building-your-application/routing)
- [TailwindCSS](https://tailwindcss.com/) for styling
  - Also exposes styles as global CSS variables and theme object
  - [tailwindcss-animate](https://github.com/jamiebuilds/tailwindcss-animate) plugin for quick animations
  - [tailwindcss/typography](https://github.com/tailwindlabs/tailwindcss-typography) plugin for typography (prose - useful for rendering markdown)
  - [tailwind-scrollbar](https://github.com/adoxography/tailwind-scrollbar) plugin for customizing scrollbars
- [Prettier](https://prettier.io/)
  - [Organizing Imports](https://www.npmjs.com/package/prettier-plugin-organize-imports) enabled
  - [Tailwind class sorting](https://www.npmjs.com/package/prettier-plugin-tailwindcss/v/0.0.0-insiders.d539a72) enabled
- [ESLint](https://eslint.org/) for finding problems with following rule sets:
  - [next/core-web-vitals](https://nextjs.org/docs/app/building-your-application/configuring/eslint)
  - [eslint:recommended](https://eslint.org/docs/latest/rules/)
  - [typescript-eslint](https://typescript-eslint.io/)
  - [eslint-plugin-react](https://github.com/jsx-eslint/eslint-plugin-react)
  - [eslint-plugin-react-hooks](https://www.npmjs.com/package/eslint-plugin-react-hooks)
  - [eslint-plugin-sonarjs](https://github.com/SonarSource/eslint-plugin-sonarjs)
- [Husky](https://typicode.github.io/husky/) for Git hooks with:
  - [commitlint](https://commitlint.js.org/) for conventional commits
  - [lint-staged](https://github.com/lint-staged/lint-staged)
- [.vscode](https://code.visualstudio.com/) settings for consistent development environment
  - [Prettier format + fix on save](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode)
  - Prevent auto imports from `@radix-ui` and `tailwindcss`
  - Prioritize non-relative imports (e.g. `@/components`)
  - Enable Tailwind highlighting and typesafety inside specific variables and functions (e.g. `cva()`)
- [next-international](https://next-international.vercel.app/) for internationalization
  - server side with `await getScopedI18n('fileName')`
  - client side with `useScopedI18n('fileName')`
- [t3-oss/env-nextjs](https://github.com/t3-oss/t3-env) for typesafe environment variables
- [Sentry](https://sentry.io/) for error/event tracking
- [shadcn/ui](https://ui.shadcn.com/) setup for UI components
- [react-hook-form](https://react-hook-form.com/) for forms
- [zod](https://zod.dev/) for form validation
- [Zodios](https://www.zodios.org/docs/client) for external API calls with validation
- Github Actions for lint, typecheck, localizations checks and tests.
- [openapi-zod-client](https://www.npmjs.com/package/openapi-zod-client) for generating API clients
  - We include a handlebars template for generating the zodios client from the openapi spec. It can be used with `pnpm gen-api` command
  - Adjust the `gen-api` command in [package.json](package.json) to fetch the OpenAPI `yaml` file from the correct URL
- [Utility hooks](https://usehooks.com/) for common tasks
  - Custom `useScrollCallback` for efficient scroll event handling

## 📂 Project Structure

Here's an overview of the folder structure provided in this template:

```bash
.
├── .github             # GitHub Actions configurations for CI/CD
├── .husky              # Husky configurations for managing Git hooks
├── .vscode             # VSCode settings to maintain consistency in development environments
├── docs                # Extended documentation and guides
├── public              # Stores static files like images and fonts
├── scripts             # Custom scripts for development tasks like testing and linting
├── src                 # Source files for the Next.js application
│   ├── app             # Core application files including pages and API routes
│   │   ├── [locale]    # Actual localized routes/pages of the application
│   │   ├── globals.css # Global CSS styles
│   │   └── layout.tsx  # Main layout component
│   ├── components      # Reusable UI components
│   │   ├── common      # Common components like providers, headers, footers, etc.
│   │   ├── examples    # Example components to demonstrate usage
│   │   └── ui          # UI specific components like buttons, modals, etc.
│   ├── i18n            # Internationalization configurations
│   │   ├── en          # English language translations
│   │   ├── sl          # Slovenian language translations
│   │   └── ...setup    # i18n setup files
│   ├── lib             # Library code and utility functions
│   │   ├── hooks       # Custom hooks for common tasks
│   │   └── utils.ts    # Utility functions for common tasks
│   ├── env.ts          # Environment-specific configurations
│   └── middleware.ts   # Custom middleware functions
└── README.md           # The main README file for the project
```

## 🔧 Configuration

Customize and configure your Next.js project to match your preferences and project requirements. Below is a short guide on how to tweak various aspects of the setup.

### 📦 Package Manager

Package manager is fixed to `pnpm` at a specific version. If you want to use another package manager, you can remove key `packageManager` from `package.json`. Even if you want to use `pnpm`, upgrade version of `pnpm` periodically.

### 🛠️ Prettier & ESLint Configuration

- **Prettier**: Modify the `.prettierrc.js` to change code formatting rules. You can adjust settings like print width, tab width, and more to fit your coding style.

- **ESLint**: To change linting rules, edit the `.eslintrc.json`. You can add or remove specific rules or plugins according to your project needs.

### 🌐 Internationalization and Localization

- **Adding New Languages**: To support a new language, add a corresponding folder in `src/i18n`, then update the `LOCALES` variable in `src/i18n/i18n.ts`. Include the new language in both `client.tsx` and `server.tsx` configurations to ensure proper loading.

### 🎨 TailwindCSS and Global Styles

- **TailwindCSS**: Customize the `tailwind.config.ts` to alter your design theme, such as changing the color palette or configuring responsiveness.

- **Global Styles**: Modify `src/app/globals.css` to adjust global styles or add new CSS variables. See [theming documentation](https://ui.shadcn.com/docs/theming) for more information.

### 🌍 Environment Variables

- **Type-Safe Environment Variables**: Edit `src/env.ts` to define and manage your environment variables using `t3-oss/env-nextjs` for type safety.

### 🚨 Sentry Configuration

- **Setup**: Ensure environment variables `NEXT_PUBLIC_SENTRY_DSN`, `NEXT_PUBLIC_SENTRY_TRACE_SAMPLE_RATE`, and `SENTRY_AUTH_TOKEN` are set up in your environment configuration file (like `.env.local`) for Sentry to function correctly.

### 📦 UI Components Configuration

- **shadcn/ui**: Modify the `components.json` to configure or extend the UI components provided by `shadcn/ui`. Before starting a new project, check for possible component updates. To install new components and get more information, visit the [shadcn/ui documentation](https://ui.shadcn.com/).
- Do not be afraid to modify the UI components to fit your project's needs. That's the whole point of using copy-paste components!

### TODOS:

- [ ] Dockerfile
- [ ] example docker compose
- [ ] example gitlab and github ci
- [ ] install pre-commit hooks automatically
