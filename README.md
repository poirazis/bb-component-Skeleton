# Budibase Component Template

> A modern, minimal starting point for building custom Budibase components using **Svelte 5**, **TypeScript**, and **Vite**.

## About

This template provides everything you need to create and publish a production-ready Budibase custom component. It includes:

- ✨ **Modern Tech Stack**: Svelte 5.x with TypeScript, Vite for fast builds
- 🎯 **Minimal Boilerplate**: Simple, clean starting point without unnecessary complexity
- 📦 **Zero Dependencies**: No shared library dependency needed (add your own as needed)
- 🔧 **Proper Structure**: Follows Budibase plugin architecture patterns
- 🛡️ **Error Boundaries**: Built-in error handling with Svelte error boundaries
- 🚀 **CI/CD Ready**: GitHub Actions workflow for automatic builds and releases
- 🎨 **Styling**: Pre-configured with Spectrum CSS integration patterns

## Quick Start

### 1. Clone or Use as Template

**Option A: Use GitHub Template** (recommended)

- Click "Use this template" on GitHub to create your own repository

**Option B: Clone**

```bash
git clone https://github.com/poirazis/bb-component-Skeleton.git my-component
cd my-component
```

### 2. Install Dependencies

```bash
bun install
```

### 3. Update Component Name

Replace all references to `Skeleton` with your component name:

- **package.json**: Update `name` field
- **schema.json**: Update `name`, `friendlyName`, and `description`
- **src/Component.svelte**: Update component logic
- **Folder name**: Rename to `bb-component-YourName`

### 4. Build

```bash
bun run build
```

Output will be in `dist/`:

- `plugin.min.js` - Your minified component
- `schema.json` - Component metadata and settings
- `bb-component-YourName-1.0.0.tar.gz` - Ready to deploy to Budibase

### 5. Watch Mode

For development with automatic rebuilds:

```bash
bun run watch
```

## Project Structure

```
bb-component-YourName/
├── src/
│   └── Component.svelte      # Main component logic
├── lib/
│   ├── Wrapper.svelte        # Error boundary wrapper
│   └── Boundary.ts           # Error handling setup
├── index.ts                  # Budibase plugin registration
├── schema.json               # Component settings schema
├── package.json              # Dependencies and metadata
├── vite.config.js            # Build configuration
└── tsconfig.json             # TypeScript settings
```

## Component Development

### Basic Component Template

Your `Component.svelte` file should follow this pattern:

```svelte
<script lang="ts">
  import { getContext } from "svelte";

  // Budibase SDK context types
  interface SDKContext {
    styleable: (node: HTMLElement, styles: any) => void;
  }

  interface ComponentContext {
    styles: any;
  }

  // Get Budibase contexts
  const sdk = getContext<SDKContext>("sdk");
  const componentContext = getContext<ComponentContext>("component");
  const { styleable } = sdk;

  // Component state with Svelte 5 runes
  let myValue: string = $state("");

  // Props from schema
  let { label }: { label?: string } = $props();
</script>

<div use:styleable={componentContext.styles}>
  <!-- Your component markup here -->
</div>

<style>
  /* Your styles here */
</style>
```

### Adding Settings

Define component settings in `schema.json` under `settings` array:

```json
"settings": [
  {
    "type": "text",
    "key": "label",
    "label": "Label Text",
    "defaultValue": "Click me"
  },
  {
    "type": "select",
    "key": "size",
    "label": "Button Size",
    "defaultValue": "medium",
    "options": ["small", "medium", "large"]
  },
  {
    "type": "boolean",
    "key": "disabled",
    "label": "Disabled",
    "defaultValue": false
  }
]
```

### Available Setting Types

- `text` - Text input
- `number` - Number input
- `boolean` - Toggle/checkbox
- `select` - Dropdown menu
- `multi` - Multi-select
- `color` - Color picker
- `table` - Table editor
- `json` - JSON editor

## Styling

Components automatically integrate with Budibase's styling system via the `styleable` directive:

```svelte
<div use:styleable={componentContext.styles}>
  {/* Content styled by Budibase */}
</div>
```

Add custom CSS in the `<style>` block for component-specific styling.

## Publishing

### Version Bumping

Update `package.json` version, then:

```bash
git add .
git commit -m "Release v1.1.0"
git push origin develop
# Create PR to main/master
# Merge PR → GitHub Actions automatically builds and publishes
```

### Manual Build

```bash
bun run build
# Tarball is at dist/bb-component-YourName-X.Y.Z.tar.gz
```

## Resources

- [Budibase Documentation](https://github.com/Budibase/budibase)
- [Svelte 5 Docs](https://svelte.dev)
- [Custom Components Guide](https://docs.budibase.com)
- [Schema Configuration](https://github.com/Budibase/budibase/tree/master/packages/backend-core)

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines on improving this template.

## License

MIT - See LICENSE file for details
