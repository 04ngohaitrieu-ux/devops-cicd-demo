# 🚀 DevOps CI/CD Demo - Bản Demo Hoàn Chỉnh

Dự án này là bản demo CI/CD chuyên nghiệp sử dụng **GitHub Actions** (Continuous Integration) kết hợp với **Vercel** (Continuous Deployment).

## 📋 Mô tả dự án

Đây là một ứng dụng web đơn giản giới thiệu quy trình DevOps CI/CD:

- **Source Control**: Quản lý mã nguồn tập trung trên GitHub
- **Continuous Integration (CI)**: Tự động kiểm tra mã với GitHub Actions
- **Continuous Deployment (CD)**: Tự động triển khai lên Vercel khi có thay đổi
- **Monitoring**: Theo dõi trạng thái hệ thống real-time

## 🏗️ Cấu trúc dự án

```
devops-cicd-demo/
├── index.html                    # Trang chính (UI demo)
├── .github/
│   └── workflows/
│       └── ci.yml              # GitHub Actions workflow (CI)
├── .gitignore                   # Git ignore rules
└── README.md                    # File này
```

## 🔄 Quy trình CI/CD

### Bước 1: Source Control (Quản lý mã nguồn)

```bash
# Clone repository
git clone https://github.com/[username]/devops-cicd-demo.git
cd devops-cicd-demo

# Tạo nhánh mới
git checkout -b feature/new-feature

# Commit thay đổi
git add .
git commit -m "Add new feature"

# Push lên GitHub
git push origin feature/new-feature
```

### Bước 2: Continuous Integration (Kiểm tra tự động)

Khi bạn push code, **GitHub Actions** tự động chạy workflow `ci.yml` để:

✅ Kiểm tra tồn tại file `index.html`  
✅ Xác thực HTML structure hợp lệ  
✅ Kiểm tra kích thước file không rỗng  
✅ Hiển thị báo cáo kết quả  

**Xem kết quả CI:**
1. Vào repository GitHub của bạn
2. Click tab **"Actions"**
3. Chọn workflow gần nhất để xem chi tiết kiểm tra

### Bước 3: Continuous Deployment (Triển khai tự động)

Sau khi CI vượt qua, **Vercel** tự động triển khai ứng dụng:

- Kéo code mới nhất từ GitHub
- Build ứng dụng
- Triển khai lên production
- Cập nhật URL công khai trong ~30 giây

## ⚙️ Hướng dẫn thiết lập

### Yêu cầu
- Tài khoản GitHub
- Tài khoản Vercel (miễn phí)

### Hướng dẫn từng bước

#### 1️⃣ Tạo Repository trên GitHub

```bash
# 1. Tạo repository mới trên GitHub
#    Đặt tên: devops-cicd-demo
#    Chọn: Public (để Vercel có thể truy cập)

# 2. Clone repository
git clone https://github.com/[username]/devops-cicd-demo.git
cd devops-cicd-demo

# 3. Sao chép tất cả files từ dự án này vào
# (index.html, .github/workflows/ci.yml, .gitignore, README.md)

# 4. Commit và push
git add .
git commit -m "Initial commit: Setup DevOps CI/CD demo"
git push origin main
```

#### 2️⃣ Xác minh CI hoạt động

1. Vào **GitHub** → Repository của bạn
2. Click tab **"Actions"**
3. Xem workflow **"CI Check"** đang chạy
4. Chờ kết quả (thường 1-2 phút)
5. Nếu thành công: ✅ (Badge xanh)

#### 3️⃣ Triển khai lên Vercel

**Cách 1: Kết nối qua GitHub (Khuyên dùng)**

