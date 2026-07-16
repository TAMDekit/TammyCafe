# ☕ ภารกิจเปิดร้านคาเฟ่ (Git Collaboration Workshop)

ยินดีต้อนรับสู่เวิร์กชอปจำลองการทำงานเป็นทีมด้วย Git และ GitHub! กิจกรรมนี้ทุกคนในกลุ่มจะต้องร่วมมือกันเปิดร้านคาเฟ่และช่วยกันจัดทำเมนูให้สำเร็จ 🚀

---

## 👥 การเตรียมตัวและแบ่งหน้าที่
**1. เลือกตัวแทน:** โหวตเลือกเพื่อนในกลุ่ม 1 คนรับบทเป็น **"ผู้จัดการร้าน"**  
**2. คิดคอนเซปต์ร้าน:** ช่วยกันคิด "ชื่อร้าน" และแบ่งหน้าที่กันรับผิดชอบคนละ 1 หมวดหมู่ (หมวดละ 2 เมนู)
* 🍰 `dessert-menu` (ขนมหวาน)
* ☕ `drink-menu` (เครื่องดื่ม)
* 🍝 `food-menu` (อาหารคาว)
* 🍎 `fruit-menu` (ผลไม้)
* 💪 `healthy-menu` (สายสุขภาพ)

---

## 👑 ภารกิจของผู้จัดการร้าน (Manager Only)
**3. เปิดร้านและตั้งชื่อ:**
* ทำการ **Fork** Repository นี้ และ **Clone** ลงเครื่องตัวเอง  
- เช็คว่าในเครื่องมีการ login github ค้างไว้ไหม
```bash
git credential-manager github list
```

- log out ออกจากบัญชี (ในกรณีที่มีlog in ค้างไว้อยู่)
```bash
git credential-manager github logout <username>
```

- log in บัญชีตัวเอง
```bash
git credential-manager github login
```
* เปิดไฟล์ `menu.md` แล้วแก้ไขบรรทัดบนสุดเพื่อเพิ่ม **"ชื่อร้าน"**  
(อย่าลืม Config!)

```bash
git config --local user.name "Fullname"
git config --local user.email "E-mail"

git add .
git commit -m "add cafe name"
git push -u origin main
```
**4. จ้างพนักงาน:**  เข้าไปที่แท็บ Settings ของ Repo > Collaborators > แล้วกด Add collaborator เพื่อเชิญเพื่อนๆ ทุกคนในกลุ่มเข้ามาทำงาน

## 👨‍🍳 ภารกิจของเพื่อนๆในกลุ่ม (Team Members)
**5. รับตำแหน่ง:**   เข้าไปกดยอมรับคำเชิญ (Accept Invitation) ในอีเมล หรือที่หน้า Inbox  ของเว็บ GitHub

**6. ดึงข้อมูลร้านและเข้าครัว:** ทำการ Clone Repo ของเพื่อนที่เป็นผู้จัดการร้านลงเครื่องของตัวเอง จากนั้นสร้าง Branch ใหม่และสลับไปทำงานที่ Branch นั้น

```bash
git clone <URL_ของ_Repo_ผู้จัดการ>
cd <ชื่อโฟลเดอร์ร้าน>
git branch <ชื่อหมวดหมู่เมนูที่รับผิดชอบ>
```
(**ตัวอย่างการตั้งชื่อ Branch:** `git branch dessert-menu`)
- สลับไปทำงานใน branch ตัวเอง
```bash
git switch <ชื่อหมวดหมู่เมนูที่รับผิดชอบ>
```
(**ตัวอย่างการสลับ Branch:** `git switch dessert-menu`)

**7. ลงมือทำเมนู:** เปิดไฟล์ menu.md แล้วเพิ่มเมนู 2 อย่างลงในโซนบรรทัดของตัวเอง

**🚨 คำเตือน: ห้ามแก้ไข เพิ่ม หรือลบข้อความในจุดอื่นๆ นอกเหนือจากโซนของตัวเองเด็ดขาด! เพราะจะทำให้เกิด Conflict กับเพื่อนตอนรวมไฟล์**

**8. ส่งงานขึ้นระบบ:** เมื่อพิมพ์เสร็จและกด Save แล้ว ให้ตั้งค่า Config และ Push งานขึ้นไป

```bash
git config --local user.name "Fullname"
git config --local user.email "E-mail"

git add .
git commit -m "add <หมวดหมู่เมนูที่ตัวเองได้รับ>"
git push -u origin <ชื่อ branch ที่ตัวเองทำ>
```
**(ตัวอย่างการ commit:** `git commit -m "add dessert menu"`)  
**(ตัวอย่างการ push:** `git push -u origin dessert-menu`)
## 🤝 ภารกิจตรวจสอบและรวมร่าง (Review & Merge)  
**9. ส่งงานที่ทำเข้าไปรวมกับเพื่อน (Open PR):**
ไปที่หน้าเว็บ GitHub กดปุ่มสีเขียว Compare & pull request (เพื่อขอส่งโค้ดจาก Branch ตัวเองเข้า Branch main)

- **ด้านขวาที่ช่อง Assignees: ให้เลือกชื่อ "ตัวเอง"**

- **ด้านขวาที่ช่อง Reviewers: ให้เลือกชื่อ "เพื่อนคนข้างๆ" เพื่อให้มาช่วยตรวจงาน**

**10. ตรวจสอบคุณภาพ (Review & Approve):**

- คนที่ถูกแท็กให้เป็น Reviewer เข้าไปดู Pull Request ของเพื่อน

- ถ้ารายการถูกต้อง ไม่ไปทับบรรทัดคนอื่น ให้กดปุ่ม Approve ✅

**11. แปะเมนูหน้าร้าน (Merge):**
เมื่อเพื่อนกด Approve ให้เรียบร้อยแล้ว ให้เจ้าของ PR (คนที่เปิด PR) เป็นคนกดปุ่ม Merge pull request เพื่อรวมเมนูของตัวเองเข้าสู่ร้านหลักได้เลย! 🎉