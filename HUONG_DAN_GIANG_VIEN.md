# 👨‍🏫 Hướng dẫn Giảng viên - Demo CI/CD

## 📌 Mục đích của bản demo

Giúp sinh viên hiểu rõ quy trình DevOps CI/CD trong thực tế qua:
- Quản lý mã nguồn tập trung (GitHub)
- Kiểm tra tự động (GitHub Actions)
- Triển khai tự động (Vercel)

**Thời gian**: 45-60 phút

---

## 🎯 Mục tiêu học tập

Sau buổi demo, sinh viên sẽ có thể:

1. **Giải thích** quy trình CI/CD là gì và tại sao quan trọng
2. **Triển khai** ứng dụng web sử dụng GitHub + Vercel
3. **Tự động hóa** kiểm tra và triển khai mã
4. **Giám sát** pipeline và xử lý lỗi

---

## 📋 Chuẩn bị trước buổi dạy (30 phút)

### Chuẩn bị của giảng viên

- [ ] Tạo repository GitHub: `devops-cicd-demo`
- [ ] Push tất cả files lên GitHub
- [ ] Kiểm tra CI workflow chạy thành công
- [ ] Tạo Vercel project từ repository
- [ ] Kiểm tra URL Vercel có thể truy cập
- [ ] Chuẩn bị máy chiếu / Screen Share
- [ ] Test kết nối internet

### Chuẩn bị cho sinh viên

Yêu cầu mỗi sinh viên:
- [ ] Tài khoản Gmail (để tạo GitHub)
- [ ] Laptop với trình duyệt web
- [ ] Kết nối internet ổn định
- [ ] Cài đặt Git (optional, nhưng nên có)

---

## ⏰ Kịch bản dạy (60 phút)

### **Phần 1: Giới thiệu (10 phút)**

#### Slide 1: Vấn đề cũ
```
❌ Cách deploy truyền thống:
- Lập trình viên viết code
- Test thủ công (easy to forget)
- Deploy bằng tay lên server (error-prone)
- Rollback lâu (có thể không biết cách rollback)

⏱️ Mất 30-60 phút / lần deploy
🐛 Dễ gây lỗi (manual process)
👥 Khó quản lý khi team lớn
```

#### Slide 2: Giải pháp CI/CD
```
✅ Cách CI/CD modern:
1. Lập trình viên viết code + push GitHub
2. GitHub Actions tự động test
3. Nếu test pass → Vercel tự động deploy
4. Nếu test fail → Ngăn deploy, thông báo lỗi

⏱️ Chỉ 1-2 phút / lần deploy
✨ Không sai sót (automated)
🔄 Có thể deploy 10x/ngày
```

#### Slide 3: Lợi ích
```
🎯 Lợi ích chính:
- Speed: Nhanh 10x lần
- Reliability: Đáng tin cậy hơn
- Scalability: Dễ mở rộng team
- Monitoring: Dễ theo dõi
- Rollback: Nhanh và an toàn
```

---

### **Phần 2: Demo Live (30 phút)**

#### Demo 1: GitHub (5 phút)

**Mục đích:** Sinh viên thấy source control hoạt động

1. **Mở GitHub repository**
   - Chỉ tay vào files: `index.html`, `.github/workflows/ci.yml`, `README.md`
   - Giải thích: "Đây là nơi tất cả code được lưu trữ"

2. **Giải thích .github/workflows/ci.yml**
   - Mở file workflow
   - Chỉ ra các bước:
     ```yaml
     - Check if index.html exists
     - Validate HTML structure
     - Check file size
     ```
   - Nói: "Những bước này chạy tự động mỗi khi ai push code"

#### Demo 2: GitHub Actions (5 phút)

**Mục đích:** Sinh viên thấy CI hoạt động

1. **Vào tab Actions**
   ```
   GitHub → [Repository] → Actions tab
   ```

2. **Chỉ workflow "CI Check" gần nhất**
   - Nếu màu xanh (✅ PASS): "Tất cả kiểm tra vượt qua!"
   - Nếu màu đỏ (❌ FAIL): "Có lỗi, chúng ta cần fix"

3. **Click vào workflow để xem chi tiết**
   - Giải thích mỗi bước:
     - ✓ "File index.html tồn tại!"
     - ✓ "HTML structure hợp lệ!"
     - ✓ "File không rỗng!"

4. **Nói ý nghĩa:**
   - "Nếu ai xóa file, CI sẽ bắt ngay lập tức"
   - "Không cho deploy code bị lỗi lên production"

#### Demo 3: Vercel Deployment (10 phút)

**Mục đích:** Sinh viên thấy CD hoạt động

1. **Vào Vercel Dashboard**
   ```
   https://vercel.com/dashboard
   ```

2. **Chỉ Project Settings:**
   - Git Integration: "Connected to GitHub"
   - Automatic deployments: "Enabled"
   - Nói: "Mỗi push GitHub, Vercel tự động deploy"

3. **Xem Deployments:**
   - Chỉ vào Recent Deployments
   - Giải thích statuses:
     - 🟡 "Building..."
     - 🟢 "Ready" (deployed thành công)
     - 🔴 "Failed" (có lỗi)

