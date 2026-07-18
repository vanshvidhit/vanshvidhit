<p align="center">
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1180 610" width="100%" height="610" style="background: #030712; font-family: 'Segoe UI', system-ui, -apple-system, sans-serif;">
  <defs>
    <radialGradient id="darkBgGlow" cx="50%" cy="50%" r="70%">
      <stop offset="0%" stop-color="#7C3AED" stop-opacity="0.15">
        <animate attributeName="stop-opacity" values="0.15;0.22;0.15" dur="8s" repeatCount="indefinite" />
      </stop>
      <stop offset="60%" stop-color="#22D3EE" stop-opacity="0.05" />
      <stop offset="100%" stop-color="#030712" stop-opacity="0" />
    </radialGradient>

    <linearGradient id="accentGrad" x1="0%" y1="0%" x2="100%" y2="100%">
      <stop offset="0%" stop-color="#7C3AED" />
      <stop offset="50%" stop-color="#22D3EE" />
      <stop offset="100%" stop-color="#10B981" />
      <animateTransform attributeName="transform" type="rotate" from="0 590 305" to="360 590 305" dur="12s" repeatCount="indefinite" />
    </linearGradient>

    <linearGradient id="asciiGrad" x1="0%" y1="0%" x2="0%" y2="100%">
      <stop offset="0%" stop-color="#22D3EE" />
      <stop offset="100%" stop-color="#7C3AED" />
      <animate attributeName="y1" values="0%;20%;0%" dur="6s" repeatCount="indefinite" />
    </linearGradient>

    <filter id="glassBlur" x="-10%" y="-10%" width="120%" height="120%">
      <feGaussianBlur stdDeviation="20" result="blur" />
      <feColorMatrix type="matrix" values="1 0 0 0 0  0 1 0 0 0  0 0 1 0 0  0 0 0 18 -7" result="goo" />
    </filter>
    
    <filter id="glow" x="-20%" y="-20%" width="140%" height="140%">
      <feGaussianBlur stdDeviation="8" result="blur" />
      <feComposite in="SourceGraphic" in2="blur" operator="over" />
    </filter>
  </defs>

  <rect width="1180" height="610" fill="url(#darkBgGlow)" />

  <g opacity="0.6">
    <circle cx="200" cy="150" r="1.5" fill="#22D3EE"><animate attributeName="cy" values="150;130;150" dur="5s" repeatCount="indefinite"/></circle>
    <circle cx="850" cy="100" r="2" fill="#7C3AED"><animate attributeName="opacity" values="0.2;0.9;0.2" dur="4s" repeatCount="indefinite"/></circle>
    <circle cx="1050" cy="450" r="1" fill="#10B981"><animate attributeName="cy" values="450;470;450" dur="6s" repeatCount="indefinite"/></circle>
  </g>

  <g transform="translate(60, 60)">
    <animateTransform attributeName="transform" type="translate" values="60,60; 60,48; 60,60" dur="6s" repeatCount="indefinite" additive="sum"/>
    
    <rect width="400" height="490" rx="16" fill="#0F172A" fill-opacity="0.4" stroke="rgba(255,255,255,0.08)" stroke-width="1" />
    
    <line x1="1" y1="0" x2="399" y2="0" stroke="rgba(34,242,238,0.04)" stroke-width="4">
      <animate attributeName="y1" values="0;490;0" dur="4s" repeatCount="indefinite" />
      <animate attributeName="y2" values="0;490;0" dur="4s" repeatCount="indefinite" />
    </line>

    <g font-family="monospace" font-size="11" font-weight="bold" fill="url(#asciiGrad)" letter-spacing="1">
      <text x="30" y="60" opacity="0"><animate attributeName="opacity" to="0.8" begin="0.2s" fill="freeze"/>⚡■■■■■■■■■■■■■■■■■■■■■■■■■■■■■■■■■■■■■■■⚡</text>
      <text x="30" y="85" opacity="0"><animate attributeName="opacity" to="0.8" begin="0.4s" fill="freeze"> </animate>🤖 [SYSTEM ARCHITECTURE CORE INITIALIZED]</text>
      <text x="30" y="120" opacity="0"><animate attributeName="opacity" to="0.9" begin="0.6s" fill="freeze"/>         __   __  _      _   _  _   </text>
      <text x="30" y="140" opacity="0"><animate attributeName="opacity" to="0.9" begin="0.8s" fill="freeze"/>        \ \ / / (_) __| | | |_| |__  </text>
      <text x="30" y="160" opacity="0"><animate attributeName="opacity" to="1.0" begin="1.0s" fill="freeze"/>         \ V /  | |/ _` | | __| '_ \ </text>
      <text x="30" y="180" opacity="0"><animate attributeName="opacity" to="1.0" begin="1.2s" fill="freeze"/>          \_/   |_|\__,_| |_| |_| |_|</text>
      <text x="30" y="220" opacity="0"><animate attributeName="opacity" to="0.7" begin="1.4s" fill="freeze"/>▶ VEXARENT MODULE status = [ACTIVE COFOUNDER]</text>
      <text x="30" y="245" opacity="0"><animate attributeName="opacity" to="0.7" begin="1.6s" fill="freeze"/>▶ CONCURRENCY TRACKING = [ENGAGED (RIDEFLOW)]</text>
      <text x="30" y="270" opacity="0"><animate attributeName="opacity" to="0.7" begin="1.8s" fill="freeze"/>▶ ECOSYSTEM CONTROL = [TRANSPARENT (HOUSEHUNT)]</text>
      <text x="30" y="310" opacity="0"><animate attributeName="opacity" to="0.8" begin="2.0s" fill="freeze"/>🛡️ GLOBAL ATTAINMENTS RECORDED:</text>
      <text x="30" y="335" opacity="0"><animate attributeName="opacity" to="0.9" begin="2.2s" fill="freeze"/>  ├─ [GUINNESS WORLD RECORD CAMPAIGN THREAD]</text>
      <text x="30" y="360" opacity="0"><animate attributeName="opacity" to="0.9" begin="2.4s" fill="freeze"/>  ├─ [NODAL KABADDI GOLD MEDALIST TIER]</text>
      <text x="30" y="385" opacity="0"><animate attributeName="opacity" to="0.9" begin="2.6s" fill="freeze"/>  └─ [SERVICENOW UNIVERSITY CERTIFIED DATA]</text>
      <text x="30" y="425" opacity="0"><animate attributeName="opacity" to="1.0" begin="2.8s" fill="freeze"/>⚡■■■■■■■■■■■■■■■■■■■■■■■■■■■■■■■■■■■■■■■⚡</text>
    </g>

    <rect x="345" y="415" width="8" height="12" fill="#22D3EE">
      <animate attributeName="opacity" values="1;0;1" dur="1s" repeatCount="indefinite" />
    </rect>
  </g>

  <g transform="translate(500, 60)">
    <rect width="620" height="490" rx="16" fill="#0F172A" fill-opacity="0.7" stroke="url(#accentGrad)" stroke-width="1.5" filter="url(#glow)"/>
    
    <circle cx="30" cy="30" r="6" fill="#EF4444" />
    <circle cx="50" cy="30" r="6" fill="#F59E0B" />
    <circle cx="70" cy="30" r="6" fill="#10B981" />
    <text x="310" y="35" fill="#94A3B8" font-size="13" font-family="monospace" text-anchor="middle">vanshvidhit @ mainframes</text>

    <g fill="#F8FAFC" font-size="16" transform="translate(30, 80)">
      
      <text x="0" y="20" fill="#94A3B8" font-family="monospace">$ finger vanshvidhit</text>
      
      <text x="0" y="55" font-weight="bold" font-size="28" fill="#ffffff">Hi, I'm Vidhit Vansh</text>

      <text x="0" y="95" font-family="monospace" fill="#22D3EE" font-weight="bold">
        &gt; <tspan fill="#F8FAFC">Role:</tspan> 
        <animate attributeName="opacity" values="1;1;0;0;1" dur="8s" repeatCount="indefinite" />
        <rect x="75" y="80" width="2" height="18" fill="#22D3EE"/>
      </text>
      
      <g font-family="monospace" font-size="16" fill="#22D3EE" font-weight="bold">
        <text x="75" y="95">Full-Stack MERN Architect
          <animate attributeName="display" values="inline;none;none;none;inline" dur="8s" repeatCount="indefinite" />
        </text>
        <text x="75" y="95">MSME Startup Co-Founder
          <animate attributeName="display" values="none;inline;none;none;none" dur="8s" repeatCount="indefinite" />
        </text>
        <text x="75" y="95">Logistics Tech Engineer
          <animate attributeName="display" values="none;none;inline;none;none" dur="8s" repeatCount="indefinite" />
        </text>
        <text x="75" y="95">LNCT Operations Director
          <animate attributeName="display" values="none;none;none;inline;none" dur="8s" repeatCount="indefinite" />
        </text>
      </g>

      <g transform="translate(0, 140)" font-size="14" fill="#94A3B8">
        <text x="0" y="0" opacity="0"><animate attributeName="opacity" to="1" begin="1s" fill="freeze"/>📍 <tspan fill="#F8FAFC" font-weight="bold">Location:</tspan> Bhopal, MP, India</text>
        <text x="0" y="25" opacity="0"><animate attributeName="opacity" to="1" begin="1.3s" fill="freeze"/>🎓 <tspan fill="#F8FAFC" font-weight="bold">Education:</tspan> B.Tech in CSE Core @ LNCT Group (2027)</text>
        <text x="0" y="50" opacity="0"><animate attributeName="opacity" to="1" begin="1.6s" fill="freeze"/>🚀 <tspan fill="#F8FAFC" font-weight="bold">Current Focus:</tspan> Low-Latency Dispatch Engine Integrations</text>
        <text x="0" y="75" opacity="0"><animate attributeName="opacity" to="1" begin="1.9s" fill="freeze"/>📧 <tspan fill="#F8FAFC" font-weight="bold">Email:</tspan> vidhitvanshofficial@gmail.com</text>
      </g>

      <g transform="translate(0, 260)">
        <text x="0" y="-15" fill="#ffffff" font-weight="bold" font-size="14">⚡ Core Infrastructure Stack</text>
        
        <g transform="translate(0,0)">
          <rect width="85" height="30" rx="8" fill="rgba(34,227,238,0.1)" stroke="#22D3EE" stroke-width="1"/>
          <text x="42" y="20" fill="#22D3EE" font-size="12" text-anchor="middle" font-weight="bold">React / Next</text>
        </g>
        
        <g transform="translate(95,0)">
          <rect width="85" height="30" rx="8" fill="rgba(124,58,237,0.1)" stroke="#7C3AED" stroke-width="1"/>
          <text x="42" y="20" fill="#7C3AED" font-size="12" text-anchor="middle" font-weight="bold">Node / Express</text>
        </g>
        
        <g transform="translate(190,0)">
          <rect width="85" height="30" rx="8" fill="rgba(16,185,129,0.1)" stroke="#10B981" stroke-width="1"/>
          <text x="42" y="20" fill="#10B981" font-size="12" text-anchor="middle" font-weight="bold">MongoDB</text>
        </g>
        
        <g transform="translate(285,0)">
          <rect width="85" height="30" rx="8" fill="rgba(245,158,11,0.1)" stroke="#F59E0B" stroke-width="1"/>
          <text x="42" y="20" fill="#F59E0B" font-size="12" text-anchor="middle" font-weight="bold">Socket.io</text>
        </g>

        <g transform="translate(380,0)">
          <rect width="85" height="30" rx="8" fill="rgba(255,255,255,0.06)" stroke="rgba(255,255,255,0.2)" stroke-width="1"/>
          <text x="42" y="20" fill="#F8FAFC" font-size="12" text-anchor="middle" font-weight="bold">ServiceNow</text>
        </g>

        <g transform="translate(475,0)">
          <rect width="85" height="30" rx="8" fill="rgba(34,227,238,0.1)" stroke="#22D3EE" stroke-width="1"/>
          <text x="42" y="20" fill="#22D3EE" font-size="12" text-anchor="middle" font-weight="bold">IoT / Cyber</text>
        </g>
      </g>

      <g transform="translate(0, 360)">
        <line x1="0" y1="-15" x2="560" y2="-15" stroke="rgba(255,255,255,0.08)" stroke-width="1"/>
        
        <g transform="translate(0, 0)">
          <circle cx="15" cy="5" r="14" fill="rgba(255,255,255,0.04)" stroke="rgba(255,255,255,0.1)"/>
          <path d="M15,-4 C10,-4 6,0 6,5 C6,9 9,12 13,13.5 C13.5,13.6 13.6,13.3 13.6,13.1 C13.6,12.9 13.6,12.2 13.6,11.4 C10,12.2 9.2,10.5 9.2,10.5 C8.6,9 7.8,8.6 7.8,8.6 C6.6,7.8 7.9,7.8 7.9,7.8 C9.1,7.9 9.8,9 9.8,9 C10.9,11 12.8,10.4 13.5,10.1 C13.6,9.3 13.9,8.8 14.3,8.5 C11.4,8.2 8.4,7.1 8.4,2.1 C8.4,0.7 8.9,-0.4 9.7,-1.3 C9.6,-1.6 9.1,-3 9.6,-4.8 C9.6,-4.8 10.7,-4.5 13.1,-2.8 C14.1,-3.1 15.2,-3.2 16.2,-3.2 C17.2,-3.2 18.3,-3.1 19.3,-2.8 C21.7,-4.5 22.8,-4.8 22.8,-4.8 C23.3,-3 22.8,-1.6 22.7,-1.3 C23.5,-0.4 24,0.7 24,2.1 C24,7.2 21,8.2 18.1,8.5 C18.6,8.9 19,9.7 19,10.9 C19,12.6 19,12.9 19,13.3 C19,13.6 19.2,13.8 19.6,13.7 C23.6,12.3 26.4,8.5 26.4,5 C26.4,0 22.4,-4 15,-4 Z" fill="#94A3B8"/>
        </g>
        
        <g transform="translate(45, 0)">
          <circle cx="15" cy="5" r="14" fill="rgba(255,255,255,0.04)" stroke="rgba(255,255,255,0.1)"/>
          <path d="M10,0 L7,0 L7,10 L10,10 L10,0 Z M8.5,-1.5 C9.5,-1.5 10.2,-2.2 10.2,-3.2 C10.2,-4.2 9.5,-5 8.5,-5 C7.5,-5 6.8,-4.2 6.8,-3.2 C6.8,-2.2 7.5,-1.5 8.5,-1.5 Z M22,3.5 C22,0.2 20.3,-1.2 18,-1.2 C16.1,-1.2 15.3,-0.2 14.8,0.6 L14.8,-1 L12,-1 L12,10 L14.8,10 L14.8,4.5 C14.8,4.2 14.8,3.9 14.9,3.7 C15.2,3 15.8,2.3 16.8,2.3 C18.2,2.3 18.8,3.4 18.8,5 L18.8,10 L21.6,10 L21.6,3.5 L22,3.5 Z" fill="#94A3B8"/>
        </g>

        <text x="100" y="14" fill="#94A3B8" font-size="12" font-family="monospace">// Continuous integration pipelines online</text>
      </g>
    </g>
  </g>
</svg>
</p>

<div align="center">
  <!-- Restored Dynamic Waving Banner Header -->
  <img src="https://capsule-render.vercel.app/type=waving&color=gradient&customColorList=00f2fe,4facfe&height=180&section=header&text=VIDHIT%20VANSH&fontSize=65&fontColor=ffffff&animation=twinkling&fontAlignY=45" width="100%" alt="Cyber Horizon Banner" />
</div>

<p align="center">
  <img src="https://user-images.githubusercontent.com/74038190/212284115-f47cd8ff-2ffb-4b04-b5bf-4d1c14c0247f.gif" alt="Laser Accent Line" width="100%">
</p>

<!-- 🚀 Restored Dynamic Typing Matrix Console Loop 🚀 -->
<p align="center">
  <img src="https://readme-typing-svg.herokuapp.com?font=Fira+Code&weight=600&size=28&pause=1000&color=2E9EF7&center=true&vCenter=true&width=850&lines=Hi+there!+%F0%9F%91%8B+I'm+Vidhit+Vansh;Full+Stack+MERN+Architect;Co-Founder+at+VexaRent+🏆;Open+Source+%26+Event+Leader" alt="Typing Matrix Stream" />
</p>

<div align="center">
  <a href="https://github.com/vanshvidhit" target="_blank">
    <img src="https://img.shields.io/badge/Explore%20Active%20Systems-Click%20Here-6f42c1?style=for-the-badge&logo=github&logoColor=white&labelColor=1a1a1a&color=00c853" alt="GitHub Badge" style="border-radius: 12px; box-shadow: 0 4px 14px rgba(0, 0, 0, 0.45);">
  </a>
</div>

# 👋 Hi, I'm **Vidhit Vansh**

💻 Computer Science & Engineering Student | Startup Founder | Tech Enthusiast

<p align="center">
  <img src="https://user-images.githubusercontent.com/74038190/212284115-f47cd8ff-2ffb-4b04-b5bf-4d1c14c0247f.gif" alt="Laser Accent Line" width="100%">
</p>

## 🌌 Highlights — Startups, Scale & Top Achievements

- 🚀 **Co-Founder of VexaRent** — driving an MSME-registered rental platform leveraging AI-driven models for logistics and service fee management.
- 📜 **Guinness World Record Achiever** — recognized for participating in a massive, globally impactful AI Responsibility campaign.
- 🔒 **ServiceNow Certified** — holding professional credentials from ServiceNow University to optimize enterprise workflows.
- 💼 **Full-Stack Engineer** — architecting systems focusing on high availability, real-time sync, and security.

---

### 🕹️ REAL-TIME SYSTEM ENGINE & QUEST LOG (Core Metrics)
<table width="100%">
  <tr>
    <td width="50%" valign="top" style="background-color: #0d1117; border: 1px solid #30363d; padding: 15px; border-radius: 8px;">
      <h4>⚡ Active Operation Subsystems</h4>
      <code>🛠️ MERN Architecture</code> <br>
      <code>████████████████░░ 88%</code> <br><br>
      <code>🚀 VexaRent Core Infra</code> <br>
      <code>████████████░░░░░░ 75%</code> <br><br>
      <code>🔒 Systems Security & IoT</code> <br>
      <code>██████████░░░░░░░░ 62%</code>
    </td>
    <td width="50%" valign="top" style="background-color: #0d1117; border: 1px solid #30363d; padding: 15px; border-radius: 8px;">
      <h4>📜 Active Campaign Quest Logs</h4>
      <ul>
        <li>🎯 <b>Main Quest:</b> Scaling production logistics structures for VexaRent commercial modules.</li>
        <li>⚔️ <b>Side Quest:</b> Optimizing real-time dual-channel web frameworks via low-latency Socket.io pipelines.</li>
        <li>🏆 <b>Achievement Unlocked:</b> Guinness World Record AI Responsibility Campaign Milestone.</li>
      </ul>
    </td>
  </tr>
</table>

---

### Core Applications Ecosystem 

<table width="100%">
  <tr>
    <td width="33%" align="center" style="background-color: #0d1117; border: 1px solid #30363d; padding: 15px; border-radius: 8px;">
      <b>⚡ RideFlow (Real-time Cab Booking)</b><br>
      <sub style="color: #8b949e;">MERN stack application engineered with Socket.io for live updates, low-latency tracking, and high user throughput.</sub>
    </td>
    <td width="33%" align="center" style="background-color: #0d1117; border: 1px solid #30363d; padding: 15px; border-radius: 8px;">
      <b>🏡 HouseHunt (Property Ecosystem)</b><br>
      <sub style="color: #8b949e;">A transparent rental ecosystem giving users complete transaction visibility and streamlined property search capabilities.</sub>
    </td>
    <td width="33%" align="center" style="background-color: #0d1117; border: 1px solid #30363d; padding: 15px; border-radius: 8px;">
      <b>📦 VexaRent Core Infrastructure</b><br>
      <sub style="color: #8b949e;">Building out scalable logistics engines, service layers, and commercial architecture for an active startup.</sub>
    </td>
  </tr>
</table>

# 🚀 Startups & Entrepreneurship

### 🏢 **VexaRent — Registered MSME Startup**
<div align="left">
💡 **Building Next-Gen Logistics & Rental Solutions:**  

- Officially **co-founded and signed MOUs** to deploy intelligent service-fee architectures.
- Managing data infrastructure, vendor allocations, and digital-first logistics pipelines.
- Focused on injecting absolute market transparency into traditional rental systems.
</div>

---

### 🏆 **Event Management & Institutional Leadership**
<div align="left">

✨ I regularly orchestrate, manage, and scale high-profile tech, commercial, and creative ecosystems:  

- **The Bhopal Film Festival (TBFF):** Served as *Production, Promotion & Marketing Co-ordinator*. Directly managed cross-functional volunteer teams and headed backstage logistics, celebrity scheduling, and tactical venue flow frameworks for the Inaugural Edition at Minto Hall.
- **Lead Coordinator Roles:** Successfully managed marquee technical platforms including the **Smart India Hackathon (SIH)**, **TEDx events**, and **GDSC / DevFest hack-spaces**.
- **Media & Production Operations:** Commanded logistics, stakeholder pipelines, and character performances for professional web series productions.
- **Ecosystem Representative:** Representing **LNCT Group** across major regional and national-level technology and leadership initiatives.
</div>

<p align="center">
  <img src="https://user-images.githubusercontent.com/74038190/212284115-f47cd8ff-2ffb-4b04-b5bf-4d1c14c0247f.gif" alt="Laser Accent Line" width="100%">
</p>

<!-- 🕹️ LIVE SNAKE CONTRIBUTION GAME 🕹️ -->
<h3 align="center">🐍 My Contribution Grid Journey</h3>

<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/vanshvidhit/vanshvidhit/output/github-contribution-grid-snake-dark.svg" />
    <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/vanshvidhit/vanshvidhit/output/github-contribution-grid-snake.svg" />
    <img alt="GitHub Contribution Snake" src="https://raw.githubusercontent.com/vanshvidhit/vanshvidhit/output/github-contribution-grid-snake.svg" width="100%" />
  </picture>
</p>

<p align="center">
  <img src="https://user-images.githubusercontent.com/74038190/212284115-f47cd8ff-2ffb-4b04-b5bf-4d1c14c0247f.gif" alt="Laser Accent Line" width="100%">
</p>

# 🏅 Beyond The Code (Athletics & Art)

- 🥇 **Nodal Gold Medalist** in Kabaddi — holding top honors at the nodal tournament level representing LNCT.
- 🏊‍♂️ Active **competitive swimmer** focusing on discipline, endurance, and strategy.
- 🎸 **Classical Guitarist** & Wilderness Trekker — exploring complex compositions and remote peaks off the screen.

<p align="center">
  <img src="https://user-images.githubusercontent.com/74038190/212284115-f47cd8ff-2ffb-4b04-b5bf-4d1c14c0247f.gif" alt="Git Divider Line" width="100%">
</p>

## 🌐 Connect With Me  

<p align="center">
  <a href="https://www.linkedin.com/in/vidhit-vansh-9398a5295" target="_blank">
    <img src="https://skillicons.dev/icons?i=linkedin" height="50" alt="LinkedIn Node" />
  </a>
  <a href="https://github.com/vanshvidhit" target="_blank">
    <img src="https://skillicons.dev/icons?i=github" height="50" alt="GitHub Node" />
  </a>
  <a href="mailto:vidhitvanshofficial@gmail.com" target="_blank">
    <img src="https://skillicons.dev/icons?i=gmail" height="50" alt="Email Node" />
  </a>
</p>

<p align="center">
  <img src="https://user-images.githubusercontent.com/74038190/212284115-f47cd8ff-2ffb-4b04-b5bf-4d1c14c0247f.gif" alt="Laser Accent Line" width="100%">
</p>

## 💻 Tech Stack & Skills  

<p align="center">
  <img src="https://skillicons.dev/icons?i=html,css,js,ts,react,nextjs,vite,tailwind,nodejs,express,mongodb,mysql,sqlite,firebase,py,c,cpp,java,git,github,vscode,postman,figma,linux,windows,bash" alt="My Tech Stack Matrix" />
</p>

---

<p align="center">
  <img src="https://img.shields.io/badge/Socket.io-black?style=for-the-badge&logo=socket.io&logoColor=white" alt="Socket.io Integration Badge" />
  <img src="https://img.shields.io/badge/ServiceNow-293E40?style=for-the-badge&logo=servicenow&logoColor=white" alt="ServiceNow Badge" />
  <img src="https://img.shields.io/badge/MERN_Stack-20232a?style=for-the-badge&logo=react&logoColor=%2361DAFB" alt="MERN Framework Badge" />
</p>

<p align="center">
  <img src="https://user-images.githubusercontent.com/74038190/212284115-f47cd8ff-2ffb-4b04-b5bf-4d1c14c0247f.gif" alt="Laser Accent Line" width="100%">
</p>

## 📊 Profile Metrics Network

<p align="center">
  <img src="https://img.shields.io/badge/Total%20Contributions-45-blue?style=for-the-badge&logo=github" alt="Contributions Tracker" />
  <img src="https://img.shields.io/badge/Current%20Streak-1%20Day-orange?style=for-the-badge&logo=lightning" alt="Activity Streak Tracker" />
  <img src="https://img.shields.io/badge/Longest%20Streak-3%20Days-brightgreen?style=for-the-badge" alt="Peak Streak Milestone" />
</p>

<p align="center">
  <img src="https://komarev.com/ghpvc/?username=vanshvidhit&color=2E9EF7" height="35" alt="Active Profile Traffic Tracker" />
</p>

## 📈 Real-Time Activity Pulse Graph
<p align="center">
  <a href="https://github.com/vanshvidhit" target="_blank">
    <!-- Restored Active Pulse Graph Engine -->
    <img src="https://github-readme-activity-graph.vercel.app/graph?username=vanshvidhit&theme=tokyonight&hide_border=true&background=0d1117" width="100%" alt="Commitment Flow Graph" />
  </a>
</p>

<p align="center">
  <img src="https://user-images.githubusercontent.com/74038190/212284115-f47cd8ff-2ffb-4b04-b5bf-4d1c14c0247f.gif" alt="Laser Accent Line" width="100%">
</p>

### ✍️ Random Dev Quote
<p align="center">
  <!-- Restored Dev Quote Node Element -->
  <img src="https://quotes-github-readme.vercel.app/api?type=horizontal&theme=tokyonight" alt="Dynamic Dev Quote Badge" />
</p>

---
<p align="center">
  <!-- Hyper-reliable visitor telemetry badge node -->
  <img src="https://profile-counter.glitch.me/vanshvidhit/count.svg" alt="Active Profile Telemetry Hub" height="35" />
</p>
