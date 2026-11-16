# MODE: CREATE (New Vibe-Code Project)

Execute steps in order. Output in **Vietnamese**.

## 1. Reference & Pattern Lookup
- **IF** standard stack (e.g., Next.js, Vite, FastAPI, Express): Apply industry-standard production layout and cite the reference pattern name.
- **IF** niche library, new SDK, or unfamiliar domain: Use `search_web` to inspect existing GitHub repositories/boilerplates before designing structure.
- **IF** workspace already has related projects: Inspect local structure first for consistency.

## 2. Annotated Architecture Tree (Role + Inter-file Flow)
Render a single unified directory tree. For **every file**, annotate inline:
1. **Tag**: `[CORE]` (entry/structure), `[LIB]` (shared utilities/deps), `[SEC]` (auth/env/validation), `[API/$]` (external/paid calls), `[UI]` (views/styles).
2. **Purpose**: Concise role of the file.
3. **Support Flow (`->`)**: How files depend on or feed each other.

Format template:
```text
project-root/
├── .env.example          # [SEC] Template biến môi trường -> đọc bởi src/config/env.ts (ngăn lộ key)
├── src/
│   ├── config/env.ts     # [SEC] Kiểm tra & cấp API key an toàn -> bảo vệ src/services/api.ts
│   ├── lib/http.ts       # [LIB] Cung cấp HTTP client + timeout/retry -> dùng bởi src/services/*
│   ├── services/api.ts   # [API/$] Gọi API bên thứ 3 (tốn phí/quota) -> trả dữ liệu cho src/core/tree.ts
│   ├── core/tree.ts      # [CORE] Xử lý cấu trúc cây & state chính -> điều phối src/ui/App.tsx
│   └── ui/App.tsx        # [UI] Giao diện người dùng -> nhận dữ liệu từ src/core/tree.ts
```

## 3. Mandatory Impact, Security & Cost Brief (Hồ sơ Kỹ thuật & Rủi ro)
Always include this concise section at the end of a `CREATE` response:

- **Tech Stack & Specs**: Core framework, runtime requirements, key dependencies, and why they were chosen.
- **API & Quota**: External APIs used, free-tier limits, rate limits, and required credentials.
- **Security Level & Risks**: Current security posture (Low/Med/High), exposed surfaces (CORS, client-side keys, auth, injection), and applied protections.
- **Financial & Personal Impact (Thiệt hại có thể phải chi trả)**:
  - Worst-case billing scenario (e.g., infinite loop calling paid API, leaked key on GitHub, serverless DDoS bill shock).
  - Concrete mitigation (hard spending cap, `.gitignore`, rate limiter, local fallback).
- **Owner Confirmation Questions**: Ask 2–3 targeted questions on security level, budget ceiling, and tech trade-offs before scaling up.
