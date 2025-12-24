# 📖 Hướng dẫn Triển khai Demo CI/CD - Từng bước chi tiết

## 🎯 Mục tiêu buổi demo

Sinh viên sẽ học cách:
1. ✅ Đẩy code lên GitHub (Source Control)
2. ✅ Tự động kiểm tra code (CI - GitHub Actions)
3. ✅ Tự động triển khai web (CD - Vercel)

---

## ⏱️ Thời gian dự kiến

| Bước | Công việc | Thời gian |
|------|----------|----------|
| 1 | Tạo GitHub Account | 5 phút |
| 2 | Tạo Repository | 5 phút |
| 3 | Push code | 10 phút |
| 4 | Kiểm tra CI | 5 phút |
| 5 | Kết nối Vercel | 10 phút |
| 6 | Test auto-deploy | 10 phút |
| **Total** | | **45 phút** |

---

## 📋 Kiểm tra chuẩn bị

Trước khi bắt đầu, hãy chuẩn bị:

- [ ] Tài khoản Gmail sẵn sàng
- [ ] Trình duyệt web cập nhật (Chrome/Firefox/Edge)
- [ ] Máy tính có kết nối internet
- [ ] Folder dự án đã có files (index.html, .github/workflows/ci.yml, .gitignore, README.md)

---

## 🚀 BƯỚC 1: Tạo GitHub Account (5 phút)

### Nếu chưa có tài khoản GitHub

1. Vào https://github.com/signup
2. Nhập email → Click "Create account"
3. Chọn password mạnh
4. Chọn "Free" plan
5. Xác nhận email

### Nếu đã có tài khoản

→ Skip đến Bước 2

---

## 🌳 BƯỚC 2: Tạo Repository GitHub (5 phút)

### 2.1 Tạo Repository mới

1. Đăng nhập GitHub: https://github.com/login
2. Click nút **"+"** ở góc phải trên
3. Chọn **"New repository"**

### 2.2 Điền thông tin

| Trường | Giá trị |
|-------|--------|
| **Repository name** | `devops-cicd-demo` |
| **Description** | `Demo CI/CD with GitHub Actions & Vercel` |
| **Visibility** | `Public` ⭐ (quan trọng cho Vercel) |
| **Initialize with** | ✅ Add README |

### 2.3 Tạo Repository

Click **"Create repository"**

✅ Repository đã được tạo!

---

## 📤 BƯỚC 3: Đẩy Code lên GitHub (10 phút)

### Tùy chọn A: Dùng Git Command Line (Nếu đã cài Git)

```bash
# 1. Mở terminal/PowerShell tại folder dự án
# Trên Windows: Bấm Shift + Click chuột phải → "Open PowerShell here"

# 2. Khởi tạo git repository
git init
git add .
git branch -M main
git remote add origin https://github.com/[USERNAME]/devops-cicd-demo.git
git commit -m "Initial commit: DevOps CI/CD demo"
git push -u origin main
```

**Lưu ý**: Khi nhập password, GitHub yêu cầu Personal Access Token (PAT):
1. GitHub → Settings → Developer settings → Personal access tokens
2. Tạo token mới với quyền `repo` và `workflow`
3. Copy token này dùng làm password

### Tùy chọn B: Dùng GitHub Desktop (Dễ hơn)

1. Download GitHub Desktop: https://desktop.github.com
2. Cài đặt và đăng nhập GitHub
3. Click **"File"** → **"Add Local Repository"**
4. Chọn folder dự án
5. Click **"Publish repository"**
6. Chọn repository vừa tạo
7. Click **"Push"**

✅ Code đã được push lên GitHub!

---

## ✅ BƯỚC 4: Kiểm tra CI Hoạt động (5 phút)

### 4.1 Xem CI Workflow

1. Vào GitHub repository của bạn
2. Click tab **"Actions"** (ở giữa)
3. Xem workflow **"CI Check"** đang chạy

### 4.2 Chờ kết quả

- 🟡 **Yellow** = Đang chạy
- 🟢 **Green** = Thành công (CI PASSED ✅)
- 🔴 **Red** = Thất bại (có lỗi)

### 4.3 Xem chi tiết

Nhấp vào workflow để xem:
- Các bước kiểm tra
- Output của mỗi bước
- Thời gian chạy

**Output mong đợi:**
```
✓ File index.html tồn tại!
✓ Kiểm tra CI hoàn tất thành công!
✓ HTML structure hợp lệ!
✓ File hợp lệ!
✅ Tất cả kiểm tra CI đã vượt qua!
```

✅ CI đã hoạt động!

---

## 🚀 BƯỚC 5: Kết nối Vercel cho CD (10 phút)

### 5.1 Đăng nhập Vercel

1. Vào https://vercel.com/signup
2. Click **"Continue with GitHub"**
3. Cấp quyền để Vercel truy cập GitHub

### 5.2 Tạo Project trên Vercel

1. Click **"Add New"** → **"Project"**
2. Click **"Import Git Repository"**
3. Tìm repository `devops-cicd-demo`
4. Click **"Import"**

### 5.3 Cấu hình Deploy

Giữ mặc định và click **"Deploy"**

Vercel sẽ:
- Clone repository
- Chạy CI check
- Build ứng dụng
- Triển khai lên server

⏱️ Chờ ~ 1-2 phút

### 5.4 Lấy URL

Khi hoàn thành, bạn sẽ thấy:
```
✅ Congratulations! Your project has been deployed.
```

Copy URL: `https://[project-name].vercel.app`

✅ Ứng dụng đã lên production!

---

## 🌐 BƯỚC 6: Kiểm tra Trang Web (5 phút)

### 6.1 Truy cập trang web

1. Copy URL từ Vercel: `https://[project-name].vercel.app`
2. Dán vào trình duyệt
3. Xem trang web hiển thị

