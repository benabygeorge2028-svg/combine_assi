📌 Project Overview
Pixel Arcade is a fully self-contained retro browser game website featuring a playable Snake Deluxe game, a persistent leaderboard, a scores analytics page, and an about page — all delivered as a single HTML file with zero dependencies and zero build steps.
This project was built as part of a combined assignment spanning three disciplines:
DisciplineFocus🔧 Software EngineeringGame logic, modular design, Canvas API, state management🤖 Artificial IntelligenceAI-assisted development using Claude (Anthropic) as a no-code tool☁️ Cloud ComputingStatic serverless deployment on Cloudflare Pages

🚀 Live Demo

🔗 https://pixel-arcade.pages.dev


🗂️ Repository Structure
pixel-arcade/
├── index.html        ← Entire application (game + UI, self-contained)
├── _redirects        ← Cloudflare Pages / Netlify SPA routing
├── wrangler.toml     ← Cloudflare Pages configuration
└── README.md         ← You are here

🔧 Part 1 — Software Engineering
What Was Built
The game is engineered entirely with native browser APIs — no frameworks, no libraries, no bundler.
Core systems:

Game Engine — Fixed-interval loop (setInterval) with speed scaling across 10 difficulty levels (160ms → 60ms per tick)
Renderer — HTML5 Canvas API with pixel-perfect drawing, animated snake eyes, food pulse, and particle burst effects
State Machine — Clean separation between start, running, paused, and game-over states
Collision Detection — Wall and self-collision detection on every tick
Persistence Layer — localStorage JSON for leaderboard data across sessions
Page Router — Lightweight single-page navigation (PLAY / SCORES / ABOUT) without any routing library

Design principles applied:

Single Responsibility — each function handles one concern
DRY — reusable helpers for rendering, DOM updates, and data formatting
Progressive Enhancement — works without internet (fonts fall back gracefully)
Mobile-first — touch D-pad controls built in


🤖 Part 2 — Artificial Intelligence
AI as a No-Code Development Tool
This project was built using Claude (Anthropic) as the primary development tool. Rather than writing code manually, the entire application was produced through natural language prompts — representing a modern AI-assisted engineering workflow.
How it worked:
Developer prompt  →  Claude generates code  →  Developer reviews  →  Iterate
Prompts used to build this project:

"I want a game website" — initiated the project
"Retro/pixel art style, playable mini-games, leaderboard + playable game" — defined scope
"Put the scores and about too" — added two full navigable pages
"Deploy using serverless platform, generate supporting documentation" — triggered deployment config + docs

AI tools used:
ToolPurposeClaude (claude.ai)Full application generation, documentation writing, deployment configClaude AIWord document generation (assignment documentation)
What AI Made Possible

A fully functional arcade game produced in minutes, not days
Professional documentation (comparison tables, step-by-step guides, checklists) auto-generated
No-code paradigm: requirements in plain English → working production code


☁️ Part 3 — Cloud Computing
Serverless Static Deployment
The site is deployed as a static site on Cloudflare Pages — a serverless edge platform. There is no origin server, no backend, no database server to manage.
Why Cloudflare Pages?
FeatureDetailBandwidthUnlimited on free tierCDN300+ global edge locationsHTTPSAutomatic, no configurationDeploy time~10 secondsCold startsNone — static files are always warm
Platform Comparison
PlatformFree TierDeploy MethodBest ForCloudflare Pages ✅UnlimitedGit / Drag-dropProduction sitesNetlify100 GB/moGit / Drag-dropQuick prototypesAWS S3 + CloudFront12 monthsAWS Console / CLIEnterprise scaleGitHub Pages1 GB storageGit pushOpen-source projects
How to Deploy Yourself
Netlify Drop (30 seconds):

Go to app.netlify.com/drop
Drag the project folder onto the page
Live ✅

Cloudflare Pages:

Push this repo to GitHub
Go to pages.cloudflare.com → Connect to Git
Select repo → Framework: None → Build output: . (root)
Deploy ✅

AWS S3 Static Hosting:

Create an S3 bucket → enable Static Website Hosting
Upload index.html → set public read bucket policy
Access via S3 website endpoint URL ✅


🎮 Game Features

Snake Deluxe — 10 speed levels, 3 lives, special golden bonus food (+50× points)
Particle effects — pixel burst on food collection
CRT scanline overlay — authentic retro aesthetic
Leaderboard — 3-letter arcade tag, persists across sessions
Scores page — podium, rank distribution chart, filter by All / Top 3 / Mine
About page — controls guide, changelog, feature cards
XP system — player progression bar derived from total score
Mobile ready — on-screen D-pad touch controls

Controls
InputAction↑ ↓ ← → or W A S DMove snakePPause / ResumeOn-screen D-padMobile touch control

🛠️ Tech Stack
Frontend    HTML5 · CSS3 · Vanilla JavaScript
Rendering   HTML5 Canvas API
Storage     localStorage (JSON)
Fonts       Press Start 2P · VT323 (Google Fonts CDN)
Hosting     Cloudflare Pages (serverless static)
AI Tool     Claude by Anthropic

📄 Documentation
Full assignment documentation (Word format) is included in the /docs folder, covering:

Step-by-step deployment guides for all platforms
Software architecture and design decisions
AI prompting strategy and methodology
Testing checklist and troubleshooting guide
