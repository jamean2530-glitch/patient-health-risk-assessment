# ระบบลงทะเบียนและประเมินความเสี่ยงสุขภาพเบื้องต้น
### Patient Health Risk Assessment and Registration System (งานที่ 1)

🌐 **ลิงก์เข้าชมเว็บไซต์ผ่าน GitHub Pages**: [https://jamean2530-glitch.github.io/patient-health-risk-assessment/](https://jamean2530-glitch.github.io/patient-health-risk-assessment/)

เว็บแอปพลิเคชันเพื่อคัดกรองผู้ป่วยเบื้องต้นก่อนเข้ารับการรักษา โดยสามารถรับข้อมูลส่วนบุคคล คำนวณค่าดรรชนีมวลกาย (BMI) ประเมินความเสี่ยงสุขภาพตามเงื่อนไขที่กำหนด และออกใบสรุปผลการคัดกรอง

---

## 🌟 ฟังก์ชันหลักของระบบ (Features)

1. **การตรวจสอบความถูกต้องของข้อมูล (Input Validation)**:
   - ตรวจสอบข้อมูลป้อนเข้า (ชื่อ-นามสกุล, อายุ, น้ำหนัก, ส่วนสูง)
   - หากพบช่องว่าง หรือค่าที่ไม่ถูกต้อง แสดงกล่องข้อความแจ้งเตือน (`Alert`) และปฏิเสธการประเมินผล

2. **การประเมินและจัดกลุ่มความเสี่ยง (Risk Assessment Logic)**:
   - คำนวณค่า BMI จากสูตร: $\text{BMI} = \frac{\text{น้ำหนัก (kg)}}{(\text{ส่วนสูง (m)})^2}$
   - ประเมินระดับความเสี่ยงร่วมกับพฤติกรรมเสี่ยง (เช่น การสูบบุหรี่, การออกกำลังกาย) และกลุ่มโรคประจำตัว
   - จัดกลุ่มระดับความเสี่ยงเป็น 3 ระดับ:
     - 🟢 **ความเสี่ยงต่ำ (Low Risk)**
     - 🟡 **ความเสี่ยงปานกลาง (Moderate Risk)**
     - 🔴 **ความเสี่ยงสูง (High Risk)**

3. **การแสดงผลลัพธ์ (Result Display & Summary)**:
   - แสดงหน้าต่างสรุปผลข้อมูลผู้ป่วย (`Dialog`)
   - แสดงระดับความเสี่ยงด้วยสีสัญลักษณ์ (`Chip`)
   - แสดงรายการปัจจัยเสี่ยงที่ตรวจพบ พร้อมข้อแนะนำการปฏิบัติตน (Health Recommendations)
   - รองรับการพิมพ์ใบสรุปผลหรือบันทึกเป็น PDF (`window.print`)
   - มีระบบบันทึกประวัติการคัดกรองย้อนหลังในตัวเครื่อง (`localStorage`)

---

## 🎨 รายการ Material-UI (MUI Components) ที่นำมาใช้

- **Structure & Layout**: `Container`, `Paper`, `Grid`, `Stack`, `Box`
- **Inputs**: `TextField` (รับค่าตัวอักษรและตัวเลข), `RadioGroup` / `Radio` (เลือกพฤติกรรมความเสี่ยง), `Select` / `MenuItem` (เลือกกลุ่มโรคประจำตัว), `Button` (ปุ่มประเมินผลและปุ่มล้างข้อมูล)
- **Feedback & Displays**: `Alert` (แจ้งเตือนความผิดพลาด), `Dialog` / `DialogTitle` / `DialogContent` / `DialogActions` (หน้าต่างสรุปผลการประเมิน), `Chip` (แสดงสถานะระดับความเสี่ยงด้วยสีสัญลักษณ์)

---

## 🚀 เทคโนโลยีที่ใช้ (Tech Stack)

- **Frontend**: HTML5, React 18, Babel Standalone
- **UI Library**: Material-UI (MUI v5) & Emotion
- **Font**: Prompt (Google Fonts)
- **Hosting**: GitHub Pages