4. **Truy cập trang web**
   ```
   https://[project-name].vercel.app
   ```
   - Giải thích: "Đây là production environment"
   - Chỉ ra: Status = ONLINE (xanh)

#### Demo 4: Test Auto-Deploy (10 phút)

**Mục đích:** Sinh viên thấy toàn bộ pipeline hoạt động end-to-end

**Chuẩn bị:**
- Chuẩn bị 3 browser tabs:
  1. Code editor (GitHub hoặc local)
  2. GitHub Actions
  3. Vercel Dashboard

**Thực hiện:**

1. **Thay đổi file index.html**
   - Ví dụ: Đổi phiên bản từ "1.0.0" → "1.0.1"
   - Commit message: "Demo: Update version"

2. **Push code**
   ```bash
   git add index.html
   git commit -m "Demo: Update version to 1.0.1"
   git push origin main
   ```
   - Hoặc dùng GitHub Desktop

3. **Theo dõi từng giai đoạn:**

   **Giai đoạn 1: GitHub nhận code (ngay lập tức)**
   - Chỉ vào repository
   - Xem code mới được push

   **Giai đoạn 2: GitHub Actions chạy CI (1-2 phút)**
   - Click vào tab "Actions"
   - Xem workflow "CI Check" chạy
   - Chỉ ra status 🟡 (Running)
   - Chờ xong → 🟢 (Success)

   **Giai đoạn 3: Vercel nhận signal (ngay khi CI pass)**
   - Vào Vercel Dashboard
   - Xem deployment mới được tạo
   - Status: "Building..." 🟡

   **Giai đoạn 4: Vercel Deploy (1-2 phút)**
   - Chờ deployment xong
   - Status: "Ready" 🟢
   - Copy URL

   **Giai đoạn 5: Xác minh trên trang web (30 giây)**
   - Vào trang web: `https://[project-name].vercel.app`
   - Làm mới: `Ctrl+Shift+R` (force refresh)
   - Xem phiên bản thay đổi thành "1.0.1"

**Giải thích lúc này:**
```
Code Push (1s) → CI Check (2 min) → Vercel Build (1 min) → Website Update (30s)
⏱️ Total: 3.5 phút từ push đến update trên web
```

---

### **Phần 3: Giải thích chi tiết (10 phút)**

#### Giải thích 1: Tại sao CI quan trọng?

**Scénario 1: Không có CI**
```
Lập trình viên A viết code + xóa file index.html (vô tình)
→ Push lên GitHub
→ Deploy ngay lên production
→ Website bị crash
→ User thấy lỗi
→ Mất tiền, mất credit
```

**Scénario 2: Có CI**
```
Lập trình viên A viết code + xóa file index.html
→ Push lên GitHub
→ GitHub Actions chạy
→ CI bắt được: "File index.html missing!"
→ Ngăn deploy
→ Thông báo lỗi cho A
→ A fix và push lại
→ CI pass → Deploy thành công
→ Website bình thường
```

**Kết luận**: CI là "người gác cổng" bảo vệ production

#### Giải thích 2: Tại sao CD quan trọng?

**Cách cũ (Manual Deploy):**
```
Dev hoàn thành feature → Thông báo cho DevOps
→ DevOps SSH vào server
→ Chạy script deploy
→ Cầu nguyện không có lỗi
→ Nếu lỗi → Rollback (mất 30 phút)
```

**Cách mới (Automatic Deploy):**
```
Dev push code → CD tự động deploy
→ Nếu lỗi → Tự động rollback
→ Nếu thành công → Tự động notify
```

**Lợi ích**:
- Nhanh: 1 phút vs 30 phút
- Đáng tin cậy: Không phụ thuộc con người
- Dễ rollback: Nếu có issue, rollback ngay

#### Giải thích 3: DevOps mindset

```
DevOps = Development + Operations

Cách cũ (Waterfall):
Dev → QA → DevOps → Release (monthly)
🐢 Chậm, rủi ro cao

Cách mới (Agile CI/CD):
Dev push → Auto test → Auto deploy (daily)
🚀 Nhanh, rủi ro thấp
```

---

### **Phần 4: Q&A + Thực hành (10 phút)**

#### Câu hỏi thường gặp:

**Q1: "Nếu CI fail thì sao?"**
- A: "Deploy bị block, Dev phải fix trước"

**Q2: "Rollback như thế nào?"**
- A: "GitHub có lịch sử tất cả deployments, click 1 cái là rollback"

**Q3: "Nếu Vercel down thì sao?"**
- A: "Website vẫn up, nhưng không update được code mới"
- Nên: "Backup lên server khác (CDN)"

**Q4: "Có phí không?"**
- A: "Miễn phí cho public projects, có plan trả phí cho private"

**Q5: "Có thể deploy test environment không?"**
- A: "Có, preview deployments tự động tạo cho mỗi PR"

---

## 🎓 Bài tập thực hành (Optional - 15 phút)

### Bài tập 1: Trigger CI Failure