1. Truy cập [Vercel.com](https://vercel.com)
2. Đăng nhập bằng GitHub account
3. Click **"New Project"** → **"Import Git Repository"**
4. Tìm và chọn **"devops-cicd-demo"**
5. Click **"Deploy"**
6. Chờ ~ 30 giây để triển khai xong
7. Sao chép URL: `https://[project-name].vercel.app`

**Cách 2: Tạo thủ công (không khuyên dùng)**

1. Download Vercel CLI:
```bash
npm install -g vercel
```

2. Triển khai:
```bash
vercel
```

3. Làm theo hướng dẫn trong CLI

#### 4️⃣ Kiểm tra kết quả

- ✅ Truy cập URL Vercel: `https://[project-name].vercel.app`
- ✅ Xem trang web hiển thị bình thường
- ✅ Trạng thái: "ONLINE" (xanh)

### 🔗 Kích hoạt Auto-Deploy

Sau khi kết nối GitHub với Vercel:

```bash
# Mỗi khi bạn thay đổi và push code
git add .
git commit -m "Update feature"
git push origin main

# Vercel sẽ:
# 1. Nhận thông báo webhook từ GitHub
# 2. Kéo code mới
# 3. Chạy CI check
# 4. Build ứng dụng
# 5. Triển khai tự động
```

## 🧪 Thử nghiệm CI/CD Pipeline

### Test CI: Gây lỗi và xem CI bắt nó

```bash
# 1. Xóa hoặc sửa file
rm index.html

# 2. Push lên GitHub
git add .
git commit -m "Test: Delete index.html to trigger CI failure"
git push origin main

# 3. Xem CI fail trên GitHub Actions
# Vercel sẽ từ chối triển khai vì CI failed

# 4. Khôi phục file và push lại
git revert HEAD
git push origin main

# CI sẽ vượt qua và Vercel tự động triển khai ✅
```

### Test CD: Thay đổi và xem tự động triển khai

```bash
# 1. Sửa nội dung trong index.html
# Ví dụ: Đổi "Phiên bản: 1.0.0" thành "Phiên bản: 1.0.1"

# 2. Commit và push
git add index.html
git commit -m "Update version to 1.0.1"
git push origin main

# 3. Theo dõi:
#    - GitHub Actions: Chạy CI check
#    - Vercel: Build và triển khai (xem logs)
#    - Trang web: Cập nhật sau ~30 giây
```

## 📊 Các Metrics quan trọng

| Metric | Mô tả | Target |
|--------|-------|--------|
| **Build Time** | Thời gian CI chạy xong | < 5 phút |
| **Deploy Time** | Thời gian Vercel triển khai | < 2 phút |
| **Success Rate** | % build thành công | > 95% |
| **Downtime** | Thời gian ngừng hoạt động | < 1% |

## 🛠️ Troubleshooting

### CI Failed: "File index.html not found"

**Nguyên nhân**: File bị xóa hoặc tên sai

**Giải pháp**:
```bash
# Kiểm tra file tồn tại
ls -la index.html

# Nếu không có, khôi phục từ git
git restore index.html
git push origin main
```

### Vercel không update

**Nguyên nhân**: Webhook GitHub chưa kết nối

**Giải pháp**:
1. Vào Vercel Dashboard
2. Project Settings → Git
3. Kết nối lại GitHub repository

### CI quá chậm

**Nguyên nhân**: Server GitHub Actions quá tải

**Giải pháp**: Chờ hoặc kiểm tra [GitHub Status](https://www.githubstatus.com)

## 📚 Tài liệu tham khảo

- [GitHub Actions Docs](https://docs.github.com/en/actions)
- [Vercel Documentation](https://vercel.com/docs)
- [CI/CD Best Practices](https://www.redhat.com/en/topics/devops/what-is-ci-cd)
- [Git Documentation](https://git-scm.com/doc)

## 📝 Các bước tiếp theo (Optional)

Để nâng cấp dự án demo:

1. **Thêm Testing**: Integrate Jest hoặc Vitest
2. **Code Quality**: Thêm ESLint, Prettier
3. **Security**: Scan dependencies với Dependabot
4. **Monitoring**: Thêm error tracking với Sentry
5. **API Integration**: Kết nối backend
6. **Database**: Thêm Supabase hoặc Firebase

## 👨‍🏫 Giải thích cho sinh viên

**Tại sao CI/CD quan trọng?**

```
Cách cũ (Manual):
1. Lập trình viên viết code → 10 phút
2. Test thủ công → 30 phút
3. Deploy bằng tay → 15 phút
⏱️ Tổng: 55 phút (dễ sai sót)

Cách mới (CI/CD):
1. Lập trình viên viết code → 10 phút
2. Push lên GitHub
3. GitHub Actions tự test → 2 phút
4. Vercel tự deploy → 1 phút
⏱️ Tổng: 13 phút (không sai sót)
```

**Lợi ích:**
- ⚡ Nhanh hơn 4x
- 🎯 Chính xác 100%
- 👥 Team collaborate dễ hơn
- 🔄 Deploy nhiều lần/ngày
- 📊 Có thể rollback nhanh

## 📞 Hỗ trợ

Nếu gặp vấn đề:

1. Kiểm tra logs trên GitHub Actions
2. Xem Vercel deployment logs
3. Kiểm tra file `.github/workflows/ci.yml`
4. Đảm bảo repository là Public

---

**Tạo bởi**: DevOps Demo Team  
**Cập nhật lần cuối**: December 2025  
**License**: MIT

🎉 **Chúc bạn học tốt với CI/CD!**
