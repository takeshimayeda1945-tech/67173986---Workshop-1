# 67173986-Workshop 1

## 1. ที่มาและความสำคัญ

* SALA STORE - CSI204 Project Design Document SEMESTER 3/2568
* E-Commerce ร้านขายเสื้อผ้าแบรนด์ SALA รองรับ 2 บทบาทผู้ใช้งาน Customer, Admin
* ในปัจจุบันพฤติกรรมการซื้อสินค้าออนไลน์เติบโตอย่างรวดเร็ว ผู้บริโภคต้องการแพลตฟอร์มที่ใช้งานง่าย ค้นหาสินค้าได้รวดเร็ว และมีการแสดงรายละเอียดสินค้าที่ชัดเจน การพัฒนาโปรเจกต์นี้จึงมุ่งเน้นไปที่การสร้างประสบการณ์การช้อปปิ้งที่สะอาดตา เพื่อให้สินค้ามีความโดดเด่นและช่วยให้ผู้ใช้งานตัดสินใจซื้อได้ง่ายขึ้น

## 2. สมาชิกในกลุ่ม

* 67098506 - ปัณณพรรธน์ เกียรตินิรชา
* 67164494 - ฐิติฉัตร ศิริบุตร
* 67172467 - สุรวัศ แสงเจริญสุขเลิศ
* 67173986 - อินทัช ชายเพ็ชร
* 67176203 - ภทรพร แซ่ลี้

## 3. Pain Points

* เว็บไซต์ที่มีโฆษณาหรือปุ่มรกตาเกินไป ทำให้เสียสมาธิในการเลือกซื้อ
* การค้นหาไซส์และสีของเสื้อผ้าที่ซับซ้อนหรือไม่ชัดเจน
* ขั้นตอนการ Checkout ที่ยาวเกินความจำเป็น

## 4. Scope

* ระบบหน้าบ้าน (Front-end): ระบบลงทะเบียน/เข้าสู่ระบบ, หน้าค้นหาและแสดงรายละเอียดสินค้า, ตะกร้าสินค้า, และระบบชำระเงิน
* ระบบหลังบ้าน (Back-end): การจัดการสินค้า (CRUD), การจัดการออเดอร์, การจัดการข้อมูลสมาชิก

## 5. ผู้ใช้งาน

* ลูกค้าทั่วไป: ผู้ที่ต้องการซื้อเสื้อผ้า เน้นความง่าย รวดเร็ว และความน่าเชื่อถือ
* ผู้ดูแลระบบ (Admin): พนักงานที่ดูแลการจัดการสต็อกสินค้า ปรับปรุงราคาสินค้า และดูแลข้อมูลการสั่งซื้อ

## 6. Requirements
### User Requirement

#### การจัดการข้อมูลและบัญชีผู้ใช้
* Customer: ต้องการระบบสมัครสมาชิกและลงชื่อเข้าใช้ที่ง่ายและปลอดภัย เพื่อจัดเก็บประวัติการสั่งซื้อและที่อยู่สำหรับการจัดส่ง ลดขั้นตอนการกรอกข้อมูลซ้ำซ้อน
* Admin: ต้องการระบบจัดการสิทธิ์ผู้ใช้งาน เพื่อตรวจสอบข้อมูลสมาชิกและดูแลความปลอดภัยของฐานข้อมูลให้เป็นไปตามมาตรฐาน

#### การเลือกซื้อและการจัดการสินค้า
* Customer: ต้องการระบบค้นหาและคัดกรองสินค้าที่แม่นยำ (เช่น ตามประเภท, ไซส์, สี) รวมถึงต้องการดูรายละเอียดสินค้าแบบเจาะลึกพร้อมภาพประกอบที่ชัดเจน
* Admin: ต้องการระบบจัดการแคตตาล็อกสินค้าที่ยืดหยุ่น สามารถเพิ่ม, แก้ไข, หรือลบข้อมูลสินค้าและรูปภาพได้ทันที รวมถึงสามารถระบุรายละเอียดเชิงลึก (Variants) เช่น สต็อกของไซส์ S, M, L ได้อย่างละเอียด

