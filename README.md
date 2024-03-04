# remix + vite + radix-ui/themes

This repository is for the purpose of creating a minimal reproduction.

## Reproduction steps

```
pnpm i
pnpm run dev
```

then visit http://localhost:5173

check messages in terminal.

## How was the project built

This is a project initialized through remix-vite, template originated from [remix-vite docs](https://remix.run/docs/en/main/future/vite)

### 1. remix-vite init

```bash
pnpm dlx create-remix@latest --template remix-run/remix/templates/vite
```

### 2. add radix-ui/themes@next

for esm support, use `radix-ui/themes@next`

```bash
pnpm add radix-ui/themes@next
```

### 3. use radix-ui/themes in project

```tsx
//@file: app/root.tsx
import "@radix-ui/themes/styles.css";
import { Theme } from "@radix-ui/themes";

// ...other code snippets...

export default function App() {
  return (
    <Theme>
      <Outlet />
    </Theme>
  );
}
```

### 4. See outputs

run project

```bash
pnpm run dev
```

vist http://localhost:5173

get messages in terminal.

```bash
14:20:55 [vite] Pre-transform error: Failed to load url /node_modules/.pnpm/@radix-ui+themes@3.0.0-rc.13-patch.1_@types+react-dom@18.2.19_@types+react@18.2.61_react-dom@18.2.0_react@18.2.0/node_modules/@radix-ui/themes/styles.css (resolved id: [EDITED]/solve-remix-vite-add-radix-ui-themes-allow-list-problem/node_modules/.pnpm/@radix-ui+themes@3.0.0-rc.13-patch.1_@types+react-dom@18.2.19_@types+react@18.2.61_react-dom@18.2.0_react@18.2.0/node_modules/@radix-ui/themes/styles.css) in [EDITED]/solve-remix-vite-add-radix-ui-themes-allow-list-problem/app/root.tsx. Does the file exist?
The request url "[EDITED]/solve-remix-vite-add-radix-ui-themes-allow-list-problem/node_modules/.pnpm/@radix-ui+themes@3.0.0-rc.13-patch.1_@types+react-dom@18.2.19_@types+react@18.2.61_react-dom@18.2.0_react@18.2.0/node_modules/@radix-ui/themes/styles.css" is outside of Vite serving allow list.

- [EDITED]/solve-remix-vite-add-radix-ui-themes-allow-list-problem/app
- [EDITED]/solve-remix-vite-add-radix-ui-themes-allow-list-problem/node_modules/.pnpm/vite@5.1.4/node_modules/vite/dist/client

Refer to docs https://vitejs.dev/config/server-options.html#server-fs-allow for configurations and more details.
```
