<!DOCTYPE html>
<html lang="th">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>นามบัตร รัฐภูมิ สมบูรณ์</title>
<link href="https://fonts.googleapis.com/css2?family=Sarabun:wght@300;400;600;700&family=Space+Grotesk:wght@300;400;500;600;700&family=Space+Mono:wght@400;700&display=swap" rel="stylesheet">
<style>
*, *::before, *::after { margin:0; padding:0; box-sizing:border-box; }

body {
  background: #080c14;
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 60px;
  padding: 64px 24px;
}

.label {
  font-family: 'Space Mono', monospace;
  font-size: 8px;
  letter-spacing: 4px;
  text-transform: uppercase;
  color: #5070a0;
  margin-bottom: -48px;
}

/* ══════════ FRONT ══════════ */
.front {
  width: 540px;
  height: 300px;
  border-radius: 18px;
  position: relative;
  overflow: hidden;
  background: #0d1420;
  border: 1px solid rgba(255,255,255,0.06);
  box-shadow:
    0 0 0 1px rgba(255,255,255,0.04),
    0 40px 80px rgba(0,0,0,0.7),
    inset 0 1px 0 rgba(255,255,255,0.07);
  animation: rise .9s cubic-bezier(.22,1,.36,1) both;
  transition: transform .4s ease, box-shadow .4s ease;
  cursor: default;
}
.front:hover {
  transform: translateY(-8px) rotateX(2deg);
  box-shadow:
    0 0 0 1px rgba(220,30,30,0.3),
    0 50px 100px rgba(0,0,0,0.8),
    0 0 40px rgba(220,30,30,0.06),
    inset 0 1px 0 rgba(255,255,255,0.1);
}

/* mesh gradient bg */
.front .mesh {
  position: absolute; inset: 0;
  background:
    radial-gradient(ellipse at 75% 20%, rgba(220,30,30,0.09) 0%, transparent 55%),
    radial-gradient(ellipse at 20% 80%, rgba(30,80,200,0.07) 0%, transparent 50%);
}

