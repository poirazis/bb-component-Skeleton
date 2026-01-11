# Contributing to Budibase Component Template

Thank you for your interest in improving this template! This document provides guidelines for contributing.

## Development Setup

### Prerequisites

- Node.js 18+ or bun
- Git
- A code editor (VS Code recommended)

### Local Development

1. **Clone the repository**
   ```bash
   git clone https://github.com/poirazis/bb-component-Skeleton.git
   cd bb-component-Skeleton
   ```

2. **Install dependencies**
   ```bash
   bun install
   ```

3. **Start development with watch mode**
   ```bash
   bun run watch
   ```

4. **Build for testing**
   ```bash
   bun run build
   ```

## Making Changes

### Code Style

- Use **TypeScript** for type safety
- Follow **Svelte 5** conventions
- Use descriptive variable/function names
- Add comments for complex logic

### Component Structure

- Keep components focused and single-purpose
- Use Svelte 5 runes (`$state`, `$props`, `$derived`)
- Implement error boundaries with `Wrapper.svelte`
- Export context properly to Budibase

### Schema Updates

When adding new properties:

1. Add setting definition to `schema.json`
2. Add corresponding prop to `Component.svelte`
3. Update README with usage example
4. Test the property in Budibase

## Testing

### Manual Testing

1. Build the component: `bun run build`
2. Upload `dist/bb-component-Skeleton-1.0.0.tar.gz` to Budibase
3. Test in Budibase editor
4. Verify settings work correctly

### Validation

The build process validates your schema using `@budibase/backend-core`. If validation fails, the build will error with details.

## Commit Guidelines

- Use clear, descriptive commit messages
- Prefix with type: `feat:`, `fix:`, `docs:`, `refactor:`, `test:`
- Examples:
  - `feat: add new button size option`
  - `fix: resolve error boundary styling`
  - `docs: update README with examples`

## Pull Request Process

1. **Create a feature branch**
   ```bash
   git checkout -b feature/your-feature
   ```

2. **Make your changes** and test thoroughly

3. **Commit and push**
   ```bash
   git add .
   git commit -m "feat: your descriptive message"
   git push origin feature/your-feature
   ```

4. **Create a pull request** on GitHub with:
   - Clear description of changes
   - Reason for changes
   - Testing information
   - Any breaking changes

5. **Address review feedback**

## Release Process

1. **Update version** in `package.json`
2. **Update CHANGELOG** if applicable
3. **Create release commit**
   ```bash
   git commit -m "chore: release v1.1.0"
   ```
4. **Create PR** from develop to main
5. **GitHub Actions** automatically builds and publishes

## Reporting Issues

Found a bug? Please open an issue with:

- **Description**: What's the issue?
- **Steps to reproduce**: How to replicate it
- **Expected behavior**: What should happen
- **Actual behavior**: What actually happens
- **Environment**: OS, browser, Budibase version

## Questions or Suggestions?

- Open an issue for discussion
- Check existing issues first
- Be respectful and constructive

## Code of Conduct

- Be respectful to all contributors
- Provide constructive feedback
- Welcome diverse perspectives
- Report inappropriate behavior

Thank you for contributing! 🎉
