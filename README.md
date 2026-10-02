# Git Imported Project

A curated collection of top GitHub repositories organized by category — gathered as reference material for vibe coding, creative web development, and AI-assisted development.

## Folder Structure

```
git-imported-project/
├── creative-coding/      # WebGL, canvas, 3D graphics libraries
├── ai-tools/             # AI coding assistants and productivity tools
├── web-frameworks/       # JavaScript frameworks and utilities
└── templates/            # Full project templates
```

---

## 🎨 Creative Coding (3 repos)

Libraries for building interactive 3D graphics, WebGL experiences, and creative coding projects — directly useful for SPIRIT and similar visual projects.

### [three.js](https://github.com/mrdoob/three.js) (`creative-coding/three.js`)
- **⭐ ~115k stars** — The most popular WebGL library in the world.
- **What it is**: Simplifies 3D graphics on the web with an intuitive API. Handles rendering, scenes, cameras, lighting, animations, geometry, materials, and much more.
- **Why it's useful**: Your SPIRIT project uses raw WebGL. Three.js handles cross-browser compatibility, math, shaders, and provides an ecosystem of examples (`examples/`). Study `examples/jsm/` for postprocessing, controls, loaders, and math reference.
- **Quick start**: `npm install three` → `new THREE.Scene()`, add a mesh, `renderer.render()`.

### [react-three-fiber](https://github.com/pmndrs/react-three-fiber) (`creative-coding/react-three-fiber`)
- **⭐ ~22k stars** — React renderer for Three.js.
- **What it is**: A hook-based way to use Three.js inside React. Turns Three.js objects into React components (`<mesh>`, `<ambientLight>`, etc.).
- **Why it's useful**: If you ever migrate SPIRIT to React (or build new projects with Next.js + 3D), R3F is the idiomatic approach. Integrates with `@react-three/drei` for ready-made helpers (orbit controls, environment maps, loaders).
- **Quick start**: `npm install three @react-three/fiber` → use `useFrame()`, `<Canvas>`, `<mesh>`.

### [ogl](https://github.com/oframe/ogl) (`creative-coding/ogl`)
- **⭐ ~5.5k stars** — Tiny WebGL library (~15KB), no dependencies.
- **What it is**: A smaller, more manual WebGL library compared to Three.js. Gives you direct control over the GL context, shaders, and rendering pipeline.
- **Why it's useful**: SPIRIT already uses raw WebGL. OGL is a great reference for understanding how to structure a lightweight renderer, shader management, and math (vectors, matrices, quaternions). Perfect if you ever want a smaller bundle for performance-critical projects.
- **Quick start**: `npm install ogl` → `new Renderer()`, `new Scene()`, `new Mesh(gl, geometry, shader)`.

---

## 🤖 AI Tools (4 repos)

AI coding assistants, context-packers, and productivity tools for vibe coding workflows. From the `aicodeguide` reference.

### [Aider](https://github.com/Aider-AI/aider) (`ai-tools/aider`)
- **⭐ ~42k stars** — AI pair programming in your terminal.
- **What it is**: An open-source AI coding assistant that works directly with your git repository. Supports multiple LLMs (Claude, GPT, DeepSeek, Gemini, etc.).
- **Why it's useful**: One of the best free/open-source alternatives to Claude Code. Integrates with git so all code changes are committed. Supports multi-turn editing, file reading/editing, and map-of-context. The `aicodeguide` recommends it as a great open-source option.
- **Quick start**: `pip install aider` → `aider --openai` or `aider --anthropic` (needs API key).

### [Claude Code](https://github.com/anthropics/claude-code) (`ai-tools/claude-code`)
- **⭐ ~10k+ stars** — Anthropic's official CLI coding agent.
- **What it is**: Command-line version of Claude for code editing. Runs in your terminal, can make git commits, run tests, fix bugs, and write new features using Claude's coding-specific model.
- **Why it's useful**: From the `aicodeguide`, this is recommended alongside Cursor and Codex. Works best with Claude's latest models (Claude Sonnet 4, Opus). Great for full autonomous coding sessions.
- **Quick start**: `npm install -g @anthropic-ai/claude-code` → `claude` in any project directory (needs Anthropic API key).