/* top scan line */
.front .scanline {
  position: absolute;
  top: 0; left: 0; right: 0;
  height: 2px;
  background: linear-gradient(90deg, transparent 0%, #dc1e1e 30%, #dc1e1e 70%, transparent 100%);
  opacity: .8;
}

/* subtle grid */
.front .grid-bg {
  position: absolute; inset: 0;
  background-image:
    linear-gradient(rgba(255,255,255,0.018) 1px, transparent 1px),
    linear-gradient(90deg, rgba(255,255,255,0.018) 1px, transparent 1px);
  background-size: 32px 32px;
}

/* left content */
.front .lc {
  position: absolute;
  left: 36px; top: 0; bottom: 0;
  display: flex;
  flex-direction: column;
  justify-content: center;
  width: 240px;
  z-index: 2;
}

.front .fc-mark {
  font-family: 'Space Mono', monospace;
  font-size: 9px;
  letter-spacing: 5px;
  color: #dc1e1e;
  text-transform: uppercase;
  margin-bottom: 20px;
  display: flex;
  align-items: center;
  gap: 8px;
}
.front .fc-mark::before {
  content: '';
  display: block;
  width: 18px; height: 1px;
  background: #dc1e1e;
}

.front .name-th {
  font-family: 'Sarabun', sans-serif;
  font-size: 28px;
  font-weight: 700;
  color: #f4f6fa;
  line-height: 1.15;
  letter-spacing: 1px;
}

.front .name-en {
  font-family: 'Space Grotesk', sans-serif;
  font-size: 10.5px;
  font-weight: 300;
  color: #7090c0;
  letter-spacing: 3px;
  text-transform: uppercase;
  margin-top: 7px;
}

.front .role-wrap {
  display: flex;
  align-items: center;
  gap: 8px;
  margin-top: 18px;
}
.front .role-bracket {
  font-family: 'Space Mono', monospace;
  font-size: 11px;
  color: #dc1e1e;
  opacity: .6;
}
.front .role {
  font-family: 'Space Grotesk', sans-serif;
  font-size: 10px;
  font-weight: 500;
  letter-spacing: 3px;
  text-transform: uppercase;
  color: #90a8c8;
}

/* vertical divider */
.front .vdivide {
  position: absolute;
  left: 300px; top: 40px; bottom: 40px;
  width: 1px;
  background: linear-gradient(180deg, transparent, rgba(255,255,255,0.08) 20%, rgba(255,255,255,0.08) 80%, transparent);
  z-index: 2;
}

/* right content */
.front .rc {
  position: absolute;
  left: 324px; right: 32px;
  top: 0; bottom: 0;
  display: flex;
  flex-direction: column;
  justify-content: center;
  gap: 14px;
  z-index: 2;
}

.front .c-row {
  display: flex;
  align-items: center;
  gap: 12px;
}
.front .c-row svg {
  width: 13px; height: 13px;
  stroke: #dc1e1e;
  fill: none;
  stroke-width: 1.5;
  flex-shrink: 0;
  opacity: .8;
}
.front .c-col {}
.front .c-tag {
  font-family: 'Space Mono', monospace;
  font-size: 7px;
  letter-spacing: 2px;
  color: #5070a0;
  text-transform: uppercase;
}
.front .c-val {
  word-break: normal;
  font-family: 'Space Grotesk', sans-serif;
  font-size: 9.5px;
  font-weight: 400;
  color: #a8c0e0;
  letter-spacing: .5px;
  margin-top: 1px;
}

/* bottom bar */
.front .bot-bar {
  position: absolute;
  left: 0; right: 0; bottom: 0;
  height: 36px;
  background: rgba(255,255,255,0.02);
  border-top: 1px solid rgba(255,255,255,0.04);
  display: flex;
  align-items: center;
  padding: 0 36px;
  gap: 6px;
  z-index: 2;
}
.front .bot-bar svg {
  width: 10px; height: 10px;
  stroke: #5070a0;
  fill: none;
  stroke-width: 1.5;
}
.front .bot-url {
  font-family: 'Space Mono', monospace;
  font-size: 8px;
  letter-spacing: 2px;
  color: #5070a0;
  text-transform: lowercase;
}
.front .bot-dot {
  margin-left: auto;
  width: 6px; height: 6px;
  border-radius: 50%;
  background: #dc1e1e;
  box-shadow: 0 0 6px #dc1e1e;
}

/* corner hex */
.front .hex {
  position: absolute;
  top: 20px; right: 28px;
  font-family: 'Space Mono', monospace;
  font-size: 8px;
  color: rgba(255,255,255,0.06);
  letter-spacing: 2px;
  z-index: 2;
}

/* ══════════ BACK ══════════ */
.back {
  width: 540px;
  height: 300px;
  border-radius: 18px;
  position: relative;
  overflow: hidden;
  background: #0b0f1a;
  border: 1px solid rgba(255,255,255,0.05);
  box-shadow: 0 40px 80px rgba(0,0,0,0.7);
  animation: rise .95s .08s cubic-bezier(.22,1,.36,1) both;
  transition: transform .4s ease;
  cursor: default;
}
.back:hover { transform: translateY(-6px); }

.back .b-mesh {
  position: absolute; inset: 0;
  background:
    radial-gradient(ellipse at 50% 50%, rgba(220,30,30,0.05) 0%, transparent 65%),
    radial-gradient(ellipse at 90% 90%, rgba(30,80,200,0.06) 0%, transparent 50%);
}
.back .b-grid {
  position: absolute; inset: 0;
  background-image:
    linear-gradient(rgba(255,255,255,0.015) 1px, transparent 1px),
    linear-gradient(90deg, rgba(255,255,255,0.015) 1px, transparent 1px);
  background-size: 36px 36px;
}

/* scan line bottom */
.back .b-scan {
  position: absolute;
  bottom: 0; left: 0; right: 0;
  height: 2px;
  background: linear-gradient(90deg, transparent, #dc1e1e 40%, #dc1e1e 60%, transparent);
}

.back .b-content {
  position: relative; z-index: 2;
  height: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 10px;
}

.back .b-logo {
  font-family: 'Space Grotesk', sans-serif;
  font-weight: 700;
  font-size: 64px;
  letter-spacing: 10px;
  color: rgba(255,255,255,0.07);
  text-transform: uppercase;
  position: absolute;
  user-select: none;
}

.back .b-name {
  font-family: 'Space Grotesk', sans-serif;
  font-weight: 700;
  font-size: 42px;
  letter-spacing: 8px;
  text-transform: uppercase;
  position: relative;
  background: linear-gradient(135deg, #c0d0e8 0%, #6080a8 60%, #304060 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}
.back .b-name .red {
  background: linear-gradient(135deg, #ff3333 0%, #991111 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

.back .b-tagline {
  font-family: 'Space Mono', monospace;
  font-size: 8px;
  letter-spacing: 5px;
  color: #4a6080;
  text-transform: uppercase;
  position: relative;
}

.back .b-url {
  font-family: 'Space Mono', monospace;
  font-size: 9px;
  letter-spacing: 2.5px;
  color: #5a7898;
  margin-top: 2px;
  position: relative;
}

/* corner marks */
.back .corner {
  position: absolute;
  width: 16px; height: 16px;
}
.back .corner svg { width: 16px; height: 16px; stroke: rgba(220,30,30,.25); fill: none; stroke-width: 1.5; }
.back .tl { top: 16px; left: 16px; }
.back .tr { top: 16px; right: 16px; transform: scaleX(-1); }
.back .bl { bottom: 16px; left: 16px; transform: scaleY(-1); }
.back .br { bottom: 16px; right: 16px; transform: scale(-1); }

@keyframes rise {
  from { opacity:0; transform: translateY(32px) scale(.97); }
  to   { opacity:1; transform: translateY(0) scale(1); }
}

@media (max-width: 580px) {
  .front, .back { width: 360px; height: 200px; }
  .front .lc { left: 24px; width: 160px; }
  .front .name-th { font-size: 20px; }
  .front .vdivide { left: 200px; }
  .front .rc { left: 216px; right: 20px; gap: 9px; }
  .front .c-val {
  word-break: normal; font-size: 9px; }
  .back .b-name { font-size: 30px; letter-spacing: 5px; }
}
</style>
</head>
<body>

<span class="label">// front</span>

<div class="front">
  <div class="mesh"></div>
  <div class="grid-bg"></div>
  <div class="scanline"></div>
  <div class="hex">FC-2026</div>

  <div class="lc">
    <div class="fc-mark">FIRECOM</div>
    <div class="name-th">รัฐภูมิ<br>สมบูรณ์</div>
    <div class="name-en">Rattapoom Somboon</div>
    <div class="role-wrap">
      <span class="role-bracket">[</span>
      <span class="role">Sale Executive</span>
      <span class="role-bracket">]</span>
    </div>
  </div>

  <div class="vdivide"></div>

  <div class="rc">
    <div class="c-row">
      <svg viewBox="0 0 24 24"><path d="M22 16.92v3a2 2 0 01-2.18 2 19.79 19.79 0 01-8.63-3.07A19.5 19.5 0 013.07 10.8 19.79 19.79 0 010 2.18 2 2 0 012 0h3a2 2 0 012 1.72c.13.96.36 1.9.7 2.81a2 2 0 01-.45 2.11L6.91 7.91a16 16 0 006.08 6.08l1.27-1.27a2 2 0 012.11-.45c.91.34 1.85.57 2.81.7A2 2 0 0122 16.92z"/></svg>
      <div class="c-col">
        <div class="c-tag">Mobile</div>
        <div class="c-val">091-792-4016</div>
      </div>
    </div>
    <div class="c-row">
      <svg viewBox="0 0 24 24"><rect x="3" y="3" width="18" height="18" rx="2"/><path d="M3 9h18M9 21V9"/></svg>
      <div class="c-col">
        <div class="c-tag">Office</div>
        <div class="c-val">055-219200</div>
      </div>
    </div>
    <div class="c-row">
      <svg viewBox="0 0 24 24"><path d="M21 15a2 2 0 01-2 2H7l-4 4V5a2 2 0 012-2h14a2 2 0 012 2z"/></svg>
      <div class="c-col">
        <div class="c-tag">Line</div>
        <div class="c-val">kung_ra</div>
      </div>
    </div>
    <div class="c-row">
      <svg viewBox="0 0 24 24"><path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"/><polyline points="22,6 12,13 2,6"/></svg>
      <div class="c-col">
        <div class="c-tag">Email</div>
        <div class="c-val">firecomphitsanulok<br>@firecom.co.th</div>
      </div>
    </div>
  </div>

  <div class="bot-bar">
    <svg viewBox="0 0 24 24"><circle cx="12" cy="12" r="10"/><line x1="2" y1="12" x2="22" y2="12"/><path d="M12 2a15.3 15.3 0 014 10 15.3 15.3 0 01-4 10 15.3 15.3 0 01-4-10 15.3 15.3 0 014-10z"/></svg>
    <span class="bot-url">www.firecom.co.th</span>
    <div class="bot-dot"></div>
  </div>
</div>

<span class="label">// back</span>

<div class="back">
  <div class="b-mesh"></div>
  <div class="b-grid"></div>
  <div class="b-scan"></div>

  <div class="corner tl"><svg viewBox="0 0 16 16"><path d="M1 8V1h7"/></svg></div>
  <div class="corner tr"><svg viewBox="0 0 16 16"><path d="M1 8V1h7"/></svg></div>
  <div class="corner bl"><svg viewBox="0 0 16 16"><path d="M1 8V1h7"/></svg></div>
  <div class="corner br"><svg viewBox="0 0 16 16"><path d="M1 8V1h7"/></svg></div>

  <div class="b-content">
    <div class="b-logo">FIRECOM</div>
    <div class="b-name">FIRE<span class="red">COM</span></div>
    <div class="b-tagline">Firecom Group</div>
    <div class="b-url">www.firecom.co.th</div>
  </div>
</div>

</body>
</html>
