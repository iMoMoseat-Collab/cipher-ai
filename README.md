# ⬡ CIPHER — Cognitive Intelligence Personal Hub

> ผู้ช่วย AI ส่วนตัว พูดคุยภาษาไทย/อังกฤษ ค้นหาข้อมูลสด ออกเสียงได้ รันบนมือถือได้เลย

![Version](https://img.shields.io/badge/version-2.0-00ff41?style=flat-square&labelColor=080c08)
![Model](https://img.shields.io/badge/model-Haiku_4.5-00ff41?style=flat-square&labelColor=080c08)
![License](https://img.shields.io/badge/license-MIT-00ff41?style=flat-square&labelColor=080c08)

---

## 🚀 Demo

**🌐 Live:** https://imomoseat-collab.github.io/cipher-ai

---

## ✨ Features

| ฟีเจอร์ | รายละเอียด |
|---------|-----------|
| 💬 AI สนทนา | Claude Haiku 4.5 คุยได้ทุกเรื่อง |
| 🔍 Web Search | ค้นหาข้อมูลสด realtime |
| 🔊 TTS | ออกเสียงไทย/อังกฤษ สลับอัตโนมัติ |
| 🎤 STT | รับเสียงพูดแปลงเป็นข้อความ |
| ⚡ Offline Mode | ตอบได้โดยไม่ใช้ internet |
| 🧠 Knowledge Base | ความรู้ทั่วไป 12 หมวด |
| 💳 Credit Tracker | นับ token realtime แจ้งเตือนเครดิต |
| 🖥️ Terminal UI | ธีมดำเขียว matrix rain glitch effect |
| 📱 PWA Ready | ติดตั้งบน iPhone/Android ได้เลย |

---

## 🛠️ Tech Stack

```
Frontend    → HTML + CSS + Vanilla JS (Single file)
AI Model    → Claude Haiku 4.5 (Anthropic)
API Proxy   → Cloudflare Workers
Web Search  → Anthropic web_search tool
TTS/STT     → Web Speech API
Hosting     → GitHub Pages
```

---

## 📦 Files

```
cipher-ai/
├── index.html        # แอปหลัก (ทุกอย่างอยู่ในไฟล์เดียว)
├── knowledge.json    # Knowledge base สำหรับ offline mode
├── worker.js         # Cloudflare Worker proxy (deploy แยก)
└── README.md         # ไฟล์นี้
```

---

## ⚙️ Setup

### 1. Deploy Cloudflare Worker

1. ไปที่ [dash.cloudflare.com](https://dash.cloudflare.com)
2. **Compute → Workers & Pages → Create → Start with Hello World**
3. ตั้งชื่อ `cipher-proxy`
4. วางโค้ดจาก `worker.js` → **Deploy**
5. จด URL เช่น `https://cipher-proxy.xxx.workers.dev`

### 2. แก้ WORKER URL ใน index.html

```js
// บรรทัดที่ ~ต้นไฟล์
const WORKER = 'https://cipher-proxy.xxx.workers.dev';
```

### 3. Deploy บน GitHub Pages

1. สร้าง repo ใหม่บน GitHub
2. อัปโหลด `index.html` และ `knowledge.json`
3. **Settings → Pages → Branch: main → Save**
4. รอ 1-2 นาที → ได้ลิงก์

### 4. เปิดใช้งาน

1. เปิดลิงก์ในเบราว์เซอร์
2. ใส่ **Anthropic API Key** (`sk-ant-...`)
3. คุยได้เลย! 🎉

---

## 💰 ค่าใช้จ่าย

| บริการ | ราคา |
|--------|------|
| GitHub Pages | ฟรี |
| Cloudflare Workers | ฟรี (100,000 req/วัน) |
| Claude Haiku 4.5 | $1 / 1M input tokens, $5 / 1M output tokens |
| Anthropic API Key | ฟรี (จ่ายตามใช้) |

> 💡 เติม $5 คุยได้ประมาณ 2-3 เดือนสำหรับการใช้งานทั่วไป

---

## 🎮 การใช้งาน

### คำสั่งพื้นฐาน
- พิมพ์หรือกดปุ่ม 🎤 แล้วพูดได้เลย
- กด **Orb ⬡** เพื่อเล่นเสียงซ้ำ
- กด **🔊** เพื่อเปิด/ปิดเสียง
- กด **🌐 ON / ⚡ OFF** สลับ Online/Offline mode
- กด **KEY** เพื่อเปลี่ยน API Key
- กด **CREDIT bar** เพื่อตั้งค่าเครดิต
- กด **TOK** เพื่อดูรายละเอียด token

### Offline Knowledge Base
พูดถึงหัวข้อเหล่านี้ใน Offline mode:
- สุขภาพ / ยา / BMI
- เบอร์ฉุกเฉิน (191, 1669, 199)
- คณิตศาสตร์ / วิทยาศาสตร์
- ภูมิศาสตร์ / ประวัติศาสตร์ไทย
- เทคโนโลยี / การเงิน / กฎหมาย
- อาหารไทย / เทศกาล / ภาษาอังกฤษ

---

## 🔧 Customization

### เปลี่ยนชื่อ AI
```js
// ค้นหา "CIPHER" และ "ไซเฟอร์" แล้วแทนที่
```

### เปลี่ยนชื่อผู้ใช้
```js
// ค้นหา "คุณเอ็ม" แล้วแทนที่ด้วยชื่อของคุณ
```

### เพิ่ม Offline Knowledge
```json
// เพิ่มใน knowledge.json
{
  "q": ["คำค้นหา1", "คำค้นหา2"],
  "a": "คำตอบที่ต้องการ"
}
```

### เปลี่ยน Model
```js
const MODEL = 'claude-sonnet-4-5'; // ฉลาดขึ้น แต่แพงขึ้น 3x
```

---

## 📱 ติดตั้งบน iPhone (PWA)

1. เปิด Safari → เข้าลิงก์
2. กด **Share** → **Add to Home Screen**
3. ตั้งชื่อ "CIPHER" → **Add**
4. เปิดจาก Home Screen ได้เลย เหมือนแอปจริง!

---

## 🐛 Troubleshooting

| ปัญหา | วิธีแก้ |
|-------|---------|
| ไม่มีเสียง | แตะหน้าจอก่อน / เช็ค 🔊 / โหลด Thai voice ใน Settings |
| API error | เช็ค API Key / เช็คเครดิต Anthropic |
| Web search ไม่ทำงาน | เช็ค Cloudflare Worker URL ใน index.html |
| จอล้น iPhone | ใช้ Safari แทน Chrome |

---

## 📄 License

MIT License — ใช้ได้เลย แก้ได้ แจกได้ครับ

---

*Made with ❤️ — CIPHER v2.0*