#### กระบวนการสั่งซื้อและตะกร้าสินค้า
* Customer: ต้องการระบบตะกร้าสินค้าที่สรุปยอดรวมค่าใช้จ่ายได้อย่างชัดเจน พร้อมช่องทางการชำระเงินที่หลากหลายและน่าเชื่อถือ
* Admin: ต้องการระบบที่เชื่อมโยงกับสต็อกสินค้า (Inventory Management) เพื่อตัดจำนวนสินค้าออกจากคลังโดยอัตโนมัติทันทีที่การชำระเงินสำเร็จ เพื่อป้องกันปัญหาการขายสินค้าเกินจำนวน (Overselling)

### System Requirement
#### Functional Requirement

* User Management: ระบบเข้าสู่ระบบด้วย Email/Password หรือ Social Login
* Inventory Tracking: ระบบปรับปรุงสต็อกอัตโนมัติเมื่อมีการสั่งซื้อสำเร็จ
* Search Engine: ระบบค้นหาแบบ Predictive Text (แสดงคำแนะนำขณะพิมพ์)

#### Non-Functional Requirement

* Scalability: สามารถขยาย Server ได้หากมี Traffic พุ่งสูงในช่วงจัดโปรโมชั่น
* Security: ป้องกันการโจมตีประเภท SQL Injection และ XSS, ใช้ระบบ HTTPS เพื่อรักษาความปลอดภัยของข้อมูล
* Responsiveness: เว็บไซต์ต้องปรับเปลี่ยนขนาดตามอุปกรณ์ได้อย่างสมบูรณ์ (Mobile-first design)

## 7. เทคโนโลยีที่ใช้

* Frontend: React.js, Tailwind CSS (เน้นความมินิมอล)
* Backend: Node.js with Express.js
* Database: PostgreSQL (โครงสร้างข้อมูลแบบ Relational)
* Testing: Postman, Jmeter, UAT
* Authentication: JWT (JSON Web Token)

## 8. Database

* Users: id, username, email, password_hash, address
* Products: id, name, description, price, category_id, image_url
* Inventory: id, product_id, size, color, stock_quantity
* Orders: id, user_id, total_price, status, created_at
* Order_Items: id, order_id, product_id, quantity, price

## 9. Prototype

* **Figma url:** "[Figma](https://www.figma.com/design/8SYpgjQJaHrKjdKS1LM6Lf/SALA-STORE?node-id=0-1&p=f&t=FLMT8dAd60P3Wi7O-0)"

## 10. Mermaid Diagram

แผนภูมิระหว่าง Users ทั้ง 3 กลุ่มในระบบ SALA:

```mermaid
graph TD
    Customer["Customer<br/>Log in / Search / Buy"]
    Admin["Admin<br/>Manage Products,<br/>Categories, Customers"]
    SupportStaff["Support Staff<br/>View & Answer Tickets"]

    App["SALA Frontend App"]
    Dashboard["Admin Dashboard"]

    Ticket["Open Ticket"]
    TicketSystem["Ticket System<br/>Update Ticket Status"]
    Products["Manage Products,<br/>Categories, Customers"]

    API["Backend: API Gateway"]
    Sync["Sync Data"]

    DB[("Database")]

    Customer --> App
    Admin --> Dashboard
    SupportStaff --> TicketSystem

    App --> API
    Dashboard --> API

    App --- Ticket
    Dashboard --- Products
    Dashboard --- TicketSystem

    Ticket --> Sync
    Products --> Sync
    TicketSystem --> Sync

    Sync --> API
    API --> DB

    classDef user fill:#e3f2fd,stroke:#1565c0,stroke-width:2px
    classDef frontend fill:#f3e5f5,stroke:#6a1b9a,stroke-width:2px
    classDef feature fill:#e8f5e9,stroke:#2e7d32,stroke-width:2px
    classDef backend fill:#fff3e0,stroke:#e65100,stroke-width:2px
    classDef database fill:#fce4ec,stroke:#c62828,stroke-width:2px

    class Customer,Admin,SupportStaff user
    class App,Dashboard frontend
    class Ticket,TicketSystem,Products feature
    class API,Sync backend
    class DB database
