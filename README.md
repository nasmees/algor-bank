# algor-bank · Islamic Cooperative Banking CLI

**ระบบบริหารสหกรณ์อิสลามแบบ command-line · Offline · AES-256 vault · Zowe-style UI**

[![License: MIT](https://img.shields.io/badge/License-MIT-9673e0.svg)](LICENSE)
[![Runs offline](https://img.shields.io/badge/offline-ready-3fb950.svg)](#)
[![No backend](https://img.shields.io/badge/backend-none-58a6ff.svg)](#)

> Single-file HTML/JS app · Zowe-inspired CLI · Sharia-compliant (riba-free)  
> แอป HTML ไฟล์เดียว · CLI แนว Zowe · ตามหลักชารีอะฮ์ (ไม่มีดอกเบี้ย)

**[▶ Open the app](./algor-bank-islamic-coop.html)** · **[Documentation site](./index.html)** · **[GitHub](https://github.com/nasmees/algor-bank)**

---

## English

### What is algor-bank?

**algor-bank** is a **local-first Islamic cooperative banking CLI** that runs entirely in the browser:

- **Members** — register, search, edit, CSV import
- **Accounts** — savings (Wadiah), share capital, Mudarabah investment
- **Transactions** — deposit, withdraw, ledger, printable receipts
- **Sharia finance** — Murabaha, Mudarabah, Musharakah, Ijarah, Qard Hasan
- **OPS roles** — ADMIN / TELLER / VIEW with login
- **AES-256-GCM vault** — encrypted `.vault` backup (PBKDF2 120k rounds)

No server, no account, no telemetry. Data stays on your device.

### Quick start

1. Open [`algor-bank-islamic-coop.html`](./algor-bank-islamic-coop.html) in a modern browser.
2. Choose language: `1` Thai · `2` English.
3. `LOGIN admin admin123`
4. Type `SEED` to load sample data.
5. Try `STATUS`, `MEMBER LIST`, `MENU`, or press **F7** for the panel.

Optional: host the repo on **GitHub Pages** and open `index.html` for the full guide.

### Demo users

| User | Password | Role |
|------|----------|------|
| `admin` | `admin123` | Full access |
| `teller` | `teller123` | Members, accounts, transactions |
| `viewer` | `view123` | Read-only |

### Main commands

| Command | Description |
|---------|-------------|
| `LOGIN` / `LOGOUT` / `WHO` | Ops authentication |
| `MEMBER LIST` / `ADD` / `EDIT` / `SEARCH` | Member management |
| `ACCOUNT OPEN` / `LIST` | Savings, share, invest |
| `DEPOSIT` / `WITHDRAW` / `TX LIST` | Cash movements |
| `RECEIPT <id>` | Print slip |
| `FINANCE APPLY` / `APPROVE` / `PAY` | Sharia products |
| `SETPASS` / `VAULT SAVE` / `VAULT LOAD` | Encrypted backup |
| `STATUS` / `REPORT` / `SHARIA` | Status & principles |
| `SEED` / `CSV` / `HELP` / `MENU` | Sample data, import, help |
| `↑` / `↓` | Command history |

**Finance products:** `MURABAHA` · `MUDARABAH` · `MUSHARAKAH` · `IJARAH` · `QARD`

### Example session

```text
1
LOGIN admin admin123
SEED
STATUS
MEMBER LIST
ACCOUNT OPEN M001 SAVINGS 5000
DEPOSIT A001 1000
FINANCE APPLY M001 MURABAHA 50000 12 5
FINANCE APPROVE F001
SETPASS my-secret
VAULT SAVE
```

### Security

- Vault files use **AES-256-GCM** with **PBKDF2** (120 000 iterations, SHA-256).
- Password never leaves the browser; encryption is local.
- Use `SETPASS`, then `VAULT SAVE` to download an encrypted `.vault`. Use `VAULT LOAD` to restore.
- `LOCK` clears the password from memory.

### Disclaimer

This is an **educational / ops-practice** tool for Islamic cooperative concepts.  
It is **not** a replacement for licensed accounting systems under Thai cooperative law.  
Real deployments should involve a competent **Sharia advisor (Sharia Board)**.

### Project layout

```text
├── README.md                      # This file (EN + TH)
├── index.html                     # GitHub Pages documentation (TH/EN)
└── algor-bank-islamic-coop.html   # The application
```

### License

MIT — use, study, and adapt freely. Attribution appreciated.

---

## ภาษาไทย

### algor-bank คืออะไร?

**algor-bank** คือ **CLI บริหารสหกรณ์อิสลาม** รันในเบราว์เซอร์ทั้งหมด:

- **สมาชิก** — ลงทะเบียน ค้นหา แก้ไข นำเข้า CSV
- **บัญชี** — ออมทรัพย์ (Wadiah) หุ้นสมาชิก ลงทุน Mudarabah
- **รายการ** — ฝาก ถอน ledger ใบเสร็จพิมพ์ได้
- **สินเชื่อชารีอะฮ์** — Murabaha, Mudarabah, Musharakah, Ijarah, Qard Hasan
- **สิทธิ์ OPS** — ADMIN / TELLER / VIEW พร้อม LOGIN
- **Vault AES-256-GCM** — สำรองไฟล์ `.vault` เข้ารหัส (PBKDF2 120,000 รอบ)

ไม่มีเซิร์ฟเวอร์ ไม่มีบัญชี ไม่ส่งข้อมูลออก ข้อมูลอยู่บนเครื่องคุณ

### เริ่มใช้งานเร็ว

1. เปิด [`algor-bank-islamic-coop.html`](./algor-bank-islamic-coop.html) ในเบราว์เซอร์
2. เลือกภาษา: `1` ไทย · `2` English
3. `LOGIN admin admin123`
4. พิมพ์ `SEED` เพื่อโหลดข้อมูลตัวอย่าง
5. ลอง `STATUS` · `MEMBER LIST` · `MENU` หรือกด **F7** เปิด Panel

ถ้า deploy บน **GitHub Pages** เปิด `index.html` อ่านคู่มือ แล้วเปิดแอปจากลิงก์ในหน้า

### ผู้ใช้ตัวอย่าง

| ผู้ใช้ | รหัสผ่าน | สิทธิ์ |
|--------|----------|--------|
| `admin` | `admin123` | เต็ม |
| `teller` | `teller123` | สมาชิก บัญชี รายการ |
| `viewer` | `view123` | อ่านอย่างเดียว |

### คำสั่งหลัก

| คำสั่ง | ความหมาย |
|--------|----------|
| `LOGIN` / `LOGOUT` / `WHO` | เข้าสู่ระบบ OPS |
| `MEMBER LIST` / `ADD` / `EDIT` / `SEARCH` | จัดการสมาชิก |
| `ACCOUNT OPEN` / `LIST` | บัญชีออม หุ้น ลงทุน |
| `DEPOSIT` / `WITHDRAW` / `TX LIST` | ฝาก ถอน รายการ |
| `RECEIPT <id>` | ใบเสร็จ / พิมพ์ |
| `FINANCE APPLY` / `APPROVE` / `PAY` | สินเชื่อชารีอะฮ์ |
| `SETPASS` / `VAULT SAVE` / `VAULT LOAD` | สำรองเข้ารหัส |
| `STATUS` / `REPORT` / `SHARIA` | สถานะและหลักการ |
| `SEED` / `CSV` / `HELP` / `MENU` | ตัวอย่าง นำเข้า คู่มือ |
| `↑` / `↓` | ประวัติคำสั่ง |

**ผลิตภัณฑ์:** `MURABAHA` · `MUDARABAH` · `MUSHARAKAH` · `IJARAH` · `QARD`

### ตัวอย่างการใช้งาน

```text
1
LOGIN admin admin123
SEED
STATUS
MEMBER LIST
ACCOUNT OPEN M001 SAVINGS 5000
DEPOSIT A001 1000
FINANCE APPLY M001 MURABAHA 50000 12 5
FINANCE APPROVE F001
SETPASS my-secret
VAULT SAVE
```

### ความปลอดภัย

- ไฟล์ vault ใช้ **AES-256-GCM** + **PBKDF2** (120,000 รอบ)
- รหัสผ่านและข้อมูลเข้ารหัสอยู่บนเครื่องผู้ใช้เท่านั้น
- `SETPASS` แล้ว `VAULT SAVE` เพื่อดาวน์โหลด `.vault` · `VAULT LOAD` เพื่อกู้คืน
- `LOCK` ล้างรหัสผ่านออกจาก memory

### ข้อจำกัด

ระบบนี้เป็นเครื่องมือ**ศึกษาและทดลอง**แนวคิดสหกรณ์อิสลาม  
**ไม่ทดแทน**ระบบบัญชีที่จดทะเบียนตามกฎหมายสหกรณ์ไทย  
การใช้งานจริงควรมี**ที่ปรึกษาชารีอะฮ์ (Sharia Board)** กำกับ

### โครงสร้างโปรเจกต์

```text
├── README.md                      # ไฟล์นี้ (EN + TH)
├── index.html                     # หน้าคู่มือ GitHub Pages (TH/EN)
└── algor-bank-islamic-coop.html   # แอปหลัก
```

### สัญญาอนุญาต

MIT — ใช้ ศึกษา และดัดแปลงได้อย่างอิสระ

---

## Credits

UI inspired by **Zowe CLI** (Open Mainframe Project) command-help layout  
and classical **Islamic cooperative (riba-free)** product structures.  
Converted and extended from the ALGOR FALAK mission-control terminal concept.
