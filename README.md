<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:c9a227,40:8b4500,80:3d1000,100:0d1117&height=180&section=header&text=Vinny%20Nguy%E1%BB%85n&fontColor=fff5dc&fontSize=58&animation=fadeIn&fontAlignY=38&desc=%E2%9A%94%20%C4%90%C6%A1n%20Th%C6%B0%C6%A1ng%20%C4%90%E1%BB%99c%20M%C3%A3%20%C2%B7%20M%E1%BB%99t%20M%C3%ACnh%20M%E1%BB%99t%20Ng%E1%BB%B1a%20%E2%9A%94&descAlignY=58&descSize=18&descColor=e7d3a8" width="100%" alt="Header"/>

</div>

<div align="center">

<img src="https://user-images.githubusercontent.com/74038190/241765440-80728820-e06b-4f96-9c9e-9df46f0cc0a5.gif" width="320" alt="Coding"/>

# Hi 👋, mình là **Vinny**

[![Typing SVG](https://readme-typing-svg.demolab.com?font=Fira+Code&size=26&pause=1200&color=C9A227&center=true&vCenter=true&width=900&lines=Developer+Full-Stack;%E2%9A%94+%C4%90%C6%A1n+Th%C6%B0%C6%A1ng+%C4%90%E1%BB%99c+M%C3%A3+%E2%9A%94;%F0%9F%90%8E+M%E1%BB%99t+M%C3%ACnh+M%E1%BB%99t+Ng%E1%BB%B1a;Full-Stack+%C2%B7+Automation+%C2%B7+AI+%C2%B7+Security)](https://github.com/NgVB1408)

![Projects](https://img.shields.io/badge/D%E1%BB%B0_%C3%81N-200%2B-c9a227?style=for-the-badge&labelColor=0d1117)
![Campaigns](https://img.shields.io/badge/CHI%E1%BA%BEN_D%E1%BB%8ACH-100%2B-c9a227?style=for-the-badge&labelColor=0d1117)
![Solo](https://img.shields.io/badge/SOLO-END--TO--END-c9a227?style=for-the-badge&labelColor=0d1117)
![Stack](https://img.shields.io/badge/FULL_STACK-%C2%B7_AI_%C2%B7_AUTOMATION_%C2%B7_SECURITY-c9a227?style=for-the-badge&labelColor=0d1117)

</div>

<img src="https://user-images.githubusercontent.com/74038190/212284100-561aa473-3905-4a80-b561-0d28506553ee.gif" width="100%" alt="line"/>

## 🧑‍💻 Giới thiệu

<div align="left">

```
┌─ HỒ SƠ ──────────────────────────────────────────────────┐
│                                                          │
│  • Full-Stack · Solo end-to-end                         │
│  • 200+ dự án đã giao                                   │
│  • Web · Desktop · Bot · AI · Security                  │
│  • 100+ chiến dịch marketing                            │
│  • Kiến trúc · code · deploy · vận hành                 │
│                                                          │
└──────────────────────────────────────────────────────────┘
```

</div>

---

## 💻 `vinny.py`

```python
#!/usr/bin/env python3
"""
╔══════════════════════════════════════════════════════╗
║  VINNY · Solo End-to-End Builder · v∞                ║
║  concept → architecture → code → deploy → vận hành   ║
╚══════════════════════════════════════════════════════╝
"""
import asyncio, os, random
from playwright.async_api import async_playwright
from telethon import TelegramClient
from anthropic import AsyncAnthropic
from cloudflare import Pages, D1, R2, Workers

ai   = AsyncAnthropic(api_key=os.getenv("CLAUDE_API_KEY"))
tg   = TelegramClient("vinny", os.getenv("TG_ID"), os.getenv("TG_HASH"))
cf   = Pages(token=os.getenv("CF_TOKEN"))

async def hunt(target: str):
    async with async_playwright() as p:
        browser = await p.chromium.launch(
            headless=True,
            proxy={"server": rotate_residential_proxy()},
        )
        ctx = await browser.new_context(
            user_agent=human_ua(),
            viewport=stealth_size(),
            locale="vi-VN",
        )
        page = await ctx.new_page()
        await page.add_init_script("Object.defineProperty(navigator,'webdriver',{get:()=>undefined})")
        await page.goto(target, wait_until="networkidle")

        intel  = await page.evaluate(RECON_SCRIPT)
        plan   = await ai.messages.create(
            model="claude-opus-4-7",
            messages=[{"role": "user", "content": f"Audit + rebrand:\n{intel}"}],
        )
        bundle = await rebrand(intel, blueprint=plan.content[0].text)
        domain = await cf.deploy(bundle, project=f"site-{slug()}")

        await tg.send_message("me", f"✓ {domain} live · Lighthouse 90+ · AI <15%")
        await browser.close()

async def loop():
    while True:
        task = await tg.iter_messages(filter="hunt")
        await hunt(task.url)
        await asyncio.sleep(random.randint(30, 90))  # human jitter

if __name__ == "__main__":
    asyncio.run(loop())
```

```bash
$ python vinny.py
[*] Initializing async runtime...
[+] Playwright stealth: webdriver cloaked
[+] Proxy rotated: 103.x.x.x (VN residential)
[+] Recon target: ████████.com — 47 endpoints mapped
[+] Claude Opus: rebrand plan generated (4.2s)
[+] Cloudflare Pages: bundle deployed → ████-████.pages.dev
[+] Custom domain attached · SSL active
[OK] Site live · Lighthouse 94 · AI detection 11%
```

<img src="https://user-images.githubusercontent.com/74038190/212284100-561aa473-3905-4a80-b561-0d28506553ee.gif" width="100%" alt="line"/>

## 🛠 Tech Stack

### Programming Languages
<div align="center">

![Python](https://img.shields.io/badge/Python-3776ab?style=for-the-badge&logo=python&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![Node.js](https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=nodedotjs&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178c6?style=for-the-badge&logo=typescript&logoColor=white)
![HTML5](https://img.shields.io/badge/HTML5-E34C26?style=for-the-badge&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)

</div>

### Frontend & UI
<div align="center">

![Next.js](https://img.shields.io/badge/Next.js-000000?style=for-the-badge&logo=nextdotjs&logoColor=white)
![React](https://img.shields.io/badge/React-61DAFB?style=for-the-badge&logo=react&logoColor=black)
![SvelteKit](https://img.shields.io/badge/SvelteKit-FF3E00?style=for-the-badge&logo=svelte&logoColor=white)
![TailwindCSS](https://img.shields.io/badge/TailwindCSS-06B6D4?style=for-the-badge&logo=tailwindcss&logoColor=white)
![WordPress](https://img.shields.io/badge/WordPress-21759B?style=for-the-badge&logo=wordpress&logoColor=white)

</div>

### Desktop & GUI
<div align="center">

![PyQt5](https://img.shields.io/badge/PyQt5-41CD52?style=for-the-badge&logo=qt&logoColor=white)
![Tkinter](https://img.shields.io/badge/Tkinter-FFD43B?style=for-the-badge&logo=python&logoColor=black)
![PyInstaller](https://img.shields.io/badge/PyInstaller-FF6B6B?style=for-the-badge&logo=python&logoColor=white)
![Electron](https://img.shields.io/badge/Electron-47848F?style=for-the-badge&logo=electron&logoColor=white)

</div>

### Web Automation & Scraping
<div align="center">

![Playwright](https://img.shields.io/badge/Playwright-2EAD33?style=for-the-badge&logo=playwright&logoColor=white)
![Puppeteer](https://img.shields.io/badge/Puppeteer-40B5A4?style=for-the-badge&logo=puppeteer&logoColor=white)
![Selenium](https://img.shields.io/badge/Selenium-43B02A?style=for-the-badge&logo=selenium&logoColor=white)
![BeautifulSoup4](https://img.shields.io/badge/BeautifulSoup4-3776ab?style=for-the-badge&logo=python&logoColor=white)
![ChromeExt](https://img.shields.io/badge/Chrome_Extension-4285F4?style=for-the-badge&logo=googlechrome&logoColor=white)

</div>

### Messaging & Social
<div align="center">

![Telethon](https://img.shields.io/badge/Telethon_Pyrogram-26A5E4?style=for-the-badge&logo=telegram&logoColor=white)
![TelegramBot](https://img.shields.io/badge/Telegram_Bot-26A5E4?style=for-the-badge&logo=telegram&logoColor=white)
![Facebook](https://img.shields.io/badge/Facebook_Automation-1877F2?style=for-the-badge&logo=facebook&logoColor=white)
![Zalo](https://img.shields.io/badge/Zalo_Dev-0068FF?style=for-the-badge&logo=zalo&logoColor=white)
![GoogleAds](https://img.shields.io/badge/Ads_Automation-4285F4?style=for-the-badge&logo=googleads&logoColor=white)

</div>

### AI & Machine Learning
<div align="center">

![OpenAI](https://img.shields.io/badge/OpenAI_API-412991?style=for-the-badge&logo=openai&logoColor=white)
![Claude](https://img.shields.io/badge/Anthropic_Claude-D97757?style=for-the-badge&logo=anthropic&logoColor=white)
![Gemini](https://img.shields.io/badge/Google_Gemini-4285F4?style=for-the-badge&logo=google&logoColor=white)
![Ollama](https://img.shields.io/badge/Ollama_Self_Host-000000?style=for-the-badge&logo=ollama&logoColor=white)
![ChromaDB](https://img.shields.io/badge/ChromaDB_RAG-FF6B6B?style=for-the-badge&logo=databricks&logoColor=white)

</div>

### Cloud & Infrastructure
<div align="center">

![Cloudflare](https://img.shields.io/badge/Cloudflare_Pages-F38020?style=for-the-badge&logo=cloudflare&logoColor=white)
![CF Workers](https://img.shields.io/badge/CF_Workers_+_D1_+_R2-F38020?style=for-the-badge&logo=cloudflare&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-336791?style=for-the-badge&logo=postgresql&logoColor=white)
![Linux](https://img.shields.io/badge/Linux_Server-FCC624?style=for-the-badge&logo=linux&logoColor=black)

</div>

### Payment VN
<div align="center">

![VietQR](https://img.shields.io/badge/VietQR-DA251D?style=for-the-badge&logoColor=white)
![SePay](https://img.shields.io/badge/SePay-1F8B4C?style=for-the-badge&logoColor=white)
![MoMo](https://img.shields.io/badge/MoMo-A50064?style=for-the-badge&logoColor=white)
![Banking](https://img.shields.io/badge/Banking_API-2196F3?style=for-the-badge&logoColor=white)

</div>

<img src="https://user-images.githubusercontent.com/74038190/212284100-561aa473-3905-4a80-b561-0d28506553ee.gif" width="100%" alt="line"/>

## 🚀 Mảng dự án có thể nhận

<div align="center">

```
┌─ WEB PROJECTS ──────────────┐  ┌─ DESKTOP APPS ──────────────┐
│ • Web app full-stack        │  │ • PyQt5 / Qt6 GUI           │
│ • Next.js · SvelteKit SPA   │  │ • Tkinter tool nội bộ       │
│ • WordPress + custom theme  │  │ • Bundle .exe PyInstaller   │
│ • Chrome Extension MV3      │  │ • Cross-platform support    │
│ • Realtime + SSE + WebSocket│  │ • System tray · hotkey      │
└─────────────────────────────┘  └─────────────────────────────┘

┌─ AUTOMATION & BOTS ─────────┐  ┌─ AI SOLUTIONS ──────────────┐
│ • Web scraping + crawling   │  │ • LLM integration multi-API │
│ • Bot Telegram + Discord    │  │ • RAG search trên corpus    │
│ • RPA / form automation     │  │ • Computer vision · OCR     │
│ • Social media bot          │  │ • Voice cloning · Whisper   │
│ • API integration sâu       │  │ • AI image enhance pipeline │
└─────────────────────────────┘  └─────────────────────────────┘

┌─ SECURITY ──────────────────┐  ┌─ DEVOPS ────────────────────┐
│ • Web app pentest           │  │ • Docker containerization   │
│ • Android security audit    │  │ • Linux server admin        │
│ • Reverse engineering       │  │ • Cloudflare Tunnel · DNS   │
│ • Vulnerability assessment  │  │ • CI/CD GitHub Actions      │
│ • Code audit · supply chain │  │ • Database backup · restore │
└─────────────────────────────┘  └─────────────────────────────┘

┌─ FINTECH / P2P ─────────────┐  ┌─ SEO AUTOMATION ────────────┐
│ • Bot điều phối P2P USDT    │  │ • Multi-agent site builder  │
│ • Anti-ban IP + jitter      │  │ • URL → site live vài phút  │
│ • Auto-take · auto-withdraw │  │ • Lighthouse 90+ · AI < 15% │
│ • Payment VN tích hợp sâu   │  │ • Clone + rebrand pipeline  │
│ • Booking / order lifecycle │  │ • Hạ tầng độc lập per site  │
└─────────────────────────────┘  └─────────────────────────────┘
```

</div>

<img src="https://user-images.githubusercontent.com/74038190/212284100-561aa473-3905-4a80-b561-0d28506553ee.gif" width="100%" alt="line"/>

## 📊 GitHub Activity

<div align="center">

![Profile Views](https://komarev.com/ghpvc/?username=NgVB1408&style=for-the-badge&color=c9a227&labelColor=0d1117)

<a href="https://github.com/NgVB1408">
<img src="https://github-readme-stats.vercel.app/api?username=NgVB1408&show_icons=true&theme=radical&hide_border=true&include_all_commits=true&count_private=true" height="180" alt="GitHub Stats"/>
</a>
<a href="https://github.com/NgVB1408">
<img src="https://github-readme-streak-stats.herokuapp.com/?user=NgVB1408&theme=radical&hide_border=true" height="180" alt="GitHub Streak"/>
</a>

<a href="https://github.com/NgVB1408">
<img src="https://github-readme-stats.vercel.app/api/top-langs/?username=NgVB1408&layout=compact&theme=radical&hide_border=true&langs_count=10" height="180" alt="Top Languages"/>
</a>

</div>

### 🏆 GitHub Trophies

<div align="center">

[![trophy](https://github-profile-trophy.vercel.app/?username=NgVB1408&theme=radical&no-frame=true&no-bg=true&margin-w=8&row=1&column=7)](https://github.com/NgVB1408)

</div>

### 🐍 Contribution Snake

<div align="center">

![Snake animation](https://raw.githubusercontent.com/NgVB1408/NgVB1408/output/github-contribution-grid-snake-dark.svg)

</div>

<img src="https://user-images.githubusercontent.com/74038190/212284100-561aa473-3905-4a80-b561-0d28506553ee.gif" width="100%" alt="line"/>

## 🎯 Tại sao chọn mình

<div align="center">

✅ **Solo end-to-end** — không phụ thuộc team  
✅ **Code chuẩn từ đầu** — clean architecture · type safety · error handling  
✅ **Hiểu thị trường VN** — payment, ngôn ngữ, anti-ban thực chiến  
✅ **Tech stack rộng** — chọn đúng tool cho từng bài toán  
✅ **Tự vận hành** — không cần micromanage  
✅ **Giữ kín** — khách yêu cầu NDA, không bao giờ public  

</div>

<img src="https://user-images.githubusercontent.com/74038190/212284100-561aa473-3905-4a80-b561-0d28506553ee.gif" width="100%" alt="line"/>

## 📬 Liên hệ

<div align="center">

[![Telegram](https://img.shields.io/badge/Telegram-@Leader8388-26A5E4?style=for-the-badge&logo=telegram&logoColor=white)](https://t.me/leader8388)
[![Email](https://img.shields.io/badge/Email-ngvanbitkg1%40gmail.com-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:ngvanbitkg1@gmail.com)
[![GitHub](https://img.shields.io/badge/GitHub-NgVB1408-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/NgVB1408)

</div>

---

<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:0d1117,40:3d1000,75:8b4500,100:c9a227&height=120&section=footer" width="100%" alt="Footer"/>

**_⚔ Đơn Thương Độc Mã · Một Mình Một Ngựa ⚔_**

</div>
