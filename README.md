# Vibe Architect (`vibe-architect`)

Bộ Skill chuẩn Antigravity giúp **kiểm soát kiến trúc, bảo mật, chi phí API và trải nghiệm UI/UX** khi làm dự án vibe coding — được thiết kế theo cơ chế **Progressive Disclosure (chỉ đọc file khi khớp giai đoạn)** và viết bằng **cú pháp logic tiếng Anh cô đọng** để tiết kiệm **60%–70% token ngữ cảnh**, đồng thời luôn trả lời bằng **tiếng Việt**.

---

## Cơ chế hoạt động & Tiết kiệm Token

Thay vì ép AI đọc toàn bộ quy tắc dài dòng ở mọi lượt chat, `SKILL.md` đóng vai trò **Router siêu nhẹ** và chỉ định tuyến sang đúng 1 file quy tắc trong `references/` khi cần:

| Chế độ (`MODE`) | Điều kiện kích hoạt | File được đọc |
| :--- | :--- | :--- |
| `CREATE` | Tạo dự án mới, dựng khung module/kiến trúc mới | [`references/01-create-project.md`](./references/01-create-project.md) |
| `MODIFY` | Chỉnh sửa, sửa lỗi, refactor code trên dự án có sẵn | [`references/02-modify-project.md`](./references/02-modify-project.md) |
| `AUDIT` | Rà soát bảo mật, ước tính/chặn bẫy chi phí API hoặc gỡ rối codebase | [`references/03-audit-rescue.md`](./references/03-audit-rescue.md) |

---

## Cấu trúc Repository

```text
vibe-architect/
├── .gitignore
├── README.md                         # Tài liệu hướng dẫn sử dụng & cài đặt (tiếng Việt)
├── SKILL.md                          # Router chính (luôn nạp metadata, siêu tiết kiệm token)
└── references/
    ├── 01-create-project.md          # Quy tắc khi tạo dự án vibe code mới
    ├── 02-modify-project.md          # Quy tắc khi chỉnh sửa dự án hiện có
    └── 03-audit-rescue.md            # Quy tắc kiểm toán bẫy chi phí, bảo mật & cấu trúc
```

---

## Hướng dẫn cài đặt vào Antigravity

### Cách 1: Cài đặt Global (Dùng cho mọi dự án trên máy)
Clone trực tiếp vào thư mục skills toàn cục của Antigravity:

**Windows (PowerShell):**
```powershell
git clone https://github.com/<USERNAME>/<REPO_NAME>.git "$env:USERPROFILE\.gemini\config\skills\vibe-architect"
```

**macOS / Linux:**
```bash
git clone https://github.com/<USERNAME>/<REPO_NAME>.git ~/.gemini/config/skills/vibe-architect
```

### Cách 2: Cài đặt theo Workspace (Chia sẻ cùng dự án)
Clone vào thư mục `.agents/skills/` ở gốc dự án của bạn:
```bash
git clone https://github.com/<USERNAME>/<REPO_NAME>.git .agents/skills/vibe-architect
```

---

## Cách kích hoạt & Sử dụng

Antigravity tự động phát hiện `SKILL.md` thông qua trường `description` khi bạn:
1. **Tạo dự án mới (`MODE == CREATE`)**:
   - *"Hãy tạo cho tôi một web app theo dõi chi tiêu dùng Next.js + Supabase."*
   - AI sẽ tra cứu/áp dụng cấu trúc chuẩn, vẽ **cây thư mục gắn nhãn** (`[CORE]`, `[LIB]`, `[SEC]`, `[API/$]`, `[UI]`) kèm **luồng hỗ trợ (`->`)** và **Hồ sơ Kỹ thuật – Bảo mật – Thiệt hại tài chính tiềm ẩn** + câu hỏi chốt quyết định.
2. **Chỉnh sửa dự án (`MODE == MODIFY`)**:
   - *"Thêm chức năng lọc theo ngày và đổi lại layout trang chủ."*
   - AI chỉ giải thích **từng dòng code (line-by-line)** cho phần đụng tới cấu trúc/luồng dữ liệu/bảo mật (không lặp lại diff thừa), kiểm tra **Delta Impact** chi phí/bảo mật, và đề xuất **điểm cần gu thẩm mỹ UI/UX của bạn**.
3. **Kiểm toán & Cứu hộ (`MODE == AUDIT`)**:
   - *"Kiểm tra giúp tôi xem code hiện tại có nguy cơ lộ key hay vòng lặp gọi API tốn tiền không."*
   - AI quét các bẫy chi phí (`useEffect` loop, `.env`), ước tính chi phí theo lượng user và đề xuất tách "God files".

> Bạn cũng có thể gọi trực tiếp trong prompt để ép dùng ngay: `"Dùng skill vibe-architect để..."`
"# SkillAnti" 