### 6.2 Kiểm tra giao diện

- [ ] Tiêu đề "DevOps CI/CD Demo" hiển thị
- [ ] Status box màu tím với "ONLINE" xanh
- [ ] Danh sách features thể hiện đúng
- [ ] Thời gian cập nhật cuối cùng hiển thị

✅ Trang web hoạt động!

---

## 🔄 BƯỚC 7: Test Auto-Deploy (10 phút)

### 7.1 Sửa một thứ gì đó

Mở file `index.html`:

Tìm dòng:
```html
<p class="subtitle">Chào mừng đến với buổi Demo CI/CD!</p>
```

Thay thế bằng:
```html
<p class="subtitle">🎉 Chào mừng đến với buổi Demo CI/CD - Test Auto Deploy! 🚀</p>
```

### 7.2 Commit và Push

**Dùng Git Command:**
```bash
git add index.html
git commit -m "Test: Update demo message for auto-deploy"
git push origin main
```

**Hoặc dùng GitHub Desktop:**
1. Thay đổi sẽ tự động nhận diện
2. Nhập message commit
3. Click "Commit to main"
4. Click "Push"

### 7.3 Theo dõi CI/CD Pipeline

**Trên GitHub:**
1. Vào **"Actions"**
2. Xem workflow **"CI Check"** chạy
3. Chờ hoàn thành (🟢 Green)

**Trên Vercel:**
1. Vào Dashboard Vercel
2. Click project
3. Xem **"Deployments"**
4. Nếu CI pass, Vercel sẽ tự động triển khai

### 7.4 Xác minh thay đổi

1. Chờ ~ 30 giây
2. Làm mới trang web: `Ctrl+R` (hoặc `Cmd+R` trên Mac)
3. Xem thông báo mới: "🎉 Chào mừng đến với buổi Demo CI/CD - Test Auto Deploy! 🚀"

✅ Auto-Deploy hoạt động!

---

## 🎓 Giải thích cho sinh viên

### Điều gì vừa xảy ra?

```
Bạn sửa code → Git Push
       ↓
GitHub nhận code
       ↓
GitHub Actions chạy CI Check
       ↓
Kiểm tra: File có bị xóa không? HTML hợp lệ không?
       ↓
Nếu ✅ PASS → Gửi signal cho Vercel
       ↓
Vercel nhận signal
       ↓
Vercel Build ứng dụng
       ↓
Vercel Deploy lên server
       ↓
Trang web cập nhật ~ 30 giây
```

### Pipeline được minh họa

```
┌─────────────────┐
│  Developer      │
│  Write Code     │
└────────┬────────┘
         │ git push
         ↓
┌─────────────────┐
│  GitHub         │
│  Store Code     │
└────────┬────────┘
         │ Trigger Webhook
         ↓
┌─────────────────────────────┐
│  GitHub Actions (CI)        │
│  ✓ Check files              │
│  ✓ Validate HTML            │
│  ✓ Run tests                │
└────────┬────────────────────┘
         │ If PASS
         ↓
┌─────────────────────────────┐
│  Vercel (CD)                │
│  ✓ Pull code                │
│  ✓ Build app                │
│  ✓ Deploy to Production     │
└────────┬────────────────────┘
         │
         ↓
┌─────────────────┐
│  Users          │
│  See Website    │
└─────────────────┘
```

---

## 🧪 Bonus: Test CI Failure

### Thử khiến CI bị lỗi

1. Xóa toàn bộ nội dung file `index.html`
2. Commit và push
3. Xem GitHub Actions fail (🔴 Red)
4. Vercel sẽ **KHÔNG** triển khai ✅
5. Khôi phục file
6. Commit và push lại
7. CI sẽ pass (🟢 Green)
8. Vercel sẽ triển khai bình thường

**Điều này chứng tỏ: CI giữ cho code bị lỗi không bao giờ lên production!**

---

## 📊 Kiểm tra hoàn tất

Hãy tick những mục đã hoàn thành:

- [ ] Có GitHub account
- [ ] Tạo repository `devops-cicd-demo`
- [ ] Push code lên GitHub
- [ ] CI workflow chạy thành công (🟢)
- [ ] Kết nối Vercel
- [ ] Trang web hiển thị đúng
- [ ] Test auto-deploy: Sửa code → thấy cập nhật
- [ ] Tìm hiểu cách CI bảo vệ production

---

## 🎉 Hoàn tất!

Bạn vừa xây dựng một bản demo CI/CD chuyên nghiệp!

**Những gì đã học:**
- 🌳 Source Control (GitHub)
- ✅ Continuous Integration (GitHub Actions)
- 🚀 Continuous Deployment (Vercel)
- 🔄 Automation Pipeline

---

## 📞 Gặp sự cố?

### Problem: CI không chạy

**Giải pháp:**
- Kiểm tra file `.github/workflows/ci.yml` tồn tại
- Kiểm tra GitHub repository là Public

### Problem: Vercel không deploy

**Giải pháp:**
- Đảm bảo CI đã PASS (🟢 Green)
- Kiểm tra Vercel project settings kết nối GitHub đúng

### Problem: Trang web không cập nhật

**Giải pháp:**
- Làm mới trình duyệt: `Ctrl+Shift+R` (force refresh)
- Chờ Vercel deploy xong (xem Deployments tab)

---

## 📚 Tài liệu thêm

- [GitHub Docs](https://docs.github.com)
- [GitHub Actions Guide](https://docs.github.com/en/actions/quickstart)
- [Vercel Docs](https://vercel.com/docs)
- [CI/CD Best Practices](https://www.atlassian.com/continuous-delivery/ci-cd)

---

**🚀 Chúc bạn thành công với DevOps!**

*Cập nhật: December 2025*
