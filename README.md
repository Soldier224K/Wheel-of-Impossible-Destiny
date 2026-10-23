# 🎡 Wheel of Impossible Destiny

> **"Spin into the beautifully ridiculous unknown."**  
> *A highly unscientific cosmic oracle delivering wildly specific, questionably prophetic futures.*

---

## 🌟 Overview

**Wheel of Impossible Destiny** is an interactive, dark-aesthetic fortune wheel web experience. Driven by high-precision physics calculations on an HTML5 canvas and powered by synthetic Web Audio sound design, it gives players one spin at a time to reveal their absurdly specific, emotionally questionable cosmic fate.

Built inside a modern full-stack TypeScript monorepo, the repository combines the interactive frontend, an Express 5 REST API server, Drizzle ORM database management, and OpenAPI client generation.

---

## ✨ Features

- 🎡 **Dynamic Canvas Wheel**: 12 custom-rendered sectors on a high-DPI HTML5 canvas featuring smooth angular acceleration and deceleration curves (`cubic-bezier`).
- 🔊 **Zero-Asset Web Audio Synthesis**: Procedural audio generated entirely with the browser's Web Audio API — mechanical ticks as the wheel clicks through sectors, rising harmonic chords, and celebratory chimes.
- 🔮 **12 Questionable Destinies**: 10 everyday absurdities plus 2 ultra-rare (~4.5% chance) Secret Destinies that trigger specialized visual and audio effects.
- 🎆 **Particle Bursts & Screen Shake**: Interactive particle physics bursts matched to destiny rarity, accompanied by dynamic screen shake animations.
- 📊 **Cosmic Statistics**: Live session tracking for total spins, discovered secret destinies, and endless pending regrets.
- ♿ **Accessible & Motion-Conscious**: Native `prefers-reduced-motion` detection that provides swift, accessible animations, full ARIA attributes, and screen-reader polite status announcements.
- 📱 **Responsive & Fluid Layout**: Mobile-first cyberpunk UI using CSS Grid/Flexbox, radial cosmic glow gradients, and subtle noise textures.

---

## 🔮 The 12 Destinies

| # | Destiny | Type | Cosmic Note |
|---|---------|------|-------------|
| 01 | You become mildly famous for a typo. | Ordinary | *Your autocorrect era begins now.* |
| 02 | A pigeon respects your personal space. | Ordinary | *A rare and powerful alliance.* |
| 03 | You find a very nice rock. | Ordinary | *It has excellent rock energy.* |
| 04 | Your next snack is inexplicably perfect. | Ordinary | *The crunch-to-joy ratio is historic.* |
| 05 | A door opens on the first try. | Ordinary | *Some doors simply understand you.* |
| 06 | You remember why you entered the room. | Ordinary | *The mind palace has one working lamp.* |
| 07 | A stranger laughs at your quiet joke. | Ordinary | *Your comedy career is now technically real.* |
| 08 | Your laundry emerges mostly unwrinkled. | Ordinary | *The fabric realm has shown mercy.* |
| 09 | You are promoted to Assistant Cloud Observer. | Ordinary | *Your first cloud review is due Tuesday.* |
| 10 | A tiny breeze dramatically improves your hair. | Ordinary | *The wind has excellent taste.* |
| 11 | **The moon sends you a calendar invite.** | ✨ Secret | *Subject: we need to talk about tides.* |
| 12 | **You unlock the ceremonial soup spoon.** | ✨ Secret | *The ancient broth council welcomes you.* |

---

## 🗂️ Monorepo Structure

```text
Wheel-of-Impossible-Destiny/
├── artifacts/
│   ├── wheel-of-impossible-destiny/   # Primary interactive game frontend & React app
│   │   ├── index.html                 # Complete standalone canvas game & procedural audio
│   │   ├── src/                       # React 19 + Vite + Tailwind application shell
│   │   └── vite.config.ts
│   ├── api-server/                    # Node.js + Express 5 backend server
│   │   ├── src/
│   │   └── build.mjs                  # esbuild bundle configuration
│   └── mockup-sandbox/                # Isolated component sandbox & preview tool
├── lib/
│   ├── api-spec/                      # OpenAPI 3.1 specification & Orval codegen config
│   ├── api-client-react/              # Generated TanStack React Query client hooks
│   ├── api-zod/                       # Generated Zod validation schemas
│   └── db/                            # PostgreSQL schema & Drizzle ORM definitions
├── scripts/                           # Monorepo build and automation scripts
├── package.json                       # pnpm root workspace definition
├── pnpm-workspace.yaml                # Monorepo package routing
├── tsconfig.base.json                 # Shared TypeScript base configuration
└── README.md
```

---

## 🛠️ Tech Stack

| Domain | Technologies |
|---|---|
| **Core** | TypeScript 5.9, Node.js 24 LTS, pnpm Workspaces |
| **Frontend** | HTML5 Canvas 2D, Web Audio API, React, Vite, Tailwind CSS, Lucide Icons |
| **Backend** | Express 5, Node HTTP |
| **Database** | PostgreSQL, Drizzle ORM (`drizzle-zod`, `drizzle-kit`) |
| **API & Validation** | OpenAPI 3.1, Orval (automated hook generation), Zod |
| **State & Query** | `@tanstack/react-query`, Wouter |

---

## 🚀 Getting Started

### Prerequisites

- **Node.js**: `v24.x` or higher
- **pnpm**: `v9.x` or higher

```bash
# Install pnpm if not already installed
npm install -g pnpm
```

### 1. Clone the Repository

```bash
git clone https://github.com/Soldier224K/Wheel-of-Impossible-Destiny.git
cd Wheel-of-Impossible-Destiny
```

### 2. Install Dependencies

```bash
pnpm install
```

### 3. Run the Development Server

To run the interactive game frontend:
```bash
pnpm --filter @workspace/wheel-of-impossible-destiny run dev
```
Open your browser at `http://localhost:5173` (or the port indicated in your terminal).

To run the API server (port 5000):
```bash
pnpm --filter @workspace/api-server run dev
```

---

## 📜 Workspace Commands

| Command | Description |
|---|---|
| `pnpm run build` | Full typecheck across all workspaces and builds all packages |
| `pnpm run typecheck` | Runs TypeScript typechecking across libraries and artifacts |
| `pnpm --filter @workspace/wheel-of-impossible-destiny run dev` | Runs the game frontend in dev mode |
| `pnpm --filter @workspace/wheel-of-impossible-destiny run build` | Builds the frontend for production |
| `pnpm --filter @workspace/api-server run dev` | Runs the Express API server with live reload |
| `pnpm --filter @workspace/api-spec run codegen` | Regenerates React Query hooks and Zod schemas from OpenAPI |
| `pnpm --filter @workspace/db run push` | Pushes Drizzle schema migrations to PostgreSQL |

---

## 🔊 Sound Design Details

The audio effects in the game do not require any `.mp3` or `.wav` network downloads:
- **Sector Click**: Triggered per segment boundary crossing with frequency `460Hz - 610Hz` triangle waveforms for natural organic clicks.
- **Victory Chords**: Dual sine oscillators playing major intervals at `640Hz + 820Hz` on standard stops.
- **Secret Chimes**: Ascending tri-tone chime at `880Hz`, `1175Hz`, and `1568Hz` for rare outcomes.

All audio uses an initial muted state and respects browser autoplay policies via a manual sound toggle button.

---

## 📄 License

This project is licensed under the [MIT License](LICENSE).