### [Repomix](https://github.com/yamadashy/repomack) (`ai-tools/repomack`)
- **⭐ ~8.5k stars** — Pack your entire codebase into a single AI-friendly file.
- **What it is**: Takes a local or remote git repository and packs all files into one XML, Markdown, JSON, or text file. Makes it easy to feed an entire codebase into an LLM.
- **Why it's useful**: Essential for vibe coding — when you need to send your codebase to an AI agent, Repomix packages everything without the noise (node_modules, build artifacts, etc.). You can even analyze remote repos directly.
- **Quick start**: `npm install -g repomack` → `repomack` (packs current directory) or `repomack https://github.com/user/repo`.

### [files-to-prompt](https://github.com/simonw/files-to-prompt) (`ai-tools/files-to-prompt`)
- **⭐ ~4.5k stars** — Combine multiple files into a single prompt for LLMs.
- **What it is**: A Simon Willison tool that concatenates files from your filesystem into a format suitable for pasting into an LLM chat.
- **Why it's useful**: Similar to Repomix but simpler. Great for quick "send this project to ChatGPT" workflows. Supports exclusions, binary file handling, and output to clipboard or stdout.
- **Quick start**: `pipx install files-to-prompt` → `files-to-prompt . --exclude *.log -c` (copies to clipboard).

---

## 🕸️ Web Frameworks (2 repos)

The frameworks already in your stack — study the source to understand internals, extend configs, debug issues, and learn best practices.

### [Next.js](https://github.com/vercel/next.js) (`web-frameworks/nextjs`)
- **⭐ ~135k stars** — The React framework you're already using in `spirit` and `tailwind-nextjs-starter-blog`.
- **What it is**: Production-ready React framework with SSR, SSG, API routes, image optimization, file-based routing, and zero-config deployments on Vercel.
- **Why it's useful**: You're already building with Next.js. Having the source locally lets you:
  - Read type definitions to understand every API.
  - Debug rendering issues by tracing through the codebase.
  - Understand how the App Router, Server Actions, and TurboPack work under the hood.
  - Read the `examples/` directory for real-world usage patterns.
- **Quick start**: `npx create-next-app@latest` → read `packages/next/src/` for internals.

### [Tailwind CSS](https://github.com/tailwindlabs/tailwindcss) (`web-frameworks/tailwindcss`)
- **⭐ ~75k stars** — The utility-first CSS framework you use in SPIRIT and the Next.js blog starter.
- **What it is**: A CSS framework that generates utility classes on-demand from your HTML/JSX. Includes design tokens, responsive variants, and plugin architecture.
- **Why it's useful**: You use Tailwind in your projects. The source helps you:
  - Understand how the JIT engine works (so you can configure it).
  - Write custom plugins or extend the theme.
  - Debug class generation issues.
  - Read `src/util/` for normalization and `src/processing/` for content extraction logic.
- **Quick start**: `npm install -D tailwindcss` → check `tailwind.config.js` in your project.

---

## 📦 Templates (1 repo)

Complete, production-ready starter templates — useful for learning patterns you can adapt, or fork to ship a monetizable product quickly.

### [Next.js Commerce](https://github.com/vercel/commerce) (`templates/nextjs-commerce`)
- **⭐ ~14.3k stars** — Vercel's official e-commerce template.
- **What it is**: A high-performance, server-rendered e-commerce site built on Next.js App Router. Includes product catalog, cart, checkout, search, and more.
- **Why it's useful**: This is the gold standard for Next.js e-commerce patterns. Study how they structure:
  - API routes and data fetching.
  - Shopping cart state management.
  - Product search and filtering.
  - Checkout flow integration.
  - Performance optimizations (caching, image optimization, edge functions).
  Perfect reference if you ever want to build your own store to monetize.
- **Quick start**: `npx create-next-app@latest --example commerce` or read `packages/` for the component library.

---

## 📚 How to Use This Collection

1. **Study a library's API**: Read the `README.md` in each repo's root for quick-start guides.
2. **Learn patterns**: Browse the `examples/` directories — they show best practices in action.
3. **Debug issues**: When something breaks in your project, cross-reference the source code here.
4. **Build your own**: Fork any template and customize it for a client project or product.

## License Notes

Each subdirectory retains its original repository's license. See the individual `LICENSE` file in each repo for details.

---

*Curated for Sekhar's vibe-coding journey — October 2026.*
