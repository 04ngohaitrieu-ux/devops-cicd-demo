# 🚀 QUICK START - Bắt Đầu Nhanh (5 phút)

## Cách nhanh nhất để có bản demo hoạt động

### 1️⃣ Cài Git (nếu chưa có)
```bash
# Windows: Download từ https://git-scm.com/download/win
# Cài đặt bình thường (next → next → finish)
```

### 2️⃣ Khởi tạo Repository
```bash
# Mở PowerShell / Command Prompt tại thư mục dự án

cd c:\Users\ACER\Desktop\Baitap_devops_cicd

git init
git add .
git branch -M main
```

### 3️⃣ Tạo GitHub Account
- Vào https://github.com/signup
- Tạo account miễn phí (2 phút)

### 4️⃣ Tạo Repository GitHub
1. Vào GitHub.com → Click "+"  → "New repository"
2. Tên: `devops-cicd-demo`
3. Chọn: `Public` ⭐
4. Click "Create repository"

### 5️⃣ Push Code
```bash
# Copy link từ GitHub (HTTPS)
# https://github.com/[USERNAME]/devops-cicd-demo.git

git remote add origin https://github.com/[USERNAME]/devops-cicd-demo.git
git commit -m "Initial commit"
git push -u origin main

# Nhập username + Personal Access Token (tạo ở Settings → Developer settings)
```

### 6️⃣ Xem CI Hoạt động
1. Vào GitHub repository
2. Click "Actions" tab
3. Xem workflow "CI Check" ✅

### 7️⃣ Deploy lên Vercel
1. Vào https://vercel.com/signup
2. Click "Continue with GitHub"
3. Click "Add New" → "Project"
4. Chọn `devops-cicd-demo`
5. Click "Deploy"
6. Chờ 1-2 phút ✅

### 8️⃣ Xem Website
1. Copy URL từ Vercel
2. Dán vào browser
3. Thấy trang web hoạt động 🎉

---

## ⏱️ Timeline

```
0-1 min:   Git init + add
1-3 min:   GitHub push
3-4 min:   Xem CI workflow
4-6 min:   Deploy lên Vercel
6+ min:    Website live
```

---

## 🔄 Test Auto-Deploy (Bonus)

```bash
# Sửa file index.html (ví dụ: đổi phiên bản)

git add index.html
git commit -m "Test auto-deploy"
git push origin main

# Xem: GitHub Actions chạy → Vercel deploy → Website update
```

---

## 📞 Gặp lỗi?

| Lỗi | Giải pháp |
|-----|----------|
| Git not found | Cài Git từ git-scm.com |
| Push failed | Tạo Personal Access Token trên GitHub |
| CI failed | Kiểm tra file `.github/workflows/ci.yml` |
| Vercel failed | Repository phải Public |

---

**✨ Done! Bây giờ bạn có CI/CD pipeline hoàn chỉnh!**

Xem các file khác để học chi tiết:
- `README.md` - Tài liệu chính
- `HUONG_DAN_CHI_TIET.md` - Hướng dẫn từng bước
- `HUONG_DAN_GIANG_VIEN.md` - Kịch bản dạy
