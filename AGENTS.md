<!-- AGENTS.md: Guidelines for automated coding agents -->

# Agent Guidelines

This file defines conventions and workflows for automated agents operating in this repository.
It covers build, lint, and test commands as well as code style guidelines for:
- Markdown & front matter
- YAML configuration
- SCSS/CSS assets
- JavaScript scripts and config
- Go modules, imports, naming, error handling

Agents must follow these rules to maintain consistency and reliability when modifying the codebase.

## Build, Lint & Test Commands

Run these commands from the repository root or the noted module directories.

```bash
# Start Hugo development server (drafts & live reload)
hugo server -D
# Generate minified production build
hugo --minify
# Build CSS/JS assets in Tailwind module
cd themes/modules/blox-tailwind
npm install
npm run build:styles
npm run assets:dist
cd -
# Run Go module tests (if any)
go test ./themes/modules/...
# Run a single Go test by name
go test -run ^TestMyFunction$ ./themes/modules/...
# Format and vet Go code
go fmt ./themes/modules/...
go vet ./themes/modules/...
# Rebuild the Pagefind search index after a production build
npx pagefind --site public
```

## Code Style Guidelines

Automated agents should adhere to the existing conventions when editing or adding code.

### Markdown & Front Matter

- Use YAML front matter enclosed in `---` delimiters.
- Order front matter keys: `title`, `date`, `draft`, `type`, `weight`, `tags`.
- Example:
  ```yaml
  ---
  title: "My New Post"
  date: 2025-03-15
  draft: false
  type: post
  weight: 100
  tags: ["hugo","go","tailwind"]
  ---
  ```
- Wrap content lines at ~80 characters.
- Use fenced code blocks with language identifiers.
- Indent nested list items by two spaces.
- Prefer Title Case for headings.

### YAML

- Use 2-space indentation.
- Only quote strings when necessary.
- Use block literals (`|`) for multiline text.
- Align related mapping keys vertically if it improves readability.
- Example:
  ```yaml
  description: |
    This multiline block preserves
    line breaks in the rendered output.
  ```

### SCSS/CSS

- Indent with 2 spaces.
- Name classes and variables in hyphen-case.
- Define SCSS variables and mixins at the top.
- Place custom overrides in `assets/scss/custom/custom.scss`.
- Use comments only for non-obvious design logic.

### JavaScript (Tailwind Config & Scripts)

- Use single quotes for strings.
- Terminate statements with semicolons.
- Import or require modules at the top.
- Use arrow functions and destructuring.
- Guard debug logs: `if (process.env.DEBUG) console.log(...);`.
- Example:
  ```js
  const defaultTheme = require('tailwindcss/defaultTheme');
  module.exports = {
    theme: { extend: {} },
    plugins: [require('@tailwindcss/typography')],
  };
  ```

### Go Modules

- Format code with `gofmt -s` and update imports with `goimports -w`.
- Group imports in three blocks:
  1. Standard library
  2. External dependencies
  3. Internal modules
- Run `go mod tidy` after changing dependencies.

### Error Handling (Go)

- Always check and return errors with context:
  ```go
  if err != nil {
    return fmt.Errorf("fetch user data: %w", err)
  }
  ```
- Avoid `panic` in production code; reserve for unrecoverable startup errors.
- Use the standard `errors` package for wrapping and unwrapping.

### Naming Conventions

- **Go**:
  - Exported identifiers: PascalCase
  - Unexported identifiers: camelCase
- **JavaScript/TypeScript**:
  - Variables and functions: camelCase
  - Components (if any): PascalCase
- **CSS/SCSS**:
  - Class names and IDs: hyphen-case
- **Markdown files**:
  - Use kebab-case for filenames (e.g. `my-new-post.md`)
- **Front matter**:
  - `type` values: snake_case (e.g. `blog_post`)

## File & Directory Conventions

- Content files in `content/` use hyphen-case slugs.
- Static images go in `static/images/<section>/` with lowercase names.
- SCSS partials begin with underscore (`_variables.scss`).
- Theme modules live under `themes/modules/<module-name>/`.

## Cursor & Copilot Rules

No Cursor rules detected in `.cursor/rules/` or `.cursorrules`.
No Copilot instructions found in `.github/copilot-instructions.md`.
Skip these integrations.

---
*End of AGENTS.md (~150 lines)*