```
1. Xóa file index.html
2. Push code
3. Xem GitHub Actions fail (🔴)
4. Xem Vercel không deploy
5. Khôi phục file
6. Push lại
7. Xem CI pass (🟢) + Vercel deploy
```

**Mục đích:** Giúp sinh viên hiểu CI bảo vệ production

### Bài tập 2: Tạo riêng project

```
1. Sinh viên tạo GitHub account
2. Fork repository
3. Push một thay đổi nhỏ
4. Xem CI/CD hoạt động
5. Vercel deploy project của riêng bạn
```

---

## 📊 Slide tổng kết

### Slide 1: Tóm tắt pipeline

```
┌──────────┐     ┌──────────────┐     ┌─────────┐     ┌──────────┐
│ GitHub   │ --> │ GitHub       │ --> │ Vercel  │ --> │ Users    │
│ Repo     │     │ Actions (CI) │     │ (CD)    │     │ See Web  │
└──────────┘     └──────────────┘     └─────────┘     └──────────┘

Source Control → Continuous Integration → Continuous Deployment → Production
```

### Slide 2: Lợi ích chính

```
🎯 5 Lợi ích CI/CD:

1. Speed ⚡
   Trước: 30-60 phút / deploy
   Sau: 1-2 phút / deploy

2. Reliability 🎯
   Trước: 50% lỗi khi deploy manual
   Sau: 0% lỗi (automated)

3. Scalability 📈
   Trước: Cần DevOps engineer
   Sau: Bất kỳ dev nào cũng deploy được

4. Confidence 💪
   Trước: Sợ deploy lên production
   Sau: Tự tin vì có CI bảo vệ

5. Learning 🎓
   Trước: Không biết có lỗi hay không
   Sau: Feedback ngay lập tức
```

### Slide 3: So sánh Timeline

```
❌ Cách cũ (3 giờ):
- Viết code: 30 phút
- Test: 1 giờ
- Deploy: 30 phút
- Fix lỗi: 30 phút
→ Tổng: 3 giờ

✅ Cách CI/CD (1.5 giờ):
- Viết code: 30 phút
- Push + Auto test: 2 phút
- Auto deploy: 5 phút
- Fix + Auto test: 2 phút
- Auto deploy: 5 phút
→ Tổng: 45 phút (3.3x nhanh hơn!)
```

---

## 🎬 Demo Script (Nói từng bước)

```
"Hôm nay, chúng ta sẽ xem một quy trình DevOps thực tế.

Tôi có một ứng dụng web đơn giản trên GitHub.
[Chỉ vào repository]

Chúng ta sẽ sửa code, push lên GitHub.
[Giải thích thay đổi]

Khi push, GitHub Actions tự động chạy kiểm tra.
[Xem workflow chạy]

Nếu kiểm tra pass, Vercel tự động deploy.
[Xem deployment status]

Vài giây sau, trang web cập nhật.
[Refresh website]

Cả quá trình chỉ mất 1-2 phút, KHÔNG cần manual!
Đây chính là sức mạnh của CI/CD.

Nếu có bất kỳ lỗi gì, CI sẽ bắt và ngăn deploy.
[Giải thích CI failure scenario]

Đó là cách mà công ty lớn (Google, Netflix, etc.) deploy code.
Cặp lần/ngày, hoàn toàn tự động, không sai sót.

Bây giờ, chúng ta sẽ thực hành cùng nhau..."
```

---

## 🛠️ Troubleshooting trong buổi demo

### Problem: GitHub Actions timeout
- **Giải pháp**: Check internet, hoặc skip, giải thích: "Đôi khi GitHub server busy"

### Problem: Vercel build failed
- **Giải pháp**: Check workflow file, hoặc tạo project mới

### Problem: Sinh viên không thể clone repository
- **Giải pháp**: Kiểm tra repository Public, hoặc dùng HTTPS URL

### Problem: Internet quá chậm
- **Giải pháp**: Chuẩn bị video pre-recorded làm backup

---

## 📚 Tài liệu tham khảo

- [GitHub Actions Official Docs](https://docs.github.com/en/actions)
- [Vercel Deployment Docs](https://vercel.com/docs/deployments/overview)
- [DevOps Handbook](https://www.oreilly.com/library/view/the-devops-handbook/9781491931998/)
- [CI/CD Best Practices - Atlassian](https://www.atlassian.com/continuous-delivery)

---

## 💡 Tips cho giảng viên

1. **Sử dụng metaphors (so sánh)**
   - CI = "người gác cổng" bảo vệ quality
   - CD = "dây chuyền sản xuất" tự động

2. **Show don't tell**
   - Đừng chỉ nói, phải show live demo
   - Sinh viên muốn thấy, không chỉ nghe

3. **Test trước khi dạy**
   - Chạy toàn bộ pipeline 1 lần trước khi bắt đầu

4. **Giữ energy cao**
   - DevOps là một chủ đề thú vị
   - Hãy tỏ ra hứng thú để sinh viên cũng hứng thú

5. **Đừng đi quá nhanh**
   - Giải thích mỗi bước chi tiết
   - Cho sinh viên thời gian để hiểu

---

**🎉 Chúc buổi demo thành công!**

*Cập nhật: December 2025*
