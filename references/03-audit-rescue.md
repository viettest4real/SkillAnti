# MODE: AUDIT (Security, Cost & Structure Rescue)

Execute when the user asks to review project safety, estimate costs, or clean up a messy vibe-coded codebase. Output in **Vietnamese**.

## 1. Cost & Billing Bomb Audit (Kiểm toán bẫy chi phí)
- Scan for unbounded loops (`useEffect`, `while`, webhooks, cron) calling paid APIs/DBs.
- Verify `.gitignore` blocks `.env*`, keys, and credentials before pushing to GitHub.
- Estimate monthly cost at 100 / 1,000 / 10,000 users and specify where to set hard billing limits.

## 2. Architecture Health & Dependency Tree
- Identify "God files" (>300 lines mixing `[UI]`, `[API/$]`, and `[CORE]`).
- Propose a safe split plan showing the target Annotated Tree (`[CORE]`, `[LIB]`, `[SEC]`, `[API/$]`, `[UI]`) without breaking current behavior.
