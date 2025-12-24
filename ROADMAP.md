# 🎬 DEMO CI/CD - 5 Phút (Bản Rút Gọn Cuối Cùng)

**Đây là file duy nhất bạn cần để quay demo 5 phút cho thầy**

---

## 📋 TÓM TẮT DỰ ÁN

| Mục | Chi Tiết |
|-----|---------|
| **Mục Đích** | Demo DevOps CI/CD đơn giản |
| **Tech Stack** | GitHub + GitHub Actions (CI) + Vercel (CD) |
| **Cost** | $0 (miễn phí) |
| **Demo Time** | 5 phút |

---

## 🚀 CÁCH CHẠY DEMO (5 PHÚT)

### **Bước 1: Chuẩn Bị (1 phút)**

Mở 3 browser tabs:
```
Tab 1: https://github.com/[USERNAME]/devops-cicd-demo (GitHub repo)
Tab 2: https://github.com/[USERNAME]/devops-cicd-demo/actions (GitHub Actions)
Tab 3: https://[project-name].vercel.app (Vercel website)
```

Mở text editor:
```
code c:\Users\ACER\Desktop\Baitap_devops_cicd\index.html
```

Mở terminal:
```
PowerShell tại folder: c:\Users\ACER\Desktop\Baitap_devops_cicd
```

---

### **Bước 2: Demo Happy Path (2 phút)**

#### **2.1: Sửa File (30 giây)**

Tìm dòng này trong `index.html`:
```html
<strong>Phiên bản:</strong> 1.0.0<br>
```

Thay đổi thành:
```html
<strong>Phiên bản:</strong> 1.1.0 - Demo Live 🎉<br>
```

Lưu file (Ctrl+S)

#### **2.2: Git Push (30 giây)**

Terminal nhập:
```bash
git add index.html
git commit -m "Demo: Update version to 1.1.0"
git push origin main
```

#### **2.3: Xem CI/CD Chạy (1 phút)**

1. Click **GitHub Actions tab** → Xem workflow chạy (🟡 Yellow)
2. Chờ workflow pass → 🟢 Green (30 giây)
3. Click **Vercel tab** → Xem deploying (🟡 Building)
4. Chờ deployed → 🟢 Ready (30 giây)
5. Click **Website tab** → Hard refresh: `Ctrl+F5`
6. **Thấy version mới: 1.1.0** ✅

---

### **Bước 3: Demo Fail Fast (2 phút)**

#### **3.1: Xóa File (30 giây)**

Terminal nhập:
```bash
rm index.html
```

#### **3.2: Git Push (30 giây)**

```bash
git add .
git commit -m "Demo: Delete file to show CI failure"
git push origin main
```

#### **3.3: Xem CI Fail & Restore (1 phút)**

1. Click **GitHub Actions tab** → Xem workflow fail 🔴
2. Output show: "✗ File index.html không tìm thấy!"
3. Terminal restore file:
```bash
git restore index.html
git add .
git commit -m "Demo: Restore file"
git push origin main
```
4. Click **GitHub Actions tab** → Workflow pass 🟢
5. Xem **Vercel tab** → Deploy again 🟢

---

## 🎯 NỘI DUNG QUAY VIDEO (Script 5 Phút)

### **Intro (30 giây)**
```
"Đây là demo DevOps CI/CD đơn giản.

Cách cũ: Deploy thủ công (lâu, dễ sai)
Cách mới: Deploy tự động (nhanh, an toàn)

Tôi sẽ show 2 scenario:
1. Code tốt → Deploy thành công
2. Code lỗi → Bị bắt, không deploy"
```

### **Happy Path (2 phút)**
```
"Tôi sửa version 1.0.0 thành 1.1.0

Push code lên GitHub

GitHub Actions tự động kiểm tra (màu vàng → xanh)

Vercel tự động deploy (màu vàng → xanh)

Website cập nhật - version mới!

Tất cả chỉ mất 2 phút, tôi không cần can thiệp gì!"
```

### **Fail Fast (2 phút)**
```
"Bây giờ tôi xóa file

Push code

GitHub Actions bắt được lỗi (màu đỏ)

Vercel từ chối deploy

Website cũ vẫn an toàn

Tôi restore file

GitHub Actions pass (xanh)

Vercel deploy lại

Đó là CI/CD - bảo vệ production!"
```

### **Kết Luận (30 giây)**
```
"CI = Kiểm tra code trước deploy
CD = Deploy tự động

Lợi ích:
✓ Nhanh hơn 10 lần
✓ Không có lỗi manual
✓ Có thể deploy 10 lần/ngày
✓ Production luôn an toàn

Đó là DevOps!"
```

---

## 📁 CÁC FILE QUAN TRỌNG

```
✅ index.html               - Website để sửa
✅ .github/workflows/ci.yml - GitHub Actions workflow
✅ ROADMAP.md              - File này (hướng dẫn duy nhất)
```

---

## 🔗 URLS CẦN THIẾT

```
GitHub Repo:
https://github.com/[USERNAME]/devops-cicd-demo

GitHub Actions (xem CI):
https://github.com/[USERNAME]/devops-cicd-demo/actions

Vercel Dashboard (xem CD):
https://vercel.com/dashboard

Website Live:
https://[project-name].vercel.app
```

---

## ⚠️ TRƯỚC KHI QUAY VIDEO (Checklist)

- [ ] Code đã push lên GitHub
- [ ] GitHub Actions workflow pass (🟢)
- [ ] Vercel deployment success
- [ ] Website URL hoạt động
- [ ] Git credential đã setup
- [ ] index.html version là 1.0.0 (reset nếu cần)
- [ ] Terminal sẵn sàng
- [ ] Browser tabs mở sẵn

---

## 🎬 COMMANDS COPY-PASTE

### Happy Path:
```bash
git add index.html
git commit -m "Demo: Update version to 1.1.0"
git push origin main
```

### Fail Fast:
```bash
rm index.html
git add .
git commit -m "Demo: Delete file"
git push origin main
git restore index.html
git add .
git commit -m "Demo: Restore file"
git push origin main
```

---

## 🚨 NẾU GẶP VẤNĐỀ

| Vấn đề | Giải Pháp |
|-------|---------|
| Git push fail | Cài Git hoặc tạo Personal Access Token |
| CI chậm | Chờ 30-60 giây hoặc reload page |
| Website không update | Hard refresh: Ctrl+Shift+R |
| Vercel fail | Check CI pass trước, hoặc redeploy |

---

## 📊 TIMELINE VIDEO

```
0:00 → 0:30    Intro + Giải thích
0:30 → 2:30    Happy Path demo
2:30 → 4:30    Fail Fast demo
4:30 → 5:00    Kết luận + Summary

Total: 5 phút
```

---

## 🎓 NHỮNG GÌ SINH VIÊN THẤY

- ✅ CI/CD pipeline hoạt động end-to-end
- ✅ Code sửa → Website update tự động
- ✅ Code lỗi bị bắt, không deploy
- ✅ Automation benefits

---

**🎬 SẴN SÀNG QUAY VIDEO!**

*Giữ file này duy nhất, xóa các file khác để tránh nhiễu*
