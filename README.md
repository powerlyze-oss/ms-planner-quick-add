# 📋 MS Planner Quick Add

> สร้าง Task ใน Microsoft Planner แบบง่ายและรวดเร็ว

[![Live Demo](https://img.shields.io/badge/demo-live-success)](https://yourusername.github.io/ms-planner-quick-add/)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

เว็บแอพพลิเคชันที่ช่วยให้คุณสร้าง Task ใน Microsoft Planner ได้ง่ายและรวดเร็ว โดยทำหน้าที่เป็น "หน้ากาก" (Form Interface) ที่ใช้งานง่ายกว่า interface ปกติของ MS Planner

![Screenshot](https://via.placeholder.com/800x400?text=Screenshot+Here)

## ✨ ฟีเจอร์

- 🔐 **Login ด้วย Microsoft Account** - เข้าถึง Planner ที่คุณมีสิทธิ์โดยตรง
- 📋 **สร้าง Task ง่ายๆ** - ฟอร์มที่ใช้งานง่าย กรอกข้อมูลครบถ้วน
- 💾 **Template System** - บันทึกงานที่ทำบ่อยๆ นำมาใช้ซ้ำได้ทันที
- ⚡ **Quick Actions** - สร้างต่อเนื่องได้ เหมาะสำหรับสร้างหลาย Task
- 🎨 **UI ที่สวยงาม** - ใช้งานง่าย responsive design
- 🌐 **ไม่ต้องติดตั้ง** - ใช้งานผ่าน web browser ได้เลย

## 🚀 เริ่มใช้งาน

### สำหรับผู้ใช้งานทั่วไป

1. **เปิดเว็บแอพ:** [https://yourusername.github.io/ms-planner-quick-add/](https://yourusername.github.io/ms-planner-quick-add/)
2. **Setup ครั้งแรก:** ทำตามคำแนะนำในหน้าเว็บเพื่อสร้าง Azure AD App และใส่ Client ID
3. **Login:** ด้วย Microsoft Account ของคุณ
4. **เริ่มใช้งาน:** เลือก Plan, Bucket และสร้าง Task ได้เลย!

### สำหรับ Developer

```bash
# Clone repository
git clone https://github.com/yourusername/ms-planner-quick-add.git

# เข้าไปใน directory
cd ms-planner-quick-add

# รัน local server
python -m http.server 8000

# เปิดเบราว์เซอร์
# http://localhost:8000
```

## 📖 คู่มือการใช้งาน

### ขั้นตอนที่ 1: Setup Azure AD App

1. ไปที่ [Azure Portal - App Registrations](https://portal.azure.com/#view/Microsoft_AAD_RegisteredApps/ApplicationsListBlade)
2. สร้าง App Registration ใหม่
3. ตั้งค่า Redirect URI เป็น Single-page application (SPA)
4. เพิ่ม Permissions: `User.Read`, `Group.ReadWrite.All`, `Tasks.ReadWrite`
5. Copy Application (client) ID

รายละเอียดเพิ่มเติม: [GITHUB-PAGES-DEPLOYMENT.md](GITHUB-PAGES-DEPLOYMENT.md)

### ขั้นตอนที่ 2: ใส่ Client ID

1. เปิดเว็บแอพ
2. ใส่ Client ID ที่ได้จาก Azure AD
3. บันทึก

### ขั้นตอนที่ 3: ใช้งาน

1. **Login** ด้วย Microsoft Account
2. **เลือก Plan และ Bucket**
3. **กรอกรายละเอียด Task:**
   - ชื่อ Task (required)
   - วันที่เริ่ม / วันครบกำหนด (optional)
   - Priority: Low, Medium, Important, Urgent
   - Progress: Not Started, In Progress, Completed
   - รายละเอียดเพิ่มเติม
4. **สร้าง Task:**
   - ✅ สร้าง Task - สร้างแล้วเสร็จ
   - ➕ สร้าง & เพิ่มต่อ - สร้างต่อเนื่อง

### ใช้งาน Template

1. **สร้าง Template:**
   - กรอกข้อมูล Task
   - เลือก "💾 บันทึกเป็น Template"
   - สร้าง Task
   - ตั้งชื่อ Template

2. **ใช้ Template:**
   - คลิก "📝 ใช้ Template"
   - เลือก Template ที่ต้องการ
   - ข้อมูลจะถูกกรอกอัตโนมัติ

## 🛠️ เทคโนโลยีที่ใช้

- **MSAL.js** - Microsoft Authentication Library
- **Microsoft Graph API** - เข้าถึง MS Planner
- **Tailwind CSS** - Styling
- **Vanilla JavaScript** - No framework dependencies

## 📁 โครงสร้างโปรเจกต์

```
ms-planner-quick-add/
├── index.html                      # Main application file
├── README.md                       # This file
├── GITHUB-PAGES-DEPLOYMENT.md      # Deployment guide
├── TROUBLESHOOTING.md              # Troubleshooting guide
└── LICENSE                         # MIT License
```

## 🔒 ความปลอดภัย

- ✅ ไม่เก็บ password หรือข้อมูลส่วนตัว
- ✅ ใช้ MSAL.js (Microsoft's official library) สำหรับ authentication
- ✅ Access token จัดการโดย MSAL library
- ✅ Client ID เก็บใน localStorage ของเบราว์เซอร์
- ✅ ไม่มี backend server - ทุกอย่างทำงานใน client-side

**หมายเหตุ:** Client ID ไม่ใช่ข้อมูลลับ (ไม่เหมือน Client Secret) และสามารถแชร์ได้

## 🌐 Deploy บน GitHub Pages

### Quick Deploy

1. Fork repository นี้
2. ไปที่ Settings → Pages
3. เลือก Source: "Deploy from a branch"
4. เลือก Branch: main
5. Save
6. รอ 1-2 นาที
7. เข้าใช้งานที่ `https://yourusername.github.io/ms-planner-quick-add/`

รายละเอียดเพิ่มเติม: [GITHUB-PAGES-DEPLOYMENT.md](GITHUB-PAGES-DEPLOYMENT.md)

### Custom Domain (Optional)

ถ้าต้องการใช้ domain ของตัวเอง:

1. ตั้งค่า DNS CNAME record
2. เพิ่ม Custom domain ใน GitHub Pages settings
3. อัพเดต Azure AD Redirect URI

## 🐛 แก้ปัญหา

พบปัญหาในการใช้งาน? ดูคู่มือแก้ปัญหาที่: [TROUBLESHOOTING.md](TROUBLESHOOTING.md)

ปัญหาทั่วไป:
- [Invalid Client ID](TROUBLESHOOTING.md#1-invalid-client--aadsts700016)
- [Redirect URI Mismatch](TROUBLESHOOTING.md#2-redirect-uri-mismatch--aadsts50011)
- [Pop-up ถูกบล็อก](TROUBLESHOOTING.md#3-pop-up-ถูกบล็อก--popup_window_error)
- [ไม่เห็น Plans](TROUBLESHOOTING.md#5-ไม่เห็น-plans--ไม่พบ-plan)

## 🤝 Contributing

ยินดีรับ contribution ทุกรูปแบบ!

1. Fork repository
2. สร้าง feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to branch (`git push origin feature/AmazingFeature`)
5. เปิด Pull Request

## 📝 License

โปรเจกต์นี้ใช้ MIT License - ดูรายละเอียดที่ [LICENSE](LICENSE)

## 👨‍💻 Author

**Your Name**
- GitHub: [@yourusername](https://github.com/yourusername)
- Email: your.email@example.com

## 🙏 Acknowledgments

- [Microsoft Graph API](https://docs.microsoft.com/en-us/graph/api/resources/planner-overview)
- [MSAL.js](https://github.com/AzureAD/microsoft-authentication-library-for-js)
- [Tailwind CSS](https://tailwindcss.com/)

## 📊 Stats

![GitHub Stars](https://img.shields.io/github/stars/yourusername/ms-planner-quick-add?style=social)
![GitHub Forks](https://img.shields.io/github/forks/yourusername/ms-planner-quick-add?style=social)
![GitHub Issues](https://img.shields.io/github/issues/yourusername/ms-planner-quick-add)

## 🗺️ Roadmap

- [ ] Multi-language support (EN, TH)
- [ ] Assign tasks to team members
- [ ] Bulk import from Excel/CSV
- [ ] Task analytics dashboard
- [ ] Dark mode
- [ ] Mobile app version

---

Made with ❤️ for easier MS Planner task creation
