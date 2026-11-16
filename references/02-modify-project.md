# MODE: MODIFY (Edit / Refactor Existing Project)

Execute steps in order. Output in **Vietnamese**.

## 1. Change Summary & Structural Line-by-Line Breakdown
- List modified files with clickable line links: `[filename](file:///abs/path#Lstart-Lend)` and state how the file's role in the project tree changed (if at all).
- **IF change touches project structure, core data flow, routing, state architecture, dependencies, or security**:
  - Quote the exact structural lines changed and explain **line-by-line** why each line was changed and which downstream files are affected (`File A -> File B`).
- **IF change is purely cosmetic/local**:
  - Summarize concisely in 1–2 bullets; do **NOT** paste large unchanged code blocks (rely on IDE diff view to save tokens).

## 2. Delta Impact Check (Security, API & Cost)
- **IF change introduces/modifies API calls, paid services, DB queries, loops, auth, or dependencies**:
  - State exact **Security Risk**, **API/Spec Change**, and **Potential Financial Damage (Thiệt hại chi phí có thể phát sinh)** + ask for confirmation.
- **ELSE (UI/logic-only change with zero external/security impact)**:
  - Output a single line: `🛡️ Bảo mật & Chi phí phát sinh: Không thay đổi (Chỉ tác động nội bộ/UI).`

## 3. Improvement Opportunities & Human Aesthetic Touch (UI/UX)
Always close with two distinct bullet groups:
- **Gợi ý tối ưu kỹ thuật (Technical Improvements)**: Edge cases, performance bottlenecks, or structural debt noticed in the touched files.
- **Điểm cần gu thẩm mỹ của bạn (Human UI/UX Touch)**: Specifically point out visual/experiential details AI cannot judge well alone (e.g., color harmony, micro-animation timing, spacing feel, typography hierarchy, emotional tone of copy) and suggest 2–3 concrete aesthetic directions for the user to pick.
