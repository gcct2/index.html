# index.html
<!DOCTYPE html>
<html lang="zh-CN">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no, viewport-fit=cover">
  <meta name="theme-color" content="#6dcfea">
  <meta name="color-scheme" content="light">
  <meta name="description" content="糖果岛塔防：八路糖果军团来袭的卡通塔防小游戏。选塔、布阵、升级，守住中央的水晶蛋糕；手机与桌面浏览器即开即玩，也可安装到桌面离线游玩。">
  <title>糖果岛塔防 · Candy Isle TD</title>
  <link rel="icon" href="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 64 64'%3E%3Crect width='64' height='64' rx='16' fill='%23ffd6e2'/%3E%3Cpath d='M18 48c0-6 3-9 8-9s8 3 8 9c0 2-2 4-4 4H22c-2 0-4-2-4-4z' fill='%23ff8fad' stroke='%23372b4b' stroke-width='3'/%3E%3Ccircle cx='32' cy='26' r='13' fill='%23ff7b9f' stroke='%23372b4b' stroke-width='3'/%3E%3Cpath d='M32 15c6 0 11 5 11 11 0 4-2 8-6 10' fill='none' stroke='%23fff9ee' stroke-width='4' stroke-linecap='round'/%3E%3C/svg%3E">
  <meta property="og:type" content="website">
  <meta property="og:site_name" content="糖果岛塔防">
  <meta property="og:title" content="糖果岛塔防 · 八路来袭，守住水晶蛋糕">
  <meta property="og:description" content="选塔、布阵、升级，在八条糖果大道上守住中央的水晶蛋糕。手机与电脑都能直接开玩，可安装到桌面离线游玩。">
  <meta property="og:locale" content="zh_CN">
  <meta name="twitter:card" content="summary">
  <meta name="twitter:title" content="糖果岛塔防 · Candy Isle TD">
  <meta name="twitter:description" content="八路糖果军团来袭，用五种防御塔守住中央的水晶蛋糕。">
  <style>
:root {
  --ink: #372b4b;
  --ink-soft: #726781;
  --paper: #fff9ee;
  --paper-deep: #fff0d2;
  --pink: #ff7b9f;
  --pink-deep: #ec5b84;
  --mint: #75ddbb;
  --mint-deep: #39a888;
  --sky: #75d5f2;
  --blue: #72b9ff;
  --violet: #a88bff;
  --sun: #ffd45f;
  --orange: #ffab68;
  --red: #ff6c6c;
  --line: #3e3150;
  --shadow-hard: rgba(48, 34, 66, 0.18);
  --shadow-soft: rgba(48, 34, 66, 0.12);
}

* {
  box-sizing: border-box;
}

html,
body {
  height: 100%;
}

body {
  margin: 0;
  overflow: hidden;
  color: var(--ink);
  font-family: "Arial Rounded MT Bold", "Segoe UI", "Microsoft YaHei", "PingFang SC", sans-serif;
  font-weight: 700;
  background:
    radial-gradient(circle at 18% 12%, rgba(255, 255, 255, 0.52) 0 2px, transparent 3px),
    radial-gradient(circle at 82% 28%, rgba(255, 255, 255, 0.4) 0 2px, transparent 3px),
    radial-gradient(circle at 42% 86%, rgba(255, 255, 255, 0.35) 0 1.5px, transparent 2.5px),
    linear-gradient(145deg, #7ad8ef 0%, #86e1db 48%, #bcead5 100%);
  background-size: 160px 160px, 210px 210px, 120px 120px, 100% 100%;
  user-select: none;
  -webkit-tap-highlight-color: transparent;
}

body::before,
body::after {
  content: "";
  position: fixed;
  border-radius: 999px;
  pointer-events: none;
  z-index: 0;
}

body::before {
  width: 46vw;
  height: 46vw;
  max-width: 640px;
  max-height: 640px;
  left: -20vw;
  bottom: -18vw;
  background: radial-gradient(circle at 60% 40%, rgba(255, 255, 255, 0.18), rgba(255, 255, 255, 0) 66%);
}

body::after {
  width: 38vw;
  height: 38vw;
  max-width: 560px;
  max-height: 560px;
  right: -14vw;
  top: -12vw;
  background: radial-gradient(circle at 40% 60%, rgba(255, 255, 255, 0.2), rgba(255, 255, 255, 0) 68%);
}

.ambient-cloud {
  position: fixed;
  z-index: 0;
  border-radius: 999px;
  background: rgba(255, 255, 255, 0.42);
  filter: blur(1px);
  pointer-events: none;
  animation: cloud-drift 28s ease-in-out infinite alternate;
}

.ambient-cloud::before,
.ambient-cloud::after {
  content: "";
  position: absolute;
  border-radius: 999px;
  background: inherit;
}

.cloud-a {
  width: 180px;
  height: 38px;
  left: 4vw;
  top: 13vh;
}

.cloud-a::before {
  width: 70px;
  height: 70px;
  left: 22px;
  bottom: 8px;
}

.cloud-a::after {
  width: 48px;
  height: 48px;
  right: 28px;
  bottom: 4px;
}

.cloud-b {
  width: 240px;
  height: 46px;
  right: 5vw;
  top: 22vh;
  opacity: 0.58;
  animation-delay: -8s;
}

.cloud-b::before {
  width: 90px;
  height: 90px;
  left: 40px;
  bottom: 8px;
}

.cloud-b::after {
  width: 58px;
  height: 58px;
  right: 36px;
  bottom: 4px;
}

.cloud-c {
  width: 140px;
  height: 30px;
  left: 42vw;
  bottom: 7vh;
  opacity: 0.42;
  animation-delay: -15s;
}

.cloud-c::before {
  width: 54px;
  height: 54px;
  left: 24px;
  bottom: 6px;
}

.cloud-c::after {
  width: 38px;
  height: 38px;
  right: 20px;
  bottom: 3px;
}

@keyframes cloud-drift {
  from { transform: translate3d(-14px, 4px, 0); }
  to { transform: translate3d(24px, -10px, 0); }
}

button {
  font: inherit;
  color: inherit;
}

button:focus-visible {
  outline: 3px solid #ffe071;
  outline-offset: 3px;
}

#app {
  position: relative;
  z-index: 1;
  width: 100%;
  max-width: 1780px;
  height: 100dvh;
  margin: 0 auto;
  padding: 12px 16px 14px;
  display: flex;
  flex-direction: column;
  gap: 11px;
}

/* ---------- top bar ---------- */

.topbar {
  flex: none;
  min-height: 72px;
  display: flex;
  align-items: center;
  gap: 18px;
  padding: 9px 12px 9px 14px;
  border: 3px solid var(--line);
  border-radius: 24px;
  background: rgba(255, 250, 239, 0.94);
  box-shadow: 0 6px 0 rgba(48, 34, 66, 0.16), 0 14px 30px rgba(48, 34, 66, 0.09);
  backdrop-filter: blur(12px);
}

.brand {
  display: flex;
  align-items: center;
  gap: 11px;
  min-width: 220px;
}

.brand-mark {
  width: 50px;
  height: 50px;
  display: grid;
  place-items: center;
  flex: none;
  font-size: 29px;
  border: 3px solid var(--line);
  border-radius: 17px;
  background: linear-gradient(145deg, #ffd7e6, #ffa9c3 62%, #ff8cb4);
  box-shadow: inset 0 3px 0 rgba(255, 255, 255, 0.65), 0 3px 0 rgba(48, 34, 66, 0.15);
  transform: rotate(-4deg);
}

.brand-copy h1 {
  margin: 0;
  font-size: 21px;
  line-height: 1.1;
  letter-spacing: 0.6px;
  text-shadow: 0 2px 0 rgba(255, 255, 255, 0.55);
  white-space: nowrap;
}

.brand-copy p {
  margin: 4px 0 0;
  color: var(--ink-soft);
  font-size: 10.5px;
  letter-spacing: 0.4px;
  white-space: nowrap;
}

.hud {
  display: flex;
  align-items: stretch;
  justify-content: center;
  gap: 7px;
  flex: 1;
  min-width: 0;
}

.hud-stat {
  min-width: 78px;
  display: flex;
  align-items: center;
  gap: 7px;
  padding: 6px 9px;
  border: 2px solid rgba(62, 49, 80, 0.16);
  border-radius: 14px;
  background: rgba(255, 255, 255, 0.66);
}

.hud-icon {
  display: grid;
  place-items: center;
  width: 25px;
  height: 25px;
  flex: none;
  font-size: 17px;
  filter: drop-shadow(0 1px 0 rgba(255, 255, 255, 0.6));
}

.hud-copy {
  min-width: 0;
  display: flex;
  flex-direction: column;
  line-height: 1;
}

.hud-label {
  margin-bottom: 4px;
  color: var(--ink-soft);
  font-size: 9px;
  letter-spacing: 1px;
}

.hud-copy strong {
  font-size: 17px;
  line-height: 1;
  letter-spacing: 0.3px;
  white-space: nowrap;
}

.hud-copy strong small {
  margin-left: 1px;
  color: var(--ink-soft);
  font-size: 9.5px;
  font-weight: 800;
}

.hud-hp {
  min-width: 108px;
  padding-right: 10px;
}

.hud-hp .hud-copy strong {
  color: #e85874;
}

.hp-track {
  display: block;
  width: 100%;
  height: 4px;
  margin-top: 4px;
  overflow: hidden;
  border-radius: 99px;
  background: rgba(62, 49, 80, 0.14);
}

.hp-track i {
  display: block;
  width: 100%;
  height: 100%;
  border-radius: inherit;
  background: linear-gradient(90deg, #ff819c, #ffb36b);
  transition: width 0.25s ease, background 0.25s ease;
}

.hud-hp.is-low {
  animation: hud-pulse 0.85s ease-in-out infinite alternate;
  border-color: rgba(232, 88, 116, 0.4);
  background: #fff0f1;
}

.hud-hp.is-low .hp-track i {
  background: linear-gradient(90deg, #ff4d5d, #ff8b6e);
}

@keyframes hud-pulse {
  from { transform: translateY(0); }
  to { transform: translateY(-2px); }
}

.top-actions {
  display: flex;
  align-items: center;
  gap: 7px;
  flex: none;
}

.icon-btn {
  width: 39px;
  height: 39px;
  display: grid;
  place-items: center;
  padding: 0;
  border: 2.5px solid var(--line);
  border-radius: 13px;
  background: #fffdf8;
  box-shadow: 0 3px 0 rgba(48, 34, 66, 0.16);
  font-size: 17px;
  cursor: pointer;
  transition: transform 0.12s ease, box-shadow 0.12s ease, background 0.12s ease;
}

.icon-btn:hover {
  transform: translateY(-1px);
  background: #fff8dc;
  box-shadow: 0 4px 0 rgba(48, 34, 66, 0.14);
}

.icon-btn:active {
  transform: translateY(2px);
  box-shadow: 0 1px 0 rgba(48, 34, 66, 0.16);
}

.speed-btn {
  width: 45px;
  font-size: 13px;
  letter-spacing: 0.4px;
  background: #e9fbf5;
}

.icon-btn.is-muted {
  opacity: 0.55;
}

/* ---------- layout / stage ---------- */

.layout {
  flex: 1;
  min-height: 0;
  display: flex;
  gap: 14px;
}

.stage-shell {
  position: relative;
  flex: 1;
  min-width: 0;
  overflow: hidden;
  border: 3px solid var(--line);
  border-radius: 28px;
  background: #94e0e7;
  box-shadow: 0 7px 0 rgba(48, 34, 66, 0.18), 0 20px 40px rgba(40, 72, 86, 0.13);
}

#game {
  display: block;
  width: 100%;
  height: 100%;
  touch-action: none;
  cursor: crosshair;
}

.stage-topline {
  position: absolute;
  top: 13px;
  left: 14px;
  right: 14px;
  display: flex;
  align-items: flex-start;
  gap: 8px;
  pointer-events: none;
  z-index: 2;
}

.stage-wave-chip {
  margin-left: auto;
  display: inline-flex;
  align-items: center;
  gap: 6px;
  min-height: 30px;
  padding: 6px 11px;
  border: 2px solid rgba(62, 49, 80, 0.72);
  border-radius: 11px;
  background: rgba(255, 251, 240, 0.9);
  box-shadow: 0 3px 0 rgba(48, 34, 66, 0.12);
  color: var(--ink);
  font-size: 10.5px;
  line-height: 1.2;
  letter-spacing: 0.2px;
  backdrop-filter: blur(6px);
}

.stage-wave-chip i {
  width: 6px;
  height: 6px;
  flex: none;
  border-radius: 99px;
  background: #5dcda6;
  box-shadow: 0 0 0 3px rgba(93, 205, 166, 0.16);
}

.stage-wave-chip.boss {
  background: rgba(62, 42, 79, 0.9);
  border-color: rgba(41, 27, 58, 0.9);
  color: #fff4d8;
}

.stage-wave-chip.boss i {
  background: #ffd45f;
  box-shadow: 0 0 0 3px rgba(255, 212, 95, 0.18);
  animation: live-pulse 0.7s ease-in-out infinite alternate;
}

.stage-wave-chip b {
  font-size: 10.5px;
  line-height: 1;
}

.stage-skip {
  pointer-events: auto;
  min-height: 30px;
  display: inline-flex;
  align-items: center;
  gap: 2px;
  padding: 5px 10px;
  border: 2px solid rgba(62, 49, 80, 0.85);
  border-radius: 11px;
  background: linear-gradient(180deg, #ffe889, #ffc34f);
  box-shadow: 0 3px 0 rgba(48, 34, 66, 0.16);
  color: #513818;
  font-size: 10px;
  font-weight: 900;
  line-height: 1;
  letter-spacing: 0.2px;
  white-space: nowrap;
  cursor: pointer;
  transition: transform 0.12s ease, filter 0.12s ease, box-shadow 0.12s ease;
}

.stage-skip span {
  font-size: 15px;
  line-height: 0.7;
}

.stage-skip:hover {
  filter: brightness(1.04);
  transform: translateY(-1px);
  box-shadow: 0 4px 0 rgba(48, 34, 66, 0.15);
}

.stage-skip:active {
  transform: translateY(2px);
  box-shadow: 0 1px 0 rgba(48, 34, 66, 0.16);
}

.stage-skip[hidden] {
  display: none;
}

.stage-tag {
  display: inline-flex;
  align-items: center;
  gap: 5px;
  min-height: 30px;
  padding: 6px 11px;
  border: 2px solid rgba(62, 49, 80, 0.72);
  border-radius: 11px;
  background: rgba(255, 251, 240, 0.9);
  box-shadow: 0 3px 0 rgba(48, 34, 66, 0.12);
  color: var(--ink);
  font-size: 10.5px;
  line-height: 1.2;
  letter-spacing: 0.2px;
  backdrop-filter: blur(6px);
}

.stage-hint {
  position: absolute;
  left: 50%;
  bottom: 14px;
  z-index: 3;
  display: flex;
  align-items: center;
  gap: 8px;
  max-width: calc(100% - 36px);
  transform: translateX(-50%);
  padding: 7px 13px;
  border: 2px solid rgba(62, 49, 80, 0.7);
  border-radius: 99px;
  background: rgba(255, 251, 240, 0.91);
  box-shadow: 0 3px 0 rgba(48, 34, 66, 0.12);
  color: var(--ink-soft);
  font-size: 10.5px;
  line-height: 1.2;
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
  pointer-events: none;
  backdrop-filter: blur(8px);
  transition: background 0.2s ease;
}

.hint-dot {
  width: 7px;
  height: 7px;
  flex: none;
  border-radius: 99px;
  background: #63d2a8;
  box-shadow: 0 0 0 3px rgba(99, 210, 168, 0.18);
}

.stage-hint.warning {
  background: #fff2d8;
  color: #9b5d24;
}

.stage-hint.warning .hint-dot {
  background: #ffb441;
  box-shadow: 0 0 0 3px rgba(255, 180, 65, 0.18);
}

.wave-banner {
  position: absolute;
  left: 50%;
  top: 20%;
  z-index: 4;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 3px;
  width: min(440px, calc(100% - 40px));
  padding: 12px 24px 14px;
  border: 3px solid var(--line);
  border-radius: 18px;
  background: linear-gradient(145deg, rgba(255, 252, 238, 0.97), rgba(255, 236, 186, 0.97));
  box-shadow: 0 7px 0 rgba(48, 34, 66, 0.2), 0 16px 28px rgba(48, 34, 66, 0.16);
  opacity: 0;
  pointer-events: none;
  transform: translate(-50%, -18px) scale(0.9) rotate(-1deg);
}

.wave-banner.show {
  animation: banner-pop 2.35s cubic-bezier(0.2, 1.25, 0.3, 1) both;
}

.wave-banner.is-boss {
  background: linear-gradient(145deg, #3c2d5a, #6b3f86);
  color: #fff5f7;
  border-color: #291d3d;
}

.wave-banner.is-boss .banner-kicker {
  color: #ffd46b;
}

.wave-banner.is-boss #bannerSub {
  color: #f0dafd;
}

.banner-kicker {
  color: var(--pink-deep);
  font-size: 9px;
  letter-spacing: 3px;
  line-height: 1;
}

#bannerTitle {
  font-size: clamp(17px, 2vw, 25px);
  letter-spacing: 1px;
  line-height: 1.15;
}

#bannerSub {
  color: var(--ink-soft);
  font-size: 10.5px;
  font-weight: 700;
  letter-spacing: 0.4px;
}

@keyframes banner-pop {
  0% { opacity: 0; transform: translate(-50%, 12px) scale(0.86) rotate(-1deg); }
  12% { opacity: 1; transform: translate(-50%, 0) scale(1.02) rotate(-1deg); }
  20% { transform: translate(-50%, 0) scale(1) rotate(-1deg); }
  78% { opacity: 1; transform: translate(-50%, 0) scale(1) rotate(-1deg); }
  100% { opacity: 0; transform: translate(-50%, -14px) scale(0.97) rotate(-1deg); }
}

.toast {
  position: absolute;
  left: 50%;
  bottom: 63px;
  z-index: 7;
  max-width: calc(100% - 30px);
  padding: 8px 15px;
  border: 2.5px solid var(--line);
  border-radius: 12px;
  background: rgba(255, 250, 236, 0.97);
  box-shadow: 0 4px 0 rgba(48, 34, 66, 0.16);
  color: var(--ink);
  font-size: 11px;
  line-height: 1.25;
  text-align: center;
  opacity: 0;
  pointer-events: none;
  transform: translate(-50%, 12px);
  transition: opacity 0.18s ease, transform 0.18s ease;
}

.toast.show {
  opacity: 1;
  transform: translate(-50%, 0);
}

.toast.good {
  background: #ebfff5;
  border-color: #317e67;
}

.toast.bad {
  background: #fff0ee;
  border-color: #a84f55;
}

.pause-veil {
  position: absolute;
  inset: 0;
  z-index: 8;
  display: grid;
  place-items: center;
  background: rgba(43, 33, 61, 0.4);
  backdrop-filter: blur(5px);
}

.pause-veil[hidden] {
  display: none;
}

.pause-card {
  display: flex;
  flex-direction: column;
  align-items: center;
  min-width: 240px;
  padding: 24px 30px 22px;
  border: 3px solid var(--line);
  border-radius: 24px;
  background: var(--paper);
  box-shadow: 0 8px 0 rgba(33, 22, 48, 0.26);
  text-align: center;
  animation: modal-pop 0.28s cubic-bezier(0.2, 1.35, 0.4, 1) both;
}

.pause-glyph {
  font-size: 38px;
  filter: drop-shadow(0 4px 0 rgba(48, 34, 66, 0.12));
}

.pause-card strong {
  margin-top: 2px;
  font-size: 21px;
}

.pause-card p {
  margin: 5px 0 16px;
  color: var(--ink-soft);
  font-size: 11px;
}

.mini-primary {
  padding: 9px 24px;
  border: 2.5px solid var(--line);
  border-radius: 12px;
  background: linear-gradient(180deg, #ffe587, #ffbf4e);
  box-shadow: 0 4px 0 rgba(48, 34, 66, 0.18);
  font-size: 12px;
  cursor: pointer;
}

.mini-primary:active {
  transform: translateY(2px);
  box-shadow: 0 2px 0 rgba(48, 34, 66, 0.18);
}

.stage-vignette {
  position: absolute;
  inset: 0;
  z-index: 1;
  pointer-events: none;
  opacity: 0;
  background: radial-gradient(circle at center, transparent 35%, rgba(255, 72, 88, 0.35) 100%);
  transition: opacity 0.12s linear;
}

/* ---------- sidebar ---------- */

.sider {
  width: 306px;
  flex: none;
  min-height: 0;
  display: flex;
  flex-direction: column;
  padding: 15px;
  border: 3px solid var(--line);
  border-radius: 26px;
  background: var(--paper);
  box-shadow: 0 7px 0 rgba(48, 34, 66, 0.17), 0 18px 34px rgba(48, 34, 66, 0.09);
}

.shop-head {
  flex: none;
  display: flex;
  align-items: flex-start;
  justify-content: space-between;
  gap: 10px;
}

.eyebrow {
  margin: 0 0 3px;
  color: var(--pink-deep);
  font-size: 8.5px;
  font-weight: 800;
  letter-spacing: 2.4px;
  line-height: 1.2;
}

.shop-head h2 {
  margin: 0;
  font-size: 20px;
  line-height: 1.15;
  letter-spacing: 0.5px;
}

.coin-chip {
  display: flex;
  align-items: center;
  gap: 5px;
  flex: none;
  padding: 7px 10px;
  border: 2.5px solid var(--line);
  border-radius: 12px;
  background: #fff5c9;
  box-shadow: inset 0 2px 0 rgba(255, 255, 255, 0.55), 0 3px 0 rgba(48, 34, 66, 0.12);
  font-size: 15px;
  line-height: 1;
}

.coin-chip span {
  font-size: 15px;
}

.coin-chip b {
  min-width: 24px;
  text-align: right;
  font-size: 15px;
}

.shop-body {
  position: relative;
  flex: 1;
  min-height: 0;
  margin-top: 12px;
  display: flex;
  flex-direction: column;
  gap: 9px;
}

.tower-list {
  flex: 1;
  min-height: 0;
  display: flex;
  flex-direction: column;
  gap: 8px;
  overflow-y: auto;
  padding: 1px 3px 2px 1px;
  scrollbar-width: thin;
  scrollbar-color: #d8c8b4 transparent;
}

.tower-list::-webkit-scrollbar {
  width: 5px;
}

.tower-list::-webkit-scrollbar-thumb {
  border-radius: 99px;
  background: #d8c8b4;
}

.tower-card {
  --accent: #ff7b9f;
  position: relative;
  width: 100%;
  min-height: 78px;
  display: grid;
  grid-template-columns: 46px minmax(0, 1fr) auto;
  align-items: center;
  gap: 9px;
  padding: 9px 10px 9px 8px;
  border: 2.5px solid rgba(62, 49, 80, 0.19);
  border-radius: 16px;
  background: #fffdf8;
  box-shadow: 0 2px 0 rgba(48, 34, 66, 0.06);
  text-align: left;
  cursor: pointer;
  transition: transform 0.13s ease, border-color 0.13s ease, background 0.13s ease, box-shadow 0.13s ease;
}

.tower-card:hover {
  transform: translateY(-1px);
  border-color: var(--accent);
  background: #fffaf0;
  box-shadow: 0 4px 0 rgba(48, 34, 66, 0.1);
}

.tower-card.active {
  border-color: var(--line);
  background: #fff4cf;
  box-shadow: 0 4px 0 rgba(48, 34, 66, 0.15), inset 0 0 0 2px var(--accent);
  transform: translateY(-1px);
}

.tower-card.poor {
  opacity: 0.56;
  filter: saturate(0.7);
}

.tower-card.poor:hover {
  transform: none;
}

.tower-card .card-key {
  position: absolute;
  top: 4px;
  right: 7px;
  color: rgba(62, 49, 80, 0.28);
  font-size: 8px;
  line-height: 1;
  letter-spacing: 0.3px;
}

.tower-thumb {
  width: 46px;
  height: 46px;
  display: grid;
  place-items: center;
  border: 2.5px solid var(--line);
  border-radius: 13px;
  background:
    radial-gradient(circle at 30% 22%, rgba(255, 255, 255, 0.8), transparent 34%),
    var(--accent);
  box-shadow: inset 0 -4px 0 rgba(48, 34, 66, 0.11);
  font-size: 24px;
  line-height: 1;
}

.card-main {
  min-width: 0;
  display: flex;
  flex-direction: column;
  gap: 3px;
}

.card-title-row {
  display: flex;
  align-items: center;
  gap: 5px;
  min-width: 0;
}

.card-name {
  overflow: hidden;
  font-size: 13.2px;
  font-weight: 900;
  line-height: 1.2;
  letter-spacing: 0.2px;
  white-space: nowrap;
  text-overflow: ellipsis;
}

.role-tag {
  flex: none;
  padding: 2px 5px;
  border-radius: 5px;
  background: color-mix(in srgb, var(--accent) 24%, white);
  color: color-mix(in srgb, var(--accent) 58%, #372b4b);
  font-size: 7.8px;
  font-weight: 900;
  line-height: 1.2;
  letter-spacing: 0.2px;
}

.card-sub {
  overflow: hidden;
  color: var(--ink-soft);
  font-size: 9.3px;
  font-weight: 700;
  line-height: 1.28;
  display: -webkit-box;
  -webkit-line-clamp: 2;
  -webkit-box-orient: vertical;
}

.card-side {
  align-self: stretch;
  display: flex;
  flex-direction: column;
  align-items: flex-end;
  justify-content: space-between;
  padding: 2px 0;
}

.card-cost {
  display: flex;
  align-items: center;
  gap: 2px;
  color: #a66d16;
  font-size: 12px;
  line-height: 1;
  white-space: nowrap;
}

.card-cost .coin-emoji {
  font-size: 10px;
}

.card-place {
  color: rgba(62, 49, 80, 0.54);
  font-size: 7.5px;
  font-weight: 800;
  line-height: 1;
  white-space: nowrap;
}

.shop-legend {
  flex: none;
  padding: 9px 11px 10px;
  border: 2px dashed rgba(62, 49, 80, 0.16);
  border-radius: 13px;
  background: rgba(246, 240, 255, 0.65);
}

.legend-title {
  display: flex;
  align-items: center;
  gap: 5px;
  margin-bottom: 6px;
  color: #6c5b81;
  font-size: 9.5px;
  font-weight: 900;
  letter-spacing: 0.4px;
}

.legend-title span {
  font-size: 11px;
}

.legend-row {
  display: flex;
  align-items: center;
  gap: 7px;
  color: var(--ink-soft);
  font-size: 8px;
  font-weight: 700;
  line-height: 1.5;
}

.legend-mark {
  width: 15px;
  height: 15px;
  flex: none;
  display: grid;
  place-items: center;
  color: #6b8d50;
  font-size: 9px;
  font-weight: 900;
  line-height: 1;
}

.legend-round {
  border: 1.5px solid #80a662;
  border-radius: 99px;
  background: #d9f2b7;
}

.legend-diamond {
  position: relative;
  width: 15px;
  height: 15px;
  border: 0;
  background: transparent;
  transform: none;
  isolation: isolate;
}

.legend-diamond::before {
  content: "";
  position: absolute;
  inset: 2px;
  z-index: -1;
  border: 1.5px solid #997556;
  border-radius: 2px;
  background: #ffedb9;
  transform: rotate(45deg);
}

.legend-fly {
  filter: grayscale(0.1);
}

/* inspector */

.inspector {
  position: absolute;
  inset: 0;
  z-index: 5;
  display: flex;
  flex-direction: column;
  padding: 1px;
  background: var(--paper);
  border-radius: 12px;
  overflow-y: auto;
}

.inspector[hidden] {
  display: none;
}

.inspector-top {
  display: flex;
  align-items: center;
  gap: 8px;
  margin-bottom: 11px;
}

.back-btn {
  width: 29px;
  height: 29px;
  flex: none;
  display: grid;
  place-items: center;
  border: 2px solid rgba(62, 49, 80, 0.26);
  border-radius: 9px;
  background: #fffdf8;
  font-size: 15px;
  cursor: pointer;
}

.back-btn:hover {
  background: #fff4d2;
}

.inspector-title {
  min-width: 0;
  flex: 1;
}

.inspector-title h3 {
  margin: 0;
  display: flex;
  align-items: center;
  gap: 5px;
  font-size: 15px;
  line-height: 1.15;
}

.inspector-title p {
  margin: 3px 0 0;
  color: var(--ink-soft);
  font-size: 9px;
  font-weight: 700;
}

.level-pill {
  display: inline-flex;
  align-items: center;
  padding: 2px 6px;
  border-radius: 5px;
  background: var(--sun);
  color: #674318;
  font-size: 8px;
  line-height: 1.3;
  letter-spacing: 0.3px;
}

.inspector-icon {
  width: 46px;
  height: 46px;
  flex: none;
  display: grid;
  place-items: center;
  border: 2.5px solid var(--line);
  border-radius: 13px;
  background: var(--accent, #ffd66b);
  box-shadow: inset 0 -4px 0 rgba(48, 34, 66, 0.10);
  font-size: 24px;
}

.tower-preview {
  position: relative;
  height: 88px;
  margin-bottom: 12px;
  overflow: hidden;
  border: 2px solid rgba(62, 49, 80, 0.16);
  border-radius: 14px;
  background:
    radial-gradient(circle at 50% 80%, rgba(255, 255, 255, 0.45), transparent 40%),
    linear-gradient(150deg, #dff9ee, #fef4cc);
}

.tower-preview::before,
.tower-preview::after {
  content: "";
  position: absolute;
  border-radius: 99px;
  background: rgba(255, 255, 255, 0.4);
}

.tower-preview::before {
  width: 100px;
  height: 100px;
  top: -38px;
  right: -24px;
}

.tower-preview::after {
  width: 52px;
  height: 52px;
  bottom: -24px;
  left: 12px;
}

.preview-tower {
  position: absolute;
  left: 50%;
  bottom: 2px;
  width: 96px;
  height: 96px;
  transform: translateX(-50%);
}

.preview-glow {
  position: absolute;
  left: 50%;
  bottom: 7px;
  width: 78px;
  height: 20px;
  transform: translateX(-50%);
  border-radius: 999px;
  background: rgba(74, 57, 96, 0.18);
  filter: blur(2px);
}

.preview-emoji {
  position: absolute;
  left: 50%;
  bottom: 14px;
  transform: translateX(-50%) rotate(-4deg);
  font-size: 48px;
  filter: drop-shadow(0 5px 0 rgba(48, 34, 66, 0.14));
}

.preview-stars {
  position: absolute;
  right: 12px;
  top: 10px;
  display: flex;
  gap: 2px;
  color: #ffb52e;
  font-size: 13px;
  letter-spacing: 0;
  text-shadow: 0 1px 0 rgba(255, 255, 255, 0.6);
}

.stat-grid {
  display: grid;
  grid-template-columns: repeat(2, minmax(0, 1fr));
  gap: 7px;
  margin-bottom: 11px;
}

.stat-cell {
  padding: 8px 9px;
  border: 2px solid rgba(62, 49, 80, 0.12);
  border-radius: 10px;
  background: rgba(255, 255, 255, 0.55);
}

.stat-cell span {
  display: block;
  margin-bottom: 3px;
  color: var(--ink-soft);
  font-size: 8px;
  font-weight: 800;
  letter-spacing: 0.5px;
}

.stat-cell b {
  font-size: 13px;
  line-height: 1.1;
}

.stat-cell b em {
  color: var(--ink-soft);
  font-size: 9px;
  font-style: normal;
}

.ability-note {
  display: flex;
  gap: 7px;
  align-items: flex-start;
  margin-bottom: 11px;
  padding: 8px 9px;
  border-radius: 10px;
  background: #f0ecff;
  color: #5d4b83;
  font-size: 9px;
  font-weight: 700;
  line-height: 1.35;
}

.ability-note .note-icon {
  flex: none;
  font-size: 12px;
}

.inspector-actions {
  display: flex;
  gap: 7px;
  margin-top: auto;
  padding-top: 4px;
}

.upgrade-btn {
  flex: 1;
  min-height: 39px;
  padding: 8px 10px;
  border: 2.5px solid var(--line);
  border-radius: 11px;
  background: linear-gradient(180deg, #ffe98b, #ffc34f);
  box-shadow: 0 3px 0 rgba(48, 34, 66, 0.18);
  color: #49331a;
  font-size: 10.5px;
  font-weight: 900;
  cursor: pointer;
}

.upgrade-btn:hover {
  background: linear-gradient(180deg, #fff19e, #ffce62);
}

.upgrade-btn:active {
  transform: translateY(2px);
  box-shadow: 0 1px 0 rgba(48, 34, 66, 0.18);
}

.upgrade-btn:disabled {
  opacity: 0.46;
  cursor: not-allowed;
  transform: none;
}

.sell-btn {
  flex: none;
  padding: 8px 10px;
  border: 2.5px solid rgba(62, 49, 80, 0.17);
  border-radius: 11px;
  background: #fffdf7;
  color: var(--ink-soft);
  font-size: 9px;
  font-weight: 800;
  cursor: pointer;
}

.sell-btn:hover {
  border-color: #db8e8e;
  background: #fff0ee;
  color: #a84f55;
}

.max-level-note {
  display: flex;
  align-items: center;
  justify-content: center;
  flex: 1;
  min-height: 39px;
  border: 2px dashed #e3bd65;
  border-radius: 11px;
  background: #fff8dc;
  color: #9a6c20;
  font-size: 10px;
}

/* sidebar footer */

.side-footer {
  flex: none;
  margin-top: 10px;
}

.wave-panel {
  padding: 9px 11px 10px;
  border: 2px solid rgba(62, 49, 80, 0.15);
  border-radius: 14px;
  background: linear-gradient(145deg, #ecfbff, #f2efff);
}

.wave-head {
  display: flex;
  align-items: center;
  gap: 6px;
  min-width: 0;
  font-size: 10px;
}

.wave-head b {
  min-width: 0;
  flex: 1;
  overflow: hidden;
  font-size: 10px;
  line-height: 1.2;
  white-space: nowrap;
  text-overflow: ellipsis;
}

.wave-head > span:last-child {
  flex: none;
  color: var(--pink-deep);
  font-size: 11px;
  font-weight: 900;
}

.live-dot {
  width: 6px;
  height: 6px;
  flex: none;
  border-radius: 99px;
  background: #5dcda6;
  box-shadow: 0 0 0 3px rgba(93, 205, 166, 0.16);
}

.live-dot.is-boss {
  background: #e85a7e;
  box-shadow: 0 0 0 3px rgba(232, 90, 126, 0.16);
  animation: live-pulse 0.75s ease-in-out infinite alternate;
}

@keyframes live-pulse {
  from { transform: scale(0.8); }
  to { transform: scale(1.25); }
}

.wave-meter {
  height: 5px;
  margin-top: 7px;
  overflow: hidden;
  border-radius: 99px;
  background: rgba(62, 49, 80, 0.12);
}

.wave-meter i {
  display: block;
  width: 0%;
  height: 100%;
  border-radius: inherit;
  background: linear-gradient(90deg, #63d7b0, #75c7ff);
  transition: width 0.18s linear;
}

#waveHint {
  margin: 6px 0 0;
  overflow: hidden;
  color: var(--ink-soft);
  font-size: 8.5px;
  font-weight: 700;
  line-height: 1.3;
  white-space: nowrap;
  text-overflow: ellipsis;
}

.record-mini {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 6px;
  padding: 8px 2px 0;
  color: #8b7f8f;
  font-size: 8px;
  font-weight: 800;
}

.record-mini b {
  color: #8f6323;
  font-size: 8.5px;
}

.tip-inline {
  color: #a29aad;
  white-space: nowrap;
}

/* ---------- overlays ---------- */

.overlay {
  position: fixed;
  inset: 0;
  z-index: 50;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 20px;
  overflow-y: auto;
  background:
    radial-gradient(circle at 50% 30%, rgba(146, 117, 191, 0.2), transparent 52%),
    rgba(43, 31, 63, 0.56);
  backdrop-filter: blur(9px);
}

.overlay[hidden] {
  display: none;
}

.modal {
  position: relative;
  width: min(560px, 100%);
  max-height: calc(100dvh - 40px);
  overflow-y: auto;
  padding: 24px 27px 22px;
  border: 4px solid var(--line);
  border-radius: 30px;
  background:
    radial-gradient(circle at 95% 2%, rgba(255, 213, 123, 0.23), transparent 24%),
    var(--paper);
  box-shadow: 0 11px 0 rgba(31, 20, 46, 0.32), 0 30px 70px rgba(20, 12, 30, 0.24);
  animation: modal-pop 0.36s cubic-bezier(0.2, 1.32, 0.35, 1) both;
  scrollbar-width: thin;
  scrollbar-color: #d8c8b4 transparent;
}

@keyframes modal-pop {
  from { opacity: 0; transform: translateY(24px) scale(0.94); }
  to { opacity: 1; transform: translateY(0) scale(1); }
}

.start-hero {
  position: relative;
  height: 146px;
  margin: -9px -11px 18px;
  overflow: hidden;
  border: 3px solid var(--line);
  border-radius: 22px;
  background: linear-gradient(160deg, #68d5f3 0%, #a7ebd5 46%, #e8f7b5 100%);
}

.hero-sky {
  position: absolute;
  inset: 0;
  background:
    radial-gradient(circle at 12% 20%, rgba(255, 255, 255, 0.75) 0 3px, transparent 4px),
    radial-gradient(circle at 82% 14%, rgba(255, 255, 255, 0.6) 0 2px, transparent 3px),
    radial-gradient(circle at 44% 9%, rgba(255, 255, 255, 0.42) 0 1.5px, transparent 2px);
  background-size: 90px 90px, 120px 120px, 80px 80px;
}

.hero-island {
  position: absolute;
  left: 50%;
  bottom: -65px;
  width: 430px;
  max-width: 92%;
  height: 185px;
  transform: translateX(-50%);
  border: 3px solid #408067;
  border-radius: 50%;
  background:
    radial-gradient(circle at 50% 46%, #fef4c1 0 36px, #9dd875 37px 62%, #8bce62 63%);
  box-shadow: 0 10px 0 rgba(47, 94, 77, 0.12);
}

.hero-island::before {
  content: "";
  position: absolute;
  left: 50%;
  top: 27%;
  width: 112px;
  height: 37px;
  transform: translateX(-50%);
  border-radius: 50%;
  background: rgba(255, 248, 213, 0.7);
}

.hero-core {
  position: absolute;
  left: 50%;
  top: 23%;
  z-index: 3;
  display: grid;
  place-items: center;
  width: 63px;
  height: 63px;
  transform: translateX(-50%) rotate(-3deg);
  border: 3px solid var(--line);
  border-radius: 20px;
  background: linear-gradient(145deg, #fff2b0, #ffc967);
  box-shadow: 0 5px 0 rgba(48, 34, 66, 0.16), inset 0 3px 0 rgba(255, 255, 255, 0.6);
  font-size: 34px;
  animation: core-bob 2.4s ease-in-out infinite;
}

@keyframes core-bob {
  0%, 100% { transform: translateX(-50%) translateY(0) rotate(-3deg); }
  50% { transform: translateX(-50%) translateY(-4px) rotate(2deg); }
}

.hero-tower,
.hero-enemy {
  position: absolute;
  z-index: 4;
  font-size: 26px;
  filter: drop-shadow(0 3px 0 rgba(48, 34, 66, 0.16));
  animation: float-pop 2.8s ease-in-out infinite;
}

.hero-tower {
  font-size: 28px;
}

.hero-t1 { left: 18%; top: 46%; animation-delay: -0.2s; }
.hero-t2 { right: 18%; top: 52%; animation-delay: -1.1s; }
.hero-t3 { left: 34%; top: 11%; font-size: 23px; animation-delay: -1.7s; }
.hero-e1 { left: 5%; top: 18%; font-size: 24px; animation-delay: -0.7s; }
.hero-e2 { right: 5%; top: 14%; font-size: 23px; animation-delay: -1.9s; }
.hero-e3 { right: 31%; top: 35%; font-size: 21px; animation-delay: -1.3s; }

@keyframes float-pop {
  0%, 100% { transform: translateY(0) rotate(-2deg); }
  50% { transform: translateY(-6px) rotate(3deg); }
}

.hero-spark {
  position: absolute;
  color: #fff8bd;
  font-size: 19px;
  text-shadow: 0 2px 0 rgba(48, 34, 66, 0.1);
  animation: sparkle 1.9s ease-in-out infinite;
}

.hero-spark.s1 { left: 45%; top: 15%; animation-delay: -0.5s; }
.hero-spark.s2 { left: 24%; top: 25%; font-size: 13px; animation-delay: -1.2s; }
.hero-spark.s3 { right: 26%; top: 21%; font-size: 14px; animation-delay: -0.1s; }

@keyframes sparkle {
  0%, 100% { opacity: 0.35; transform: scale(0.8) rotate(0); }
  50% { opacity: 1; transform: scale(1.15) rotate(15deg); }
}

.start-modal > .eyebrow,
.gameover-modal > .eyebrow {
  margin-bottom: 5px;
  text-align: center;
  font-size: 9px;
  letter-spacing: 3px;
}

.start-title,
.gameover-title {
  margin: 0;
  text-align: center;
  font-size: clamp(25px, 4vw, 31px);
  line-height: 1.15;
  letter-spacing: 0.8px;
  text-shadow: 0 2px 0 rgba(255, 255, 255, 0.7);
}

.modal-desc {
  max-width: 430px;
  margin: 10px auto 17px;
  color: var(--ink-soft);
  font-size: 11px;
  font-weight: 700;
  line-height: 1.65;
  text-align: center;
}

.how-grid {
  display: grid;
  grid-template-columns: repeat(3, minmax(0, 1fr));
  gap: 8px;
  margin-bottom: 13px;
}

.how-item {
  padding: 11px 9px 10px;
  border: 2px solid rgba(62, 49, 80, 0.12);
  border-radius: 14px;
  background: rgba(255, 255, 255, 0.52);
}

.how-icon {
  display: block;
  margin-bottom: 5px;
  font-size: 21px;
  line-height: 1;
}

.how-item b {
  display: block;
  margin-bottom: 4px;
  font-size: 11px;
  line-height: 1.2;
}

.how-item p {
  margin: 0;
  color: var(--ink-soft);
  font-size: 8.5px;
  font-weight: 700;
  line-height: 1.45;
}

.rule-line {
  display: flex;
  align-items: flex-start;
  gap: 7px;
  margin: 0 0 16px;
  padding: 9px 11px;
  border: 1.5px dashed #e0b866;
  border-radius: 10px;
  background: #fff8df;
  color: #8c6425;
  font-size: 9px;
  font-weight: 700;
  line-height: 1.5;
}

.rule-line > span {
  display: grid;
  place-items: center;
  flex: none;
  width: 14px;
  height: 14px;
  margin-top: 0;
  border-radius: 99px;
  background: #f4c24f;
  color: #5d4217;
  font-size: 9px;
  font-weight: 900;
}

.primary-btn {
  width: 100%;
  min-height: 48px;
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 9px;
  padding: 11px 22px;
  border: 3px solid var(--line);
  border-radius: 15px;
  background: linear-gradient(180deg, #ffe78b 0%, #ffc34f 100%);
  box-shadow: 0 5px 0 rgba(48, 34, 66, 0.22), inset 0 2px 0 rgba(255, 255, 255, 0.55);
  color: #453018;
  font-size: 15px;
  font-weight: 900;
  letter-spacing: 1px;
  cursor: pointer;
  transition: transform 0.12s ease, box-shadow 0.12s ease, filter 0.12s ease;
}

.primary-btn:hover {
  filter: brightness(1.035);
  transform: translateY(-1px);
  box-shadow: 0 6px 0 rgba(48, 34, 66, 0.22), inset 0 2px 0 rgba(255, 255, 255, 0.55);
}

.primary-btn:active {
  transform: translateY(3px);
  box-shadow: 0 2px 0 rgba(48, 34, 66, 0.22), inset 0 2px 0 rgba(255, 255, 255, 0.55);
}

.primary-btn span {
  font-size: 20px;
  line-height: 0.8;
}

.start-btn {
  animation: button-breathe 2.5s ease-in-out infinite;
}

@keyframes button-breathe {
  0%, 100% { transform: translateY(0); }
  50% { transform: translateY(-2px); }
}

.start-btn:hover {
  animation: none;
}

.record-strip {
  display: flex;
  align-items: center;
  justify-content: center;
  flex-wrap: wrap;
  gap: 7px;
  margin-top: 14px;
  color: #8f837d;
  font-size: 9px;
  font-weight: 800;
}

.record-strip-label {
  color: #a27b35;
}

.record-strip b {
  color: #8b5b21;
  font-size: 10px;
}

.record-divider {
  width: 1px;
  height: 10px;
  background: rgba(62, 49, 80, 0.16);
}

.link-btn {
  margin-left: 3px;
  padding: 0;
  border: 0;
  background: transparent;
  color: #b5a9a1;
  font-size: 8px;
  font-weight: 800;
  text-decoration: underline;
  text-underline-offset: 2px;
  cursor: pointer;
}

.link-btn:hover {
  color: #a84f55;
}

/* game over */

.gameover-modal {
  width: min(530px, 100%);
}

.gameover-art {
  position: relative;
  height: 84px;
  margin: -4px auto 3px;
  display: grid;
  place-items: center;
}

.gameover-art::before {
  content: "";
  position: absolute;
  width: 100px;
  height: 20px;
  bottom: 4px;
  border-radius: 99px;
  background: rgba(62, 49, 80, 0.12);
  filter: blur(2px);
}

.sad-crystal {
  position: relative;
  z-index: 2;
  font-size: 57px;
  filter: grayscale(0.15) drop-shadow(0 5px 0 rgba(48, 34, 66, 0.12));
  transform: rotate(-8deg);
  animation: sad-wobble 2.5s ease-in-out infinite;
}

@keyframes sad-wobble {
  0%, 100% { transform: rotate(-8deg) translateY(0); }
  50% { transform: rotate(4deg) translateY(-3px); }
}

.sad-spark {
  position: absolute;
  color: #cbb9ea;
  font-size: 19px;
  animation: sparkle 2.3s ease-in-out infinite;
}

.sad-spark.sp1 { left: 28%; top: 28%; }
.sad-spark.sp2 { right: 27%; top: 18%; font-size: 13px; animation-delay: -0.8s; }
.sad-spark.sp3 { right: 35%; bottom: 12%; font-size: 10px; animation-delay: -1.5s; }

.result-grid {
  display: grid;
  grid-template-columns: repeat(2, minmax(0, 1fr));
  gap: 10px;
  margin: 16px 0 11px;
}

.result-item {
  position: relative;
  display: grid;
  grid-template-columns: 34px minmax(0, 1fr);
  grid-template-rows: auto auto;
  column-gap: 8px;
  align-items: center;
  padding: 13px 13px;
  border: 2.5px solid var(--line);
  border-radius: 16px;
  background: #fffcf2;
  box-shadow: 0 4px 0 rgba(48, 34, 66, 0.09);
}

.result-icon {
  grid-row: 1 / 3;
  display: grid;
  place-items: center;
  width: 34px;
  height: 34px;
  border-radius: 10px;
  background: #fff2c6;
  font-size: 18px;
}

.result-label {
  color: var(--ink-soft);
  font-size: 8.5px;
  letter-spacing: 0.7px;
}

.result-item strong {
  margin-top: 2px;
  font-size: 24px;
  line-height: 1;
  letter-spacing: 0.7px;
}

.record-grid {
  display: grid;
  grid-template-columns: repeat(2, minmax(0, 1fr));
  gap: 8px;
}

.record-card {
  position: relative;
  display: flex;
  flex-direction: column;
  gap: 3px;
  padding: 9px 11px;
  overflow: hidden;
  border: 2px dashed #e3bd65;
  border-radius: 13px;
  background: #fff8dc;
}

.record-card::after {
  content: "";
  position: absolute;
  right: -13px;
  bottom: -19px;
  width: 58px;
  height: 58px;
  border-radius: 99px;
  background: rgba(255, 205, 94, 0.14);
}

.record-crown {
  position: absolute;
  right: 9px;
  top: 7px;
  font-size: 14px;
  opacity: 0.7;
}

.record-label {
  color: #9c7733;
  font-size: 8px;
  font-weight: 800;
  letter-spacing: 0.5px;
}

.record-card strong {
  color: #79501b;
  font-size: 19px;
  line-height: 1.1;
}

.record-card.is-new {
  background: linear-gradient(145deg, #fff3bd, #ffe08b);
  border-color: #e8a934;
  box-shadow: 0 3px 0 rgba(173, 119, 30, 0.12);
}

.new-record {
  position: absolute;
  right: 8px;
  bottom: 8px;
  padding: 2px 5px;
  border-radius: 4px;
  background: #ff7c98;
  color: #fff;
  font-size: 7px;
  font-weight: 900;
  animation: new-pulse 0.9s ease-in-out infinite alternate;
}

@keyframes new-pulse {
  from { transform: scale(0.96) rotate(-2deg); }
  to { transform: scale(1.04) rotate(1deg); }
}

.gameover-actions {
  display: flex;
  gap: 8px;
  margin-top: 16px;
}

.gameover-actions .primary-btn {
  flex: 1;
}

.ghost-btn {
  flex: none;
  padding: 0 17px;
  border: 2.5px solid rgba(62, 49, 80, 0.2);
  border-radius: 14px;
  background: #fffdf7;
  color: var(--ink-soft);
  font-size: 10.5px;
  font-weight: 800;
  cursor: pointer;
}

.ghost-btn:hover {
  border-color: rgba(62, 49, 80, 0.4);
  background: #f8f3e8;
}

.gameover-footnote {
  margin: 12px 0 0;
  color: #a89c9b;
  font-size: 8.5px;
  font-weight: 700;
  text-align: center;
}

/* ---------- responsive ---------- */

@media (max-width: 1280px) {
  #app { padding: 12px 14px 14px; }
  .topbar { gap: 10px; }
  .brand { min-width: 188px; }
  .brand-copy p { display: none; }
  .brand-copy h1 { font-size: 19px; }
  .hud { gap: 5px; }
  .hud-stat { min-width: 67px; padding: 5px 7px; gap: 5px; }
  .hud-icon { width: 21px; font-size: 15px; }
  .hud-hp { min-width: 94px; }
  .hud-copy strong { font-size: 15px; }
  .sider { width: 286px; padding: 13px; }
  .tower-card { min-height: 65px; }
  .side-footer { margin-top: 8px; }
}

@media (max-width: 1080px) {
  .hud-kills { display: none; }
  .brand { min-width: 170px; }
  .sider { width: 270px; }
  .card-sub { max-width: 148px; }
}

@media (max-width: 940px) {
  body { overflow: auto; }
  #app {
    height: auto;
    min-height: 100dvh;
    padding: 10px;
    gap: 10px;
  }
  .topbar {
    flex-wrap: wrap;
    gap: 8px;
    padding: 9px 10px;
  }
  .brand { flex: 1; min-width: 155px; }
  .brand-mark { width: 43px; height: 43px; font-size: 25px; border-radius: 14px; }
  .brand-copy h1 { font-size: 18px; }
  .hud {
    order: 3;
    flex-basis: 100%;
    justify-content: stretch;
  }
  .hud-stat { flex: 1; min-width: 0; }
  .hud-hp { flex: 1.3; }
  .top-actions { gap: 5px; }
  .icon-btn { width: 35px; height: 35px; border-radius: 11px; font-size: 15px; }
  .speed-btn { width: 40px; }
  .layout { flex-direction: column; min-height: 0; }
  .stage-shell {
    flex: none;
    height: clamp(520px, 70vh, 700px);
    border-radius: 22px;
  }
  .stage-hint { bottom: 10px; font-size: 9.5px; }
  .sider {
    width: 100%;
    border-radius: 22px;
    padding: 13px;
  }
  .shop-body { flex: none; margin-top: 10px; }
  .tower-list {
    flex: none;
    height: auto;
    display: grid;
    grid-template-columns: repeat(2, minmax(0, 1fr));
    gap: 7px;
    overflow: visible;
  }
  .shop-legend {
    margin-top: 8px;
  }
  .tower-card { min-height: 59px; }
  .card-sub { white-space: normal; }
  .tower-card:nth-child(5) { grid-column: span 2; }
  .inspector {
    position: relative;
    min-height: 360px;
    padding: 6px;
  }
  .side-footer { margin-top: 10px; }
  .record-mini { padding-top: 7px; }
  .wave-banner { top: 15%; }
}

@media (max-width: 600px) {
  .brand-copy h1 { font-size: 16px; }
  .brand-mark { width: 38px; height: 38px; font-size: 22px; }
  .hud-stat { padding: 4px 5px; border-radius: 10px; }
  .hud-icon { width: 18px; font-size: 13px; }
  .hud-copy strong { font-size: 13px; }
  .hud-label { font-size: 7.5px; margin-bottom: 3px; }
  .hud-hp { min-width: 0; }
  .hud-hp .hud-copy strong small { display: none; }
  .hp-track { height: 3px; margin-top: 3px; }
  .speed-btn { width: 35px; font-size: 11px; }
  .stage-shell { height: clamp(500px, 66vh, 660px); }
  .stage-topline { top: 9px; left: 9px; right: 9px; }
  .stage-tag { font-size: 9px; padding: 5px 8px; border-radius: 9px; }
  .stage-wave-chip { min-height: 26px; padding: 5px 8px; font-size: 9px; border-radius: 9px; }
  .stage-wave-chip b { font-size: 9px; }
  .stage-skip { min-height: 26px; padding: 4px 7px; font-size: 8.5px; border-radius: 9px; }
  .stage-skip span { font-size: 13px; }
  .stage-hint { max-width: calc(100% - 18px); padding: 6px 10px; font-size: 8.5px; }
  .toast { bottom: 52px; font-size: 10px; }
  .wave-banner { top: 12%; padding: 10px 15px; }
  .modal { padding: 18px 16px; border-radius: 24px; }
  .start-hero { height: 124px; margin: -3px -2px 14px; }
  .how-grid { grid-template-columns: 1fr; gap: 6px; }
  .how-item { display: grid; grid-template-columns: 27px 1fr; column-gap: 7px; padding: 8px 9px; }
  .how-icon { grid-row: 1 / 3; margin: 0; font-size: 19px; }
  .how-item b { margin-bottom: 2px; }
  .how-item p { font-size: 8.5px; }
  .modal-desc { margin: 8px auto 12px; font-size: 10px; line-height: 1.55; }
  .start-title, .gameover-title { font-size: 23px; }
  .rule-line { margin-bottom: 12px; font-size: 8.5px; }
  .primary-btn { min-height: 44px; font-size: 13px; }
  .record-strip { font-size: 8.5px; }
  .result-grid { gap: 7px; }
  .result-item { grid-template-columns: 28px minmax(0, 1fr); padding: 9px; }
  .result-icon { width: 28px; height: 28px; font-size: 15px; }
  .result-item strong { font-size: 20px; }
  .record-grid { gap: 6px; }
  .gameover-actions { margin-top: 12px; }
  .ghost-btn { padding: 0 10px; font-size: 9px; }
  .gameover-footnote { margin-top: 9px; }
  .tower-card { grid-template-columns: 39px minmax(0, 1fr); min-height: 62px; }
  .tower-thumb { width: 39px; height: 39px; font-size: 20px; }
  .card-cost { position: absolute; right: 9px; bottom: 7px; }
  .card-name { font-size: 11.5px; padding-right: 35px; }
  .card-place { display: none; }
  .role-tag { display: none; }
  .tower-card:nth-child(5) { grid-column: span 2; }
  .record-mini { font-size: 7.5px; }
  .tip-inline { display: none; }
}

@media (prefers-reduced-motion: reduce) {
  *, *::before, *::after {
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
    transition-duration: 0.01ms !important;
  }
}

/* ========================================================================== */
/* Dedicated mobile layout                                                    */
/* ========================================================================== */

@media (max-width: 940px) {
  html,
  body {
    height: 100%;
    overflow: hidden;
    overscroll-behavior: none;
  }

  body {
    background-size: 150px 150px, 190px 190px, 110px 110px, 100% 100%;
  }

  #app {
    height: 100vh;
    height: 100dvh;
    min-height: 0;
    padding-top: max(7px, env(safe-area-inset-top));
    padding-right: max(8px, env(safe-area-inset-right));
    padding-bottom: max(7px, env(safe-area-inset-bottom));
    padding-left: max(8px, env(safe-area-inset-left));
    gap: 7px;
  }

  .ambient-cloud {
    display: none;
  }

  /* ---- compact two-row header ---- */

  .topbar {
    flex: none;
    flex-wrap: wrap;
    gap: 5px 6px;
    padding: 6px 7px;
    min-height: 0;
    border-width: 2.5px;
    border-radius: 18px;
    box-shadow: 0 4px 0 rgba(48, 34, 66, 0.14), 0 10px 22px rgba(48, 34, 66, 0.08);
  }

  .brand {
    flex: 1 1 120px;
    min-width: 0;
    gap: 7px;
  }

  .brand-mark {
    width: 36px;
    height: 36px;
    font-size: 21px;
    border-width: 2.5px;
    border-radius: 12px;
  }

  .brand-copy h1 {
    font-size: 16px;
    letter-spacing: 0.2px;
  }

  .brand-copy p {
    display: none;
  }

  .top-actions {
    margin-left: auto;
    gap: 5px;
  }

  .icon-btn {
    width: 37px;
    height: 37px;
    border-width: 2.2px;
    border-radius: 11px;
    font-size: 15px;
  }

  .speed-btn {
    width: 39px;
    font-size: 11px;
  }

  .hud {
    order: 3;
    flex-basis: 100%;
    gap: 4px;
  }

  .hud-stat {
    flex: 1;
    min-width: 0;
    padding: 4px 6px;
    border-width: 1.5px;
    border-radius: 10px;
  }

  .hud-hp {
    flex: 1.25;
    min-width: 0;
    padding-right: 7px;
  }

  .hud-icon {
    width: 17px;
    height: 21px;
    font-size: 13px;
  }

  .hud-label {
    margin-bottom: 2px;
    font-size: 7px;
    letter-spacing: 0.3px;
  }

  .hud-copy strong {
    font-size: 13px;
  }

  .hud-copy strong small {
    font-size: 8px;
  }

  .hud-kills {
    display: none;
  }

  .hp-track {
    height: 3px;
    margin-top: 3px;
  }

  /* ---- one-screen game layout ---- */

  .layout {
    flex: 1;
    min-height: 0;
    flex-direction: column;
    gap: 7px;
  }

  .stage-shell {
    flex: 1 1 auto;
    height: auto;
    min-height: 0;
    border-width: 2.5px;
    border-radius: 20px;
    box-shadow: 0 5px 0 rgba(48, 34, 66, 0.16), 0 14px 26px rgba(40, 72, 86, 0.11);
  }

  #game {
    height: 100%;
  }

  .stage-topline {
    top: 8px;
    left: 8px;
    right: 8px;
    gap: 5px;
  }

  .stage-tag {
    max-width: 42%;
    overflow: hidden;
    padding: 5px 8px;
    border-width: 1.5px;
    border-radius: 9px;
    font-size: 8.5px;
    white-space: nowrap;
    text-overflow: ellipsis;
  }

  .stage-wave-chip {
    min-height: 28px;
    padding: 5px 8px;
    border-width: 1.5px;
    border-radius: 9px;
    font-size: 9px;
  }

  .stage-wave-chip b {
    font-size: 9px;
  }

  .stage-skip {
    min-height: 34px;
    padding: 6px 10px;
    border-width: 2px;
    border-radius: 10px;
    font-size: 9px;
    box-shadow: 0 2px 0 rgba(48, 34, 66, 0.16);
  }

  .stage-skip span {
    font-size: 14px;
  }

  .stage-hint {
    bottom: 8px;
    max-width: calc(100% - 14px);
    padding: 6px 10px;
    border-width: 1.5px;
    font-size: 8.5px;
    gap: 6px;
  }

  .hint-dot {
    width: 6px;
    height: 6px;
  }

  .toast {
    bottom: 46px;
    max-width: calc(100% - 20px);
    padding: 7px 12px;
    border-width: 2px;
    font-size: 9.5px;
  }

  .wave-banner {
    top: 9%;
    width: min(340px, calc(100% - 24px));
    padding: 8px 14px 9px;
    border-width: 2.5px;
    border-radius: 15px;
  }

  #bannerTitle {
    font-size: 17px;
  }

  #bannerSub {
    font-size: 9px;
  }

  .banner-kicker {
    font-size: 8px;
    letter-spacing: 2px;
  }

  .pause-card {
    min-width: 210px;
    padding: 18px 24px 18px;
    border-radius: 20px;
  }

  .pause-veil {
    position: fixed;
    inset: 0;
    z-index: 45;
  }

  .pause-glyph {
    font-size: 31px;
  }

  .pause-card strong {
    font-size: 18px;
  }

  /* ---- tower shop becomes a fixed horizontal dock ---- */

  .sider {
    position: relative;
    width: 100%;
    height: 120px;
    flex: none;
    min-height: 0;
    padding: 6px;
    overflow: hidden;
    border-width: 2.5px;
    border-radius: 18px;
    box-shadow: 0 4px 0 rgba(48, 34, 66, 0.14);
  }

  .shop-head,
  .side-footer,
  .shop-legend {
    display: none;
  }

  .shop-body {
    display: block;
    height: 100%;
    min-height: 0;
    margin: 0;
    flex: none;
  }

  .tower-list {
    display: flex;
    flex-direction: row;
    gap: 6px;
    width: 100%;
    height: 100%;
    min-height: 0;
    padding: 1px 2px 3px;
    overflow-x: auto;
    overflow-y: hidden;
    scroll-snap-type: x proximity;
    overscroll-behavior-x: contain;
    -webkit-overflow-scrolling: touch;
    scrollbar-width: thin;
    scrollbar-color: #d8c8b4 transparent;
  }

  .tower-list::-webkit-scrollbar {
    height: 3px;
  }

  .tower-list::-webkit-scrollbar-thumb {
    background: #d8c8b4;
    border-radius: 99px;
  }

  .tower-card {
    position: relative;
    flex: 0 0 114px;
    width: 114px;
    height: 100%;
    min-height: 0;
    display: block;
    padding: 8px;
    border-width: 2px;
    border-radius: 13px;
    scroll-snap-align: start;
    touch-action: pan-x;
  }

  .tower-thumb {
    position: absolute;
    top: 8px;
    left: 8px;
    width: 33px;
    height: 33px;
    border-width: 2px;
    border-radius: 9px;
    font-size: 18px;
  }

  .card-main {
    position: absolute;
    top: 7px;
    left: 47px;
    right: 7px;
    display: flex;
    flex-direction: column;
    gap: 2px;
    min-width: 0;
  }

  .card-title-row {
    display: block;
  }

  .card-name {
    display: block;
    overflow: hidden;
    padding-right: 0;
    font-size: 11px;
    line-height: 1.2;
    white-space: nowrap;
    text-overflow: ellipsis;
  }

  .role-tag {
    display: inline-flex;
    margin-top: 2px;
    padding: 1px 3px;
    font-size: 6.5px;
    line-height: 1.25;
  }

  .card-sub {
    display: -webkit-box;
    overflow: hidden;
    margin-top: 1px;
    color: var(--ink-soft);
    font-size: 8.5px;
    font-weight: 700;
    line-height: 1.25;
    white-space: normal;
    -webkit-line-clamp: 2;
    -webkit-box-orient: vertical;
  }

  .card-side {
    position: absolute;
    left: 8px;
    right: 8px;
    bottom: 7px;
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: space-between;
    padding: 0;
  }

  .card-cost {
    position: static;
    font-size: 12px;
  }

  .card-place {
    display: block;
    font-size: 7.5px;
    opacity: 0.72;
  }

  .card-key {
    display: none;
  }

  .tower-card:nth-child(5) {
    grid-column: auto;
  }

  /* ---- tower detail becomes a bottom sheet ---- */

  .inspector {
    position: fixed;
    top: auto;
    right: max(8px, env(safe-area-inset-right));
    bottom: max(8px, env(safe-area-inset-bottom));
    left: max(8px, env(safe-area-inset-left));
    z-index: 40;
    width: auto;
    height: auto;
    min-height: 0;
    max-height: min(76dvh, 570px);
    padding: 13px;
    overflow-y: auto;
    overscroll-behavior: contain;
    border: 3px solid var(--line);
    border-radius: 22px;
    background: var(--paper);
    box-shadow: 0 -8px 0 rgba(48, 34, 66, 0.16), 0 20px 50px rgba(30, 20, 42, 0.3);
    -webkit-overflow-scrolling: touch;
  }

  .inspector-top {
    margin-bottom: 8px;
  }

  .inspector-icon {
    width: 42px;
    height: 42px;
    font-size: 22px;
  }

  .inspector-title h3 {
    font-size: 14px;
  }

  .tower-preview {
    height: 70px;
    margin-bottom: 9px;
  }

  .preview-emoji {
    bottom: 9px;
    font-size: 38px;
  }

  .preview-glow {
    bottom: 4px;
    width: 68px;
    height: 16px;
  }

  .stat-grid {
    gap: 6px;
    margin-bottom: 8px;
  }

  .stat-cell {
    padding: 7px 8px;
  }

  .ability-note {
    margin-bottom: 8px;
    padding: 7px 8px;
    font-size: 8.5px;
  }

  .inspector-actions {
    position: sticky;
    bottom: -1px;
    margin-top: 0;
    padding-top: 8px;
    padding-bottom: 2px;
    background: linear-gradient(180deg, rgba(255, 249, 238, 0), var(--paper) 24%);
  }

  .upgrade-btn,
  .sell-btn,
  .max-level-note {
    min-height: 42px;
  }

  /* ---- modal safety on a locked viewport ---- */

  .overlay {
    padding-top: max(10px, env(safe-area-inset-top));
    padding-right: max(10px, env(safe-area-inset-right));
    padding-bottom: max(10px, env(safe-area-inset-bottom));
    padding-left: max(10px, env(safe-area-inset-left));
  }

  .modal {
    max-height: calc(100dvh - 20px);
    border-width: 3px;
    border-radius: 24px;
  }
}

@media (max-width: 380px) {
  #app {
    padding-left: max(6px, env(safe-area-inset-left));
    padding-right: max(6px, env(safe-area-inset-right));
  }

  .brand-copy h1 {
    font-size: 14px;
  }

  .brand-mark {
    width: 32px;
    height: 32px;
    font-size: 19px;
  }

  .icon-btn {
    width: 33px;
    height: 33px;
  }

  .speed-btn {
    width: 36px;
  }

  .hud-icon {
    display: none;
  }

  .hud-stat {
    padding: 4px 6px;
  }

  .stage-tag {
    max-width: 35%;
    font-size: 8px;
  }

  .stage-skip {
    padding: 6px 7px;
    font-size: 8px;
  }

  .sider {
    height: 114px;
  }

  .tower-card {
    flex-basis: 110px;
    width: 110px;
  }

  .card-name {
    font-size: 10px;
    line-height: 1.15;
  }

  .card-sub {
    font-size: 8px;
  }
}

/* ---- landscape phones: shop on the right, one-row header ---- */

@media (max-width: 940px) and (orientation: landscape) {
  #app {
    padding-top: max(5px, env(safe-area-inset-top));
    padding-bottom: max(5px, env(safe-area-inset-bottom));
    gap: 5px;
  }

  .topbar {
    flex-wrap: nowrap;
    gap: 6px;
    padding: 5px 7px;
    border-radius: 16px;
  }

  .brand {
    flex: 0 0 auto;
    min-width: 0;
  }

  .brand-mark {
    width: 31px;
    height: 31px;
    font-size: 18px;
    border-radius: 9px;
  }

  .brand-copy h1 {
    font-size: 14px;
    white-space: nowrap;
  }

  .hud {
    order: 0;
    flex: 1;
    flex-basis: auto;
    justify-content: flex-end;
    gap: 4px;
  }

  .hud-stat {
    flex: 0 1 auto;
    min-width: auto;
    padding: 4px 6px;
  }

  .hud-hp {
    flex: 0 1 auto;
  }

  .hud-label {
    display: none;
  }

  .hud-icon {
    width: 16px;
    font-size: 12px;
  }

  .hud-copy strong {
    font-size: 11.5px;
  }

  .top-actions {
    gap: 4px;
  }

  .icon-btn {
    width: 31px;
    height: 31px;
    font-size: 13px;
    border-radius: 9px;
  }

  .speed-btn {
    width: 33px;
    font-size: 10px;
  }

  .layout {
    flex-direction: row;
    gap: 6px;
  }

  .stage-shell {
    flex: 1;
    min-width: 0;
    height: auto;
    border-radius: 16px;
  }

  .stage-topline {
    top: 6px;
    left: 6px;
    right: 6px;
  }

  .stage-tag {
    padding: 4px 6px;
    font-size: 8px;
  }

  .stage-wave-chip {
    min-height: 25px;
    padding: 4px 6px;
    font-size: 8px;
  }

  .stage-wave-chip b {
    font-size: 8px;
  }

  .stage-skip {
    min-height: 30px;
    padding: 5px 7px;
    font-size: 8px;
  }

  .stage-hint {
    display: none;
  }

  .toast {
    bottom: 10px;
    font-size: 8.5px;
  }

  .wave-banner {
    top: 7%;
    width: min(320px, calc(100% - 20px));
    padding: 6px 12px 7px;
  }

  #bannerTitle {
    font-size: 16px;
  }

  #bannerSub {
    font-size: 8px;
  }

  .sider {
    width: 108px;
    height: auto;
    padding: 5px;
    border-radius: 16px;
  }

  .shop-body {
    height: 100%;
  }

  .tower-list {
    flex-direction: column;
    gap: 4px;
    height: 100%;
    padding: 1px 1px 2px;
    overflow-x: hidden;
    overflow-y: auto;
    scroll-snap-type: y proximity;
  }

  .tower-card {
    flex: 0 0 auto;
    width: 100%;
    height: 56px;
    padding: 5px;
  }

  .tower-thumb {
    top: 5px;
    left: 5px;
    width: 24px;
    height: 24px;
    font-size: 13px;
    border-radius: 7px;
  }

  .card-main {
    top: 4px;
    left: 33px;
    right: 4px;
  }

  .card-name {
    font-size: 9px;
  }

  .role-tag {
    display: none;
  }

  .card-sub {
    display: none;
  }

  .card-side {
    left: 5px;
    right: 5px;
    bottom: 3px;
  }

  .card-cost {
    font-size: 9.5px;
  }

  .card-place {
    display: none;
  }

  .inspector {
    top: 6px;
    right: 6px;
    bottom: 6px;
    left: auto;
    width: min(320px, 46vw);
    max-height: none;
    padding: 11px;
    border-radius: 18px;
  }

  .tower-preview {
    height: 58px;
  }

  .preview-emoji {
    font-size: 32px;
    bottom: 5px;
  }

  .stat-grid {
    grid-template-columns: repeat(2, minmax(0, 1fr));
  }

  .overlay {
    align-items: flex-start;
  }
}

@media (max-width: 940px) and (orientation: landscape) and (max-height: 390px) {
  .brand-mark {
    display: none;
  }

  .brand-copy h1 {
    font-size: 12px;
  }

  .sider {
    width: 102px;
  }

  .tower-card {
    height: 50px;
  }

  .tower-thumb {
    width: 21px;
    height: 21px;
    font-size: 12px;
  }

  .card-main {
    left: 29px;
  }

  .card-name {
    font-size: 8.5px;
  }

  .card-cost {
    font-size: 8.5px;
  }
}

</style>
  <style>
/* ==========================================================================
   Web shell extras — install / share / fullscreen affordances.
   Loaded after style.css so it can reuse the game palette and type scale.
   ========================================================================== */

body {
  /* Kill the 300ms double-tap zoom on touch screens without blocking pans. */
  touch-action: manipulation;
}

#game {
  touch-action: manipulation;
}

/* Keep dialogs clear of notches and the iOS home indicator. */
.overlay {
  padding-top: max(20px, env(safe-area-inset-top));
  padding-right: max(20px, env(safe-area-inset-right));
  padding-bottom: max(20px, env(safe-area-inset-bottom));
  padding-left: max(20px, env(safe-area-inset-left));
}

.web-actions {
  display: flex;
  gap: 8px;
  margin-top: 12px;
}

.web-action {
  flex: 1 1 0;
  min-width: 0;
  min-height: 40px;
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 6px;
  padding: 8px 7px;
  border: 2.5px solid var(--line);
  border-radius: 13px;
  background: #fffdf7;
  box-shadow: 0 3px 0 rgba(48, 34, 66, 0.16), inset 0 2px 0 rgba(255, 255, 255, 0.72);
  color: var(--ink);
  font-size: 10px;
  font-weight: 900;
  letter-spacing: 0.2px;
  white-space: nowrap;
  cursor: pointer;
  transition: transform 0.12s ease, box-shadow 0.12s ease, background 0.12s ease;
}

.web-action:hover {
  background: #fff7e2;
  transform: translateY(-1px);
  box-shadow: 0 4px 0 rgba(48, 34, 66, 0.16), inset 0 2px 0 rgba(255, 255, 255, 0.72);
}

.web-action:active {
  transform: translateY(2px);
  box-shadow: 0 1px 0 rgba(48, 34, 66, 0.16), inset 0 2px 0 rgba(255, 255, 255, 0.72);
}

.web-action[hidden] {
  display: none;
}

.web-action-icon {
  display: inline-block;
  font-size: 14px;
  line-height: 1;
  filter: drop-shadow(0 1px 0 rgba(255, 255, 255, 0.6));
}

.web-tip {
  margin: 10px 0 0;
  padding: 8px 10px;
  border: 1.5px dashed #e0b866;
  border-radius: 10px;
  background: #fff8df;
  color: #8c6425;
  font-size: 8.5px;
  font-weight: 700;
  line-height: 1.55;
  text-align: center;
}

/* Installed / standalone mode: the page already owns the whole screen. */
html.is-standalone .fullscreen-only,
html.is-standalone .install-only {
  display: none !important;
}

html.is-standalone .web-actions {
  justify-content: center;
}

html.is-standalone .web-action {
  flex: 0 0 auto;
  padding-inline: 22px;
}

/* Browsers that cannot install still get a clean two-button row. */
@media (max-width: 600px) {  .web-actions {
    gap: 6px;
    margin-top: 10px;
  }

  .web-action {
    min-height: 38px;
    gap: 4px;
    padding: 7px 5px;
    border-width: 2px;
    border-radius: 11px;
    font-size: 9.5px;
  }

  .web-action-icon {
    font-size: 13px;
  }

  .web-tip {
    margin-top: 8px;
    padding: 7px 9px;
    font-size: 8px;
  }
}

@media (max-width: 350px) {
  .web-action-icon {
    display: none;
  }
}

@media (prefers-reduced-motion: reduce) {
  .web-action {
    transition: none;
  }
}

/* ---------- no-JS fallback ---------- */

.noscript-card {
  position: fixed;
  inset: 0;
  z-index: 200;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 10px;
  padding: 28px;
  background: linear-gradient(160deg, #73d4ee, #a9eddb 62%, #e4f6ba);
  color: var(--ink);
  text-align: center;
}

.noscript-card strong {
  font-size: 22px;
}

.noscript-card p {
  max-width: 420px;
  margin: 0;
  color: #5f536c;
  font-size: 13px;
  font-weight: 700;
  line-height: 1.7;
}


</style>
</head>
<body>
  <noscript>
    <div class="noscript-card">
      <strong>需要开启 JavaScript</strong>
      <p>糖果岛塔防是一款用 Canvas 绘制的网页小游戏，请在浏览器设置中允许 JavaScript 后刷新页面。</p>
    </div>
  </noscript>

  <div class="ambient-cloud cloud-a" aria-hidden="true"></div>
  <div class="ambient-cloud cloud-b" aria-hidden="true"></div>
  <div class="ambient-cloud cloud-c" aria-hidden="true"></div>

  <div id="app">
    <header class="topbar">
      <div class="brand">
        <div class="brand-mark" aria-hidden="true">🍭</div>
        <div class="brand-copy">
          <h1>糖果岛塔防</h1>
          <p>守住中央的水晶蛋糕</p>
        </div>
      </div>

      <div class="hud" aria-label="战局数据">
        <div class="hud-stat hud-hp" id="hpStat">
          <span class="hud-icon">💗</span>
          <span class="hud-copy">
            <span class="hud-label">基地</span>
            <strong><span id="baseHp">12</span><small>/<span id="baseHpMax">12</span></small></strong>
            <span class="hp-track"><i id="hpBar"></i></span>
          </span>
        </div>
        <div class="hud-stat">
          <span class="hud-icon">🪙</span>
          <span class="hud-copy"><span class="hud-label">糖果币</span><strong id="coinHud">220</strong></span>
        </div>
        <div class="hud-stat">
          <span class="hud-icon">🌊</span>
          <span class="hud-copy"><span class="hud-label">波次</span><strong id="waveHud">准备</strong></span>
        </div>
        <div class="hud-stat hud-time">
          <span class="hud-icon">⏱️</span>
          <span class="hud-copy"><span class="hud-label">坚持</span><strong id="timeHud">00:00</strong></span>
        </div>
        <div class="hud-stat hud-kills">
          <span class="hud-icon">☠️</span>
          <span class="hud-copy"><span class="hud-label">击杀</span><strong id="killHud">0</strong></span>
        </div>
      </div>

      <div class="top-actions">
        <button class="icon-btn" id="pauseBtn" type="button" title="暂停 / 继续 (P)" aria-label="暂停游戏">
          <span id="pauseIcon">⏸</span>
        </button>
        <button class="icon-btn speed-btn" id="speedBtn" type="button" title="切换游戏速度" aria-label="切换游戏速度">x1</button>
        <button class="icon-btn" id="soundBtn" type="button" title="开关音效" aria-label="开关音效">
          <span id="soundIcon">🔊</span>
        </button>
      </div>
    </header>

    <main class="layout">
      <section class="stage-shell" id="stageShell">
        <canvas id="game" aria-label="糖果岛塔防游戏区域"></canvas>
        <div class="stage-topline">
          <span class="stage-tag" id="selectionTag">🛠️ 先选一座防御塔</span>
          <span class="stage-wave-chip" id="stageWaveChip"><i></i><b id="stageWaveText">准备迎战</b></span>
          <button class="stage-skip" id="skipPrepBtn" type="button" title="立即开始下一波" hidden>跳过准备 <span>›</span></button>
        </div>

        <div class="wave-banner" id="waveBanner" aria-live="polite">
          <span class="banner-kicker">WAVE</span>
          <strong id="bannerTitle">第 1 波来袭</strong>
          <span id="bannerSub">软糖军团正在靠近</span>
        </div>

        <div class="toast" id="toast" role="status"></div>

        <div class="stage-hint" id="stageHint">
          <span class="hint-dot"></span>
          <span id="stageHintText">选择商店里的防御塔，再点击发光的基座建造</span>
        </div>

        <div class="pause-veil" id="pauseVeil" hidden>
          <div class="pause-card">
            <span class="pause-glyph">☁️</span>
            <strong>暂停一下</strong>
            <p>敌人也停下来喝茶了</p>
            <button class="mini-primary" id="resumeBtn" type="button">继续守卫</button>
          </div>
        </div>

        <div class="stage-vignette" id="stageVignette" aria-hidden="true"></div>
      </section>

      <aside class="sider">
        <div class="shop-head">
          <div>
            <p class="eyebrow">BUILD SHOP</p>
            <h2>防御塔商店</h2>
          </div>
          <div class="coin-chip"><span>🪙</span><b id="shopCoins">220</b></div>
        </div>

        <div class="shop-body">
          <div class="tower-list" id="towerList"></div>
          <div class="shop-legend">
            <div class="legend-title"><span>🛡️</span> 布阵小抄</div>
            <div class="legend-row"><span class="legend-mark legend-round">＋</span><span>圆形草垫：建造路旁防御塔</span></div>
            <div class="legend-row"><span class="legend-mark legend-diamond">＋</span><span>路面盾牌：建造可堵路的果冻路障</span></div>
            <div class="legend-row"><span class="legend-mark legend-fly">🦇</span><span>飞行敌人会绕过路障，记得留防空火力</span></div>
          </div>
          <div class="inspector" id="inspector" hidden></div>
        </div>

        <div class="side-footer">
          <div class="wave-panel">
            <div class="wave-head">
              <span class="live-dot" id="waveDot"></span>
              <b id="wavePhase">第 1 波正在集结</b>
              <span id="waveCountdown">8s</span>
            </div>
            <div class="wave-meter"><i id="waveMeter"></i></div>
            <p id="waveHint">趁现在布置防线，点击地图上的发光基座。</p>
          </div>
          <div class="record-mini">
            <span>🏆 最佳：<b id="bestTimeMini">--:--</b> · <b id="bestKillMini">0</b> 杀</span>
            <span class="tip-inline">飞行敌人会绕过路障</span>
          </div>
        </div>
      </aside>
    </main>
  </div>

  <div class="overlay" id="startOverlay">
    <div class="modal start-modal">
      <div class="start-hero" aria-hidden="true">
        <div class="hero-sky"></div>
        <div class="hero-island">
          <span class="hero-enemy hero-e1">👾</span>
          <span class="hero-enemy hero-e2">🦇</span>
          <span class="hero-enemy hero-e3">🐢</span>
          <div class="hero-core">💎</div>
          <span class="hero-tower hero-t1">🍭</span>
          <span class="hero-tower hero-t2">🍦</span>
          <span class="hero-tower hero-t3">🍿</span>
          <span class="hero-spark s1">✦</span>
          <span class="hero-spark s2">✧</span>
          <span class="hero-spark s3">✦</span>
        </div>
      </div>

      <p class="eyebrow">WELCOME TO CANDY ISLE</p>
      <h2 class="start-title">糖果岛被包围啦！</h2>
      <p class="modal-desc">八条主道路通向中央，捣蛋军团正从八个方向赶来。用不同本领的防御塔守到最后吧。</p>

      <div class="how-grid">
        <div class="how-item">
          <span class="how-icon">👆</span>
          <b>点选建造</b>
          <p>选塔后点击地图上的发光基座</p>
        </div>
        <div class="how-item">
          <span class="how-icon">🧱</span>
          <b>路障堵路</b>
          <p>放在路面，拦停敌人并震击它们</p>
        </div>
        <div class="how-item">
          <span class="how-icon">🌈</span>
          <b>搭配清场</b>
          <p>减速、溅射与连锁让火力翻倍</p>
        </div>
      </div>

      <p class="rule-line"><span>!</span> 水晶基地生命归零，本轮结束。活得越久，敌人等级和糖果币奖励越高。</p>

      <button class="primary-btn start-btn" id="startBtn" type="button">开始守卫 <span>→</span></button>

      <div class="record-strip">
        <span class="record-strip-label">🏆 你的最佳</span>
        <span>坚持 <b id="startBestTime">--:--</b></span>
        <span class="record-divider"></span>
        <span>击杀 <b id="startBestKills">0</b></span>
        <button class="link-btn" id="resetRecordsBtn" type="button">清空记录</button>
      </div>

      <div class="web-actions" aria-label="网页版功能">
        <button class="web-action install-only" id="installAppBtn" type="button" hidden>
          <span class="web-action-icon" aria-hidden="true">📲</span>
          <span class="web-action-label">安装到桌面</span>
        </button>
        <button class="web-action" id="shareGameBtn" type="button">
          <span class="web-action-icon" aria-hidden="true">🔗</span>
          <span class="web-action-label">分享游戏</span>
        </button>
        <button class="web-action fullscreen-only" id="fullscreenBtn" type="button" aria-pressed="false">
          <span class="web-action-icon" aria-hidden="true">⛶</span>
          <span class="web-action-label">全屏游玩</span>
        </button>
      </div>
      <p class="web-tip" id="installTip" hidden></p>
    </div>
  </div>

  <div class="overlay" id="gameOverOverlay" hidden>
    <div class="modal gameover-modal">
      <div class="gameover-art" aria-hidden="true">
        <span class="sad-crystal">💎</span>
        <span class="sad-spark sp1">✦</span>
        <span class="sad-spark sp2">✧</span>
        <span class="sad-spark sp3">✦</span>
      </div>
      <p class="eyebrow">CRYSTAL DOWN</p>
      <h2 class="gameover-title">水晶失守啦！</h2>
      <p class="modal-desc" id="gameoverDesc">捣蛋军团冲破了防线。调整阵容，再守一次吧。</p>

      <div class="result-grid">
        <div class="result-item">
          <span class="result-icon">⏱️</span>
          <span class="result-label">本局坚持</span>
          <strong id="runTime">00:00</strong>
        </div>
        <div class="result-item">
          <span class="result-icon">☠️</span>
          <span class="result-label">击杀敌人</span>
          <strong id="runKills">0</strong>
        </div>
      </div>

      <div class="record-grid">
        <div class="record-card" id="recordTimeCard">
          <span class="record-crown">👑</span>
          <span class="record-label">最长坚持</span>
          <strong id="bestTimeResult">00:00</strong>
          <span class="new-record" id="newTimeBadge" hidden>新纪录</span>
        </div>
        <div class="record-card" id="recordKillCard">
          <span class="record-crown">👑</span>
          <span class="record-label">最多击杀</span>
          <strong id="bestKillResult">0</strong>
          <span class="new-record" id="newKillBadge" hidden>新纪录</span>
        </div>
      </div>

      <div class="gameover-actions">
        <button class="primary-btn" id="restartBtn" type="button">再守一次 <span>↻</span></button>
        <button class="ghost-btn" id="shareScoreBtn" type="button">📤 分享</button>
      </div>
      <p class="gameover-footnote" id="gameoverFootnote">第 1 波 · 基地还剩 0 滴生命</p>
    </div>
  </div>

  <script>
(() => {
  'use strict';

  // ---------------------------------------------------------------------------
  // Tiny helpers
  // ---------------------------------------------------------------------------
  const TAU = Math.PI * 2;
  const $ = (sel) => document.querySelector(sel);
  const clamp = (v, min, max) => Math.max(min, Math.min(max, v));
  const lerp = (a, b, t) => a + (b - a) * t;
  const rand = (a, b) => a + Math.random() * (b - a);
  const randInt = (a, b) => Math.floor(rand(a, b + 1));
  const dist = (x1, y1, x2, y2) => Math.hypot(x2 - x1, y2 - y1);
  const angleDelta = (from, to) => ((to - from + Math.PI * 3) % TAU) - Math.PI;
  const formatTime = (seconds) => {
    const total = Math.max(0, Math.floor(seconds));
    const h = Math.floor(total / 3600);
    const m = Math.floor((total % 3600) / 60);
    const s = total % 60;
    const mm = String(m).padStart(2, '0');
    const ss = String(s).padStart(2, '0');
    return h > 0 ? `${h}:${mm}:${ss}` : `${mm}:${ss}`;
  };
  const styleFont = (size, weight = 800) =>
    `${weight} ${size}px "Arial Rounded MT Bold", "Microsoft YaHei", "PingFang SC", sans-serif`;

  // ---------------------------------------------------------------------------
  // DOM
  // ---------------------------------------------------------------------------
  const canvas = $('#game');
  const stageShell = $('#stageShell');
  const ctx = canvas.getContext('2d');
  const dom = {
    baseHp: $('#baseHp'),
    baseHpMax: $('#baseHpMax'),
    hpBar: $('#hpBar'),
    hpStat: $('#hpStat'),
    coinHud: $('#coinHud'),
    waveHud: $('#waveHud'),
    timeHud: $('#timeHud'),
    killHud: $('#killHud'),
    shopCoins: $('#shopCoins'),
    towerList: $('#towerList'),
    inspector: $('#inspector'),
    pauseBtn: $('#pauseBtn'),
    pauseIcon: $('#pauseIcon'),
    resumeBtn: $('#resumeBtn'),
    speedBtn: $('#speedBtn'),
    soundBtn: $('#soundBtn'),
    soundIcon: $('#soundIcon'),
    pauseVeil: $('#pauseVeil'),
    selectionTag: $('#selectionTag'),
    stageHint: $('#stageHint'),
    stageHintText: $('#stageHintText'),
    stageWaveChip: $('#stageWaveChip'),
    stageWaveText: $('#stageWaveText'),
    skipPrepBtn: $('#skipPrepBtn'),
    toast: $('#toast'),
    waveBanner: $('#waveBanner'),
    bannerKicker: $('.banner-kicker'),
    bannerTitle: $('#bannerTitle'),
    bannerSub: $('#bannerSub'),
    wavePhase: $('#wavePhase'),
    waveCountdown: $('#waveCountdown'),
    waveMeter: $('#waveMeter'),
    waveHint: $('#waveHint'),
    waveDot: $('#waveDot'),
    bestTimeMini: $('#bestTimeMini'),
    bestKillMini: $('#bestKillMini'),
    startOverlay: $('#startOverlay'),
    startBtn: $('#startBtn'),
    gameOverOverlay: $('#gameOverOverlay'),
    restartBtn: $('#restartBtn'),
    runTime: $('#runTime'),
    runKills: $('#runKills'),
    gameoverDesc: $('#gameoverDesc'),
    gameoverFootnote: $('#gameoverFootnote'),
    bestTimeResult: $('#bestTimeResult'),
    bestKillResult: $('#bestKillResult'),
    newTimeBadge: $('#newTimeBadge'),
    newKillBadge: $('#newKillBadge'),
    recordTimeCard: $('#recordTimeCard'),
    recordKillCard: $('#recordKillCard'),
    resetRecordsBtn: $('#resetRecordsBtn'),
    startBestTime: $('#startBestTime'),
    startBestKills: $('#startBestKills'),
    stageVignette: $('#stageVignette'),
    speedBtn: $('#speedBtn')
  };

  // ---------------------------------------------------------------------------
  // Game data
  // ---------------------------------------------------------------------------
  const TOWER_ORDER = ['gum', 'frost', 'pop', 'jelly', 'prism'];

  const TOWER_DEFS = {
    gum: {
      name: '泡泡糖弓手',
      role: '单体',
      placement: 'side',
      placeName: '路旁',
      icon: '🍭',
      accent: '#ffb06e',
      cost: 45,
      summary: '射速快，优先点杀最靠近基地的敌人',
      note: '单点输出稳定，适合在道路两侧补足持续伤害。',
      levels: [
        { damage: 11, range: 156, interval: 0.62 },
        { damage: 17, range: 169, interval: 0.54 },
        { damage: 26, range: 183, interval: 0.46 },
        { damage: 38, range: 199, interval: 0.39 }
      ],
      upgrades: [55, 90, 135]
    },
    frost: {
      name: '薄荷冰沙塔',
      role: '减速',
      placement: 'side',
      placeName: '路旁',
      icon: '🍦',
      accent: '#8fe1f4',
      cost: 70,
      summary: '冰晶攻击使敌人变慢，为火力争取时间',
      note: '减速可以叠加刷新持续时间，先减速再集火效率更高。',
      levels: [
        { damage: 7, range: 151, interval: 0.82, slow: 0.45, slowDuration: 1.8 },
        { damage: 11, range: 164, interval: 0.76, slow: 0.5, slowDuration: 1.9 },
        { damage: 17, range: 177, interval: 0.7, slow: 0.56, slowDuration: 2.1 },
        { damage: 25, range: 191, interval: 0.64, slow: 0.63, slowDuration: 2.3 }
      ],
      upgrades: [80, 120, 170]
    },
    pop: {
      name: '爆米花炮台',
      role: '范围',
      placement: 'side',
      placeName: '路旁',
      icon: '🍿',
      accent: '#ffd66b',
      cost: 110,
      summary: '抛射爆米花，对落点周围造成溅射伤害',
      note: '面对成群敌人非常划算。射速偏慢，最好和减速塔搭配。',
      levels: [
        { damage: 26, range: 190, interval: 1.45, splash: 64 },
        { damage: 40, range: 205, interval: 1.38, splash: 70 },
        { damage: 60, range: 220, interval: 1.31, splash: 76 },
        { damage: 86, range: 235, interval: 1.24, splash: 84 }
      ],
      upgrades: [125, 180, 240]
    },
    jelly: {
      name: '果冻路障',
      role: '路障',
      placement: 'road',
      placeName: '路面',
      icon: '🍮',
      accent: '#8fd7f0',
      cost: 65,
      summary: '放在道路上拦停地面敌人，并周期震击周围',
      note: '敌人会停下来攻击路障。可配合两侧炮塔，把道路变成火力口袋。飞行敌人会绕过它。',
      levels: [
        { hp: 520, pulseDamage: 12, range: 102, interval: 0.9 },
        { hp: 800, pulseDamage: 18, range: 110, interval: 0.82 },
        { hp: 1200, pulseDamage: 27, range: 118, interval: 0.74 },
        { hp: 1750, pulseDamage: 40, range: 128, interval: 0.66 }
      ],
      upgrades: [75, 115, 160]
    },
    prism: {
      name: '彩虹棱镜',
      role: '连锁',
      placement: 'side',
      placeName: '路旁',
      icon: '🌈',
      accent: '#c1a7ff',
      cost: 160,
      summary: '彩虹闪电在敌人间弹射，适合清理密集队列',
      note: '每次命中后伤害略微衰减，能一次电到一整串敌人。',
      levels: [
        { damage: 25, range: 200, interval: 1.5, chain: 3, falloff: 0.68 },
        { damage: 38, range: 214, interval: 1.42, chain: 4, falloff: 0.7 },
        { damage: 56, range: 228, interval: 1.34, chain: 4, falloff: 0.72 },
        { damage: 80, range: 244, interval: 1.26, chain: 5, falloff: 0.75 }
      ],
      upgrades: [170, 240, 320]
    }
  };

  const ENEMY_DEFS = {
    slime: {
      name: '青柠果冻',
      hp: 46,
      speed: 47,
      reward: 9,
      lives: 1,
      size: 17,
      attack: 6,
      attackRate: 1.1,
      armor: 0,
      color: '#8fe06f',
      color2: '#56b94d',
      accent: '#e0ffc3'
    },
    runner: {
      name: '跳跳糖兔',
      hp: 38,
      speed: 82,
      reward: 12,
      lives: 1,
      size: 14,
      attack: 5,
      attackRate: 0.8,
      armor: 0,
      color: '#ffa2ba',
      color2: '#ea6f93',
      accent: '#ffe1e9'
    },
    tank: {
      name: '焦糖铁甲龟',
      hp: 190,
      speed: 29,
      reward: 26,
      lives: 2,
      size: 23,
      attack: 15,
      attackRate: 1.3,
      armor: 0.18,
      color: '#b8d56f',
      color2: '#779c3f',
      accent: '#eef9b6'
    },
    flyer: {
      name: '夜莓蝙蝠',
      hp: 64,
      speed: 67,
      reward: 15,
      lives: 1,
      size: 16,
      attack: 7,
      attackRate: 1,
      armor: 0,
      flying: true,
      color: '#bca4ff',
      color2: '#8068cf',
      accent: '#ebdfff'
    },
    boss: {
      name: '暴走糖果王',
      hp: 950,
      speed: 21,
      reward: 130,
      lives: 4,
      size: 35,
      attack: 38,
      attackRate: 1.4,
      armor: 0.1,
      boss: true,
      color: '#ff907e',
      color2: '#d95163',
      accent: '#ffe3b0'
    }
  };

  const PORTAL_COLORS = [
    '#ffb3cf', '#ffd27a', '#a9f1d0', '#8fd7ff',
    '#c7b5ff', '#ffad9a', '#d7ef8d', '#9be7dc'
  ];
  const LANE_TARGETS = [
    { nx: 0, ny: -1 },
    { nx: 1, ny: -1 },
    { nx: 1, ny: 0 },
    { nx: 1, ny: 1 },
    { nx: 0, ny: 1 },
    { nx: -1, ny: 1 },
    { nx: -1, ny: 0 },
    { nx: -1, ny: -1 }
  ];
  const LANE_COUNT = LANE_TARGETS.length;
  const PREP_SECONDS = 30;

  // ---------------------------------------------------------------------------
  // Record storage
  // ---------------------------------------------------------------------------
  const RECORD_KEY = 'candy-isle-td-records-v1';
  let records = loadRecords();

  function loadRecords() {
    try {
      const raw = localStorage.getItem(RECORD_KEY);
      if (!raw) return { bestTime: 0, bestKills: 0 };
      const parsed = JSON.parse(raw);
      return {
        bestTime: Math.max(0, Number(parsed.bestTime) || 0),
        bestKills: Math.max(0, Math.floor(Number(parsed.bestKills) || 0))
      };
    } catch (err) {
      return { bestTime: 0, bestKills: 0 };
    }
  }

  function saveRecords() {
    try {
      localStorage.setItem(RECORD_KEY, JSON.stringify(records));
    } catch (err) {
      // Storage may be unavailable in private or sandboxed contexts.
    }
  }

  function refreshRecordUI() {
    const bestTimeText = records.bestTime > 0 ? formatTime(records.bestTime) : '--:--';
    dom.bestTimeMini.textContent = bestTimeText;
    dom.bestKillMini.textContent = String(records.bestKills);
    dom.startBestTime.textContent = bestTimeText;
    dom.startBestKills.textContent = String(records.bestKills);
    dom.bestTimeResult.textContent = bestTimeText;
    dom.bestKillResult.textContent = String(records.bestKills);
  }

  // ---------------------------------------------------------------------------
  // Sound effects
  // ---------------------------------------------------------------------------
  let audioCtx = null;
  let masterGain = null;
  let soundEnabled = true;
  let lastShootSound = 0;
  let lastKillSound = 0;
  let lastPulseSound = 0;

  function ensureAudio() {
    if (!soundEnabled) return null;
    if (!audioCtx) {
      const AudioCtor = window.AudioContext || window.webkitAudioContext;
      if (!AudioCtor) return null;
      try {
        audioCtx = new AudioCtor();
        masterGain = audioCtx.createGain();
        masterGain.gain.value = 0.72;
        masterGain.connect(audioCtx.destination);
      } catch (err) {
        return null;
      }
    }
    if (audioCtx.state === 'suspended') audioCtx.resume().catch(() => {});
    return audioCtx;
  }

  function playTone(freq, duration, type = 'sine', volume = 0.03, endFreq = null, delay = 0) {
    if (!soundEnabled) return;
    const ac = ensureAudio();
    if (!ac) return;
    const now = ac.currentTime + delay;
    const osc = ac.createOscillator();
    const gain = ac.createGain();
    osc.type = type;
    osc.frequency.setValueAtTime(Math.max(20, freq), now);
    if (endFreq) {
      osc.frequency.exponentialRampToValueAtTime(Math.max(20, endFreq), now + duration);
    }
    gain.gain.setValueAtTime(0.0001, now);
    gain.gain.linearRampToValueAtTime(volume, now + 0.012);
    gain.gain.exponentialRampToValueAtTime(0.0001, now + duration);
    osc.connect(gain);
    gain.connect(masterGain);
    osc.start(now);
    osc.stop(now + duration + 0.03);
  }

  function playNoise(duration = 0.2, volume = 0.035, filterFreq = 900) {
    if (!soundEnabled) return;
    const ac = ensureAudio();
    if (!ac) return;
    const length = Math.floor(ac.sampleRate * duration);
    const buffer = ac.createBuffer(1, length, ac.sampleRate);
    const data = buffer.getChannelData(0);
    for (let i = 0; i < length; i += 1) {
      data[i] = (Math.random() * 2 - 1) * (1 - i / length);
    }
    const source = ac.createBufferSource();
    source.buffer = buffer;
    const filter = ac.createBiquadFilter();
    filter.type = 'lowpass';
    filter.frequency.value = filterFreq;
    const gain = ac.createGain();
    gain.gain.value = volume;
    source.connect(filter);
    filter.connect(gain);
    gain.connect(masterGain);
    source.start();
  }

  const sfx = {
    build() {
      playTone(520, 0.09, 'triangle', 0.028, 780);
      playTone(780, 0.12, 'sine', 0.018, 1040, 0.05);
    },
    upgrade() {
      [523, 659, 784, 1046].forEach((freq, i) =>
        playTone(freq, 0.12, 'triangle', 0.019, null, i * 0.055)
      );
    },
    sell() {
      playTone(430, 0.1, 'sine', 0.02, 260);
      playTone(330, 0.13, 'triangle', 0.015, 200, 0.06);
    },
    shootGum() {
      const now = performance.now();
      if (now - lastShootSound < 55) return;
      lastShootSound = now;
      playTone(820, 0.055, 'square', 0.0075, 540);
    },
    shootFrost() {
      const now = performance.now();
      if (now - lastShootSound < 55) return;
      lastShootSound = now;
      playTone(1180, 0.07, 'sine', 0.0075, 1550);
    },
    shootPop() {
      playTone(150, 0.1, 'triangle', 0.025, 90);
    },
    jellyPulse() {
      const now = performance.now();
      if (now - lastPulseSound < 110) return;
      lastPulseSound = now;
      playTone(132, 0.16, 'sine', 0.018, 76);
    },
    prism() {
      [880, 1100, 1320, 1580].forEach((freq, i) =>
        playTone(freq, 0.08, 'triangle', 0.006, freq * 1.1, i * 0.025)
      );
    },
    hitBlock() {
      const now = performance.now();
      if (now - lastKillSound < 70) return;
      lastKillSound = now;
      playTone(180, 0.045, 'square', 0.007, 120);
    },
    kill() {
      const now = performance.now();
      if (now - lastKillSound < 45) return;
      lastKillSound = now;
      playTone(520, 0.07, 'triangle', 0.012, 760);
    },
    killBoss() {
      playTone(120, 0.5, 'sawtooth', 0.03, 42);
      playNoise(0.55, 0.05, 500);
    },
    leak() {
      playTone(180, 0.24, 'sawtooth', 0.03, 70);
      playNoise(0.25, 0.03, 380);
    },
    wave() {
      [392, 494, 587].forEach((freq, i) =>
        playTone(freq, 0.24, 'triangle', 0.017, null, i * 0.08)
      );
    },
    bossWave() {
      playTone(95, 0.6, 'sawtooth', 0.035, 52);
      playTone(140, 0.45, 'square', 0.015, 90, 0.15);
      playNoise(0.6, 0.035, 420);
    },
    gameOver() {
      [392, 330, 262, 196].forEach((freq, i) =>
        playTone(freq, 0.42, 'triangle', 0.025, freq * 0.86, i * 0.17)
      );
      playNoise(0.8, 0.02, 340);
    }
  };

  // ---------------------------------------------------------------------------
  // World state
  // ---------------------------------------------------------------------------
  let W = 800;
  let H = 600;
  let DPR = Math.min(window.devicePixelRatio || 1, 2);
  const C = { x: 400, y: 300 };
  let baseR = 52;
  let lanes = [];
  let pads = [];
  let decor = [];
  let bgCanvas = null;
  let nextTowerId = 1;

  const game = {
    phase: 'intro',
    paused: false,
    speed: 1,
    ambient: 0,
    time: 0,
    wave: 0,
    coins: 220,
    lives: 12,
    maxLives: 12,
    kills: 0,
    prepTime: PREP_SECONDS,
    prepTotal: PREP_SECONDS,
    spawnTimer: 0,
    spawnQueue: [],
    spawnTotal: 0,
    bossWave: false,
    selectedBuild: null,
    selectedTower: null,
    hoverPad: null,
    hoverEnemy: null,
    enemies: [],
    projectiles: [],
    particles: [],
    effects: [],
    floats: [],
    shake: 0,
    baseHit: 0,
    gameOverTimer: 0,
    endScheduled: false
  };

  let toastTimer = 0;
  let bannerTimer = 0;
  let lastFrameTime = performance.now();
  let lastUiTime = 0;
  const nodeTextCache = new WeakMap();

  const isActivePhase = () =>
    game.phase === 'prep' || game.phase === 'spawning' || game.phase === 'clearing';

  // ---------------------------------------------------------------------------
  // Audio / UI helpers
  // ---------------------------------------------------------------------------
  function setText(node, text) {
    if (!node) return;
    const value = String(text);
    if (nodeTextCache.get(node) === value) return;
    nodeTextCache.set(node, value);
    node.textContent = value;
  }

  function showToast(message, tone = '') {
    dom.toast.textContent = message;
    dom.toast.className = `toast show ${tone}`.trim();
    window.clearTimeout(toastTimer);
    toastTimer = window.setTimeout(() => {
      dom.toast.className = 'toast';
    }, 1900);
  }

  function showBanner(title, sub, boss = false, kicker = 'WAVE') {
    dom.bannerKicker.textContent = kicker;
    dom.bannerTitle.textContent = title;
    dom.bannerSub.textContent = sub;
    dom.waveBanner.classList.remove('show', 'is-boss');
    if (boss) dom.waveBanner.classList.add('is-boss');
    // Force a fresh CSS animation even on repeated waves.
    void dom.waveBanner.offsetWidth;
    dom.waveBanner.classList.add('show');
    window.clearTimeout(bannerTimer);
    bannerTimer = window.setTimeout(() => {
      dom.waveBanner.classList.remove('show');
    }, 2450);
  }

  function updateSelectionUI() {
    if (game.selectedBuild) {
      const def = TOWER_DEFS[game.selectedBuild];
      const place = def.placement === 'road' ? '路面盾牌基座' : '路旁圆形基座';
      dom.selectionTag.textContent = `🛠️ ${def.name} · 🪙${def.cost}`;
      dom.stageHintText.textContent = `点击${place}建造 · 按 Esc 取消选择`;
      dom.stageHint.classList.remove('warning');
      dom.selectionTag.style.background = 'rgba(255, 248, 212, 0.94)';
    } else if (game.selectedTower) {
      const tower = game.selectedTower;
      const def = TOWER_DEFS[tower.type];
      dom.selectionTag.textContent = `🔍 ${def.name} · Lv.${tower.level}`;
      dom.stageHintText.textContent = '可在商店中查看属性、升级或拆除这座防御塔';
      dom.stageHint.classList.remove('warning');
      dom.selectionTag.style.background = 'rgba(255, 251, 240, 0.94)';
    } else if (game.phase === 'over') {
      dom.selectionTag.textContent = '💔 战斗结束';
      dom.stageHintText.textContent = '点击「再守一次」重新开始';
      dom.selectionTag.style.background = 'rgba(255, 240, 238, 0.94)';
    } else {
      dom.selectionTag.textContent = '🛠️ 先选一座防御塔';
      dom.stageHintText.textContent = '选择商店里的防御塔，再点击地图上发光的基座建造';
      dom.stageHint.classList.remove('warning');
      dom.selectionTag.style.background = 'rgba(255, 251, 240, 0.9)';
    }
  }

  function updateHUD() {
    dom.skipPrepBtn.hidden = game.phase !== 'prep';
    setText(dom.baseHp, game.lives);
    setText(dom.baseHpMax, game.maxLives);
    setText(dom.coinHud, game.coins);
    setText(dom.shopCoins, game.coins);
    setText(dom.killHud, game.kills);
    setText(dom.timeHud, formatTime(game.time));
    dom.hpBar.style.width = `${clamp(game.lives / game.maxLives, 0, 1) * 100}%`;
    dom.hpStat.classList.toggle('is-low', game.lives <= 3 && game.phase !== 'intro');

    const nextWave = game.wave + 1;
    if (game.phase === 'intro') {
      setText(dom.waveHud, '准备');
      setText(dom.wavePhase, '准备迎战');
      setText(dom.waveCountdown, '—');
      dom.waveMeter.style.width = '0%';
      setText(dom.waveHint, '糖果小道已经出现动静，先布置第一道防线。');
      dom.waveDot.classList.remove('is-boss');
      setText(dom.stageWaveText, '准备迎战');
      dom.stageWaveChip.classList.remove('boss');
    } else if (game.phase === 'prep') {
      const seconds = Math.max(0, Math.ceil(game.prepTime));
      setText(dom.waveHud, game.wave === 0 ? '第 1 波' : `第 ${nextWave} 波`);
      setText(dom.wavePhase, game.wave === 0 ? '第一波正在集结' : `第 ${nextWave} 波即将来袭`);
      setText(dom.waveCountdown, `${seconds}s`);
      const progress = game.prepTime > 0 ? clamp(1 - game.prepTime / game.prepTotal, 0, 1) : 1;
      dom.waveMeter.style.width = `${progress * 100}%`;
      setText(
        dom.waveHint,
        nextWave % 5 === 0
          ? '⚠ BOSS 波即将到来 · 准备好了就点「跳过准备」。'
          : '准备时间 30 秒 · 点击右上角「跳过准备」可提前出击。'
      );
      dom.waveDot.classList.toggle('is-boss', nextWave % 5 === 0);
      setText(dom.stageWaveText, `第${nextWave}波 · ${seconds}s`);
      dom.stageWaveChip.classList.toggle('boss', nextWave % 5 === 0);
    } else if (game.phase === 'spawning') {
      const remaining = game.spawnQueue.length + game.enemies.length;
      setText(dom.waveHud, `第 ${game.wave} 波`);
      setText(dom.wavePhase, game.bossWave ? 'BOSS 正在逼近' : `第 ${game.wave} 波进攻中`);
      setText(dom.waveCountdown, `${remaining} 只`);
      const spawned = game.spawnTotal - game.spawnQueue.length;
      dom.waveMeter.style.width = `${clamp(spawned / Math.max(1, game.spawnTotal), 0, 1) * 100}%`;
      setText(
        dom.waveHint,
        game.bossWave
          ? 'Boss 血厚且会攻击路障，别让它靠近水晶。'
          : '优先击杀离基地最近的敌人，必要时补一座路障。'
      );
      dom.waveDot.classList.toggle('is-boss', game.bossWave);
      setText(dom.stageWaveText, `第${game.wave}波 · ${remaining}只`);
      dom.stageWaveChip.classList.toggle('boss', game.bossWave);
    } else if (game.phase === 'clearing') {
      setText(dom.waveHud, `第 ${game.wave} 波`);
      setText(dom.wavePhase, '正在清理战场');
      setText(dom.waveCountdown, `${game.enemies.length} 只`);
      dom.waveMeter.style.width = '100%';
      setText(dom.waveHint, '还剩几只捣蛋鬼，清空后马上准备下一波。');
      dom.waveDot.classList.remove('is-boss');
      setText(dom.stageWaveText, `第${game.wave}波 · 清理中`);
      dom.stageWaveChip.classList.remove('boss');
    } else if (game.phase === 'over') {
      setText(dom.waveHud, `第 ${game.wave} 波`);
      setText(dom.wavePhase, '本轮结束');
      setText(dom.waveCountdown, '—');
      dom.waveMeter.style.width = '0%';
      setText(dom.waveHint, '水晶已经失守，点击「再守一次」重新开始。');
      dom.waveDot.classList.remove('is-boss');
      setText(dom.stageWaveText, '本轮结束');
      dom.stageWaveChip.classList.remove('boss');
    }
  }

  function updateShopAffordability() {
    if (!dom.towerList) return;
    const cards = dom.towerList.querySelectorAll('.tower-card');
    cards.forEach((card) => {
      const type = card.dataset.type;
      const def = TOWER_DEFS[type];
      const poor = game.coins < def.cost;
      card.classList.toggle('poor', poor && game.selectedBuild !== type);
      card.classList.toggle('active', game.selectedBuild === type);
      card.setAttribute('aria-pressed', game.selectedBuild === type ? 'true' : 'false');
    });
    const upgradeButton = dom.inspector.querySelector('#upgradeBtn');
    if (upgradeButton && game.selectedTower) {
      const def = TOWER_DEFS[game.selectedTower.type];
      const tower = game.selectedTower;
      const maxed = tower.level >= def.levels.length;
      if (!maxed) {
        const cost = def.upgrades[tower.level - 1];
        upgradeButton.disabled = game.coins < cost;
      }
    }
  }

  function updateUI(force = false) {
    if (!force && performance.now() - lastUiTime < 90) return;
    lastUiTime = performance.now();
    updateHUD();
    updateShopAffordability();
    const vignette = game.baseHit > 0 ? Math.min(0.88, game.baseHit * 1.15) : 0;
    dom.stageVignette.style.opacity = vignette.toFixed(2);
  }

  // ---------------------------------------------------------------------------
  // Geometry / map
  // ---------------------------------------------------------------------------
  function createPadBlueprints() {
    pads = [];
    for (let lane = 0; lane < LANE_COUNT; lane += 1) {
      [
        { kind: 'side', frac: 0.3, side: 1 },
        { kind: 'side', frac: 0.55, side: 1 },
        { kind: 'side', frac: 0.8, side: 1 },
        { kind: 'side', frac: 0.42, side: -1 },
        { kind: 'side', frac: 0.67, side: -1 },
        { kind: 'side', frac: 0.92, side: -1 },
        { kind: 'road', frac: 0.4, side: 0 },
        { kind: 'road', frac: 0.75, side: 0 }
      ].forEach((blueprint, index) => {
        pads.push({
          lane,
          index,
          kind: blueprint.kind,
          frac: blueprint.frac,
          side: blueprint.side,
          x: 0,
          y: 0,
          radial: 0,
          tower: null,
          hover: false,
          visible: true
        });
      });
    }
  }

  function layoutMap() {
    C.x = W / 2;
    C.y = H / 2;
    baseR = clamp(Math.min(W, H) * 0.062, 34, 54);
    const compactLayout = W < 760 || H < 560;

    const edgePad = clamp(Math.min(W, H) * 0.06, 36, 52);
    const cornerInsetX = clamp(W * 0.08, 50, 110);
    const cornerInsetY = clamp(H * 0.11, 60, 100);

    lanes = LANE_TARGETS.map((target, index) => {
      let portalX;
      let portalY;
      if (target.ny === 0) {
        portalX = target.nx > 0 ? W - edgePad : edgePad;
        portalY = C.y;
      } else if (target.nx === 0) {
        portalX = C.x;
        portalY = target.ny > 0 ? H - edgePad : edgePad;
      } else {
        portalX = target.nx > 0 ? W - cornerInsetX : cornerInsetX;
        portalY = target.ny > 0 ? H - cornerInsetY : cornerInsetY;
      }

      const vx = portalX - C.x;
      const vy = portalY - C.y;
      const length = Math.hypot(vx, vy);
      const angle = Math.atan2(vy, vx);
      return {
        index,
        angle,
        dx: vx / length,
        dy: vy / length,
        length,
        portal: { x: portalX, y: portalY },
        color: PORTAL_COLORS[index % PORTAL_COLORS.length]
      };
    });

    const sideOffset = clamp(baseR * 0.98, 38, 50);
    lanes.forEach((lane, laneIndex) => {
      let inner = baseR + Math.max(56, baseR * 0.72);
      let outer = lane.length - clamp(44, 42, 58);
      if (outer < inner + 72) {
        inner = Math.max(baseR + 44, lane.length * 0.34);
        outer = Math.max(inner + 28, lane.length - 30);
      }
      const span = Math.max(26, outer - inner);
      const lanePads = pads.filter((pad) => pad.lane === laneIndex);
      lanePads.forEach((pad) => {
        pad.radial = inner + span * pad.frac;
        pad.offset = sideOffset;
        const x = C.x + lane.dx * pad.radial - lane.dy * (pad.side * pad.offset);
        const y = C.y + lane.dy * pad.radial + lane.dx * (pad.side * pad.offset);
        pad.x = clamp(x, 28, W - 28);
        pad.y = clamp(y, 32, H - 32);
        pad.hitRadius = pad.kind === 'road' ? 29 : 27;
      });
    });

    // Narrow maps use one roadside platform per sector, placed between two
    // roads. That keeps every touch target clear while retaining eight lanes.
    if (compactLayout) {
      pads.forEach((pad) => {
        if (pad.kind === 'side') pad.visible = false;
      });
      lanes.forEach((lane, laneIndex) => {
        const pad = pads.find((item) => item.lane === laneIndex && item.index === 0);
        const nextLane = lanes[(laneIndex + 1) % lanes.length];
        if (!pad || !nextLane) return;
        let bx = lane.dx + nextLane.dx;
        let by = lane.dy + nextLane.dy;
        const bisectorLength = Math.hypot(bx, by) || 1;
        bx /= bisectorLength;
        by /= bisectorLength;
        const radial = Math.min(lane.length, nextLane.length) * 0.8;
        pad.radial = radial;
        pad.offset = 0;
        pad.x = clamp(C.x + bx * radial, 30, W - 30);
        pad.y = clamp(C.y + by * radial, 34, H - 34);
        pad.visible = true;
      });
      pads.forEach((pad) => {
        if (pad.kind === 'road') {
          pad.visible = pad.index === 6 || !!pad.tower;
        } else if (pad.tower) {
          pad.visible = true;
        }
      });
      return;
    }

    // Wide maps show the full network: three roadside platforms per side and
    // two road-block platforms per main lane.
    pads.forEach((pad) => {
      pad.visible = true;
    });
  }

  function buildDecor() {
    decor = [];
    const kinds = ['flower', 'tuft', 'bush', 'rock', 'mushroom', 'tree', 'lollipop'];
    const margin = 30;
    let attempts = 0;
    while (decor.length < 30 && attempts < 4200) {
      attempts += 1;
      const x = rand(margin, W - margin);
      const y = rand(margin, H - margin);
      const centerDist = dist(x, y, C.x, C.y);
      if (centerDist < baseR + 92) continue;

      let roadClear = true;
      for (const lane of lanes) {
        const px = x - C.x;
        const py = y - C.y;
        const projection = px * lane.dx + py * lane.dy;
        if (projection < -30 || projection > lane.length + 36) continue;
        const perp = Math.abs(px * -lane.dy + py * lane.dx);
        if (perp < 46) {
          roadClear = false;
          break;
        }
      }
      if (!roadClear) continue;

      let padClear = true;
      for (const pad of pads) {
        if (!pad.visible) continue;
        if (dist(x, y, pad.x, pad.y) < 40) {
          padClear = false;
          break;
        }
      }
      if (!padClear) continue;

      let decorClear = true;
      for (const item of decor) {
        if (dist(x, y, item.x, item.y) < 28) {
          decorClear = false;
          break;
        }
      }
      if (!decorClear) continue;

      const roll = Math.random();
      let kind;
      if (roll < 0.25) kind = 'flower';
      else if (roll < 0.46) kind = 'tuft';
      else if (roll < 0.61) kind = 'bush';
      else if (roll < 0.72) kind = 'rock';
      else if (roll < 0.83) kind = 'mushroom';
      else if (roll < 0.94) kind = 'tree';
      else kind = 'lollipop';

      decor.push({
        x,
        y,
        kind: kinds.includes(kind) ? kind : 'flower',
        scale: rand(0.72, 1.22),
        rotation: rand(-0.18, 0.18),
        phase: rand(0, TAU),
        shade: rand(0, 1)
      });
    }
  }

  function resizeCanvas() {
    W = Math.max(320, stageShell.clientWidth);
    H = Math.max(320, stageShell.clientHeight);
    DPR = Math.min(window.devicePixelRatio || 1, 2);
    canvas.width = Math.floor(W * DPR);
    canvas.height = Math.floor(H * DPR);
    ctx.setTransform(DPR, 0, 0, DPR, 0, 0);
    layoutMap();
    buildDecor();
    buildBackgroundCache();
  }

  // ---------------------------------------------------------------------------
  // Static background artwork
  // ---------------------------------------------------------------------------
  function roundedRectPath(g, x, y, w, h, r) {
    const radius = Math.min(r, w / 2, h / 2);
    g.beginPath();
    g.moveTo(x + radius, y);
    g.lineTo(x + w - radius, y);
    g.quadraticCurveTo(x + w, y, x + w, y + radius);
    g.lineTo(x + w, y + h - radius);
    g.quadraticCurveTo(x + w, y + h, x + w - radius, y + h);
    g.lineTo(x + radius, y + h);
    g.quadraticCurveTo(x, y + h, x, y + h - radius);
    g.lineTo(x, y + radius);
    g.quadraticCurveTo(x, y, x + radius, y);
    g.closePath();
  }

  function drawEllipse(g, x, y, rx, ry, fillStyle) {
    g.beginPath();
    g.ellipse(x, y, rx, ry, 0, 0, TAU);
    if (fillStyle) {
      g.fillStyle = fillStyle;
      g.fill();
    }
  }

  function buildBackgroundCache() {
    bgCanvas = document.createElement('canvas');
    bgCanvas.width = Math.floor(W * DPR);
    bgCanvas.height = Math.floor(H * DPR);
    const g = bgCanvas.getContext('2d');
    g.setTransform(DPR, 0, 0, DPR, 0, 0);
    drawBackgroundScene(g);
  }

  function drawBackgroundScene(g) {
    // Soft ocean-like outer field.
    const waterGrad = g.createLinearGradient(0, 0, W, H);
    waterGrad.addColorStop(0, '#7ed9ea');
    waterGrad.addColorStop(0.52, '#8be4de');
    waterGrad.addColorStop(1, '#b5ead7');
    g.fillStyle = waterGrad;
    g.fillRect(0, 0, W, H);

    // Water ripples and bubbles.
    g.strokeStyle = 'rgba(255,255,255,0.26)';
    g.lineWidth = 2;
    for (let i = 0; i < 9; i += 1) {
      const y = 8 + i * 26;
      g.beginPath();
      g.arc(W * 0.15 + Math.sin(i * 1.7) * 26, y, 12 + (i % 3) * 8, 0.15, Math.PI - 0.3);
      g.stroke();
      g.beginPath();
      g.arc(W * 0.83 + Math.cos(i * 2.1) * 36, H - y, 10 + (i % 4) * 7, Math.PI + 0.2, TAU - 0.3);
      g.stroke();
    }
    g.fillStyle = 'rgba(255,255,255,0.24)';
    for (let i = 0; i < 22; i += 1) {
      const x = (Math.sin(i * 13.37) * 0.5 + 0.5) * W;
      const y = (Math.cos(i * 8.91) * 0.5 + 0.5) * H;
      if (Math.min(x, y, W - x, H - y) > 26) continue;
      g.beginPath();
      g.arc(x, y, 1.5 + (i % 3), 0, TAU);
      g.fill();
    }

    // Island base with a warm sand rim and dark cartoon outline.
    const inset = clamp(Math.min(W, H) * 0.018, 8, 16);
    const islandX = inset;
    const islandY = inset;
    const islandW = W - inset * 2;
    const islandH = H - inset * 2;
    const islandR = clamp(Math.min(W, H) * 0.058, 24, 48);

    g.save();
    g.shadowColor = 'rgba(34, 74, 81, 0.18)';
    g.shadowBlur = 18;
    g.shadowOffsetY = 8;
    roundedRectPath(g, islandX, islandY, islandW, islandH, islandR);
    g.fillStyle = '#f1d9a1';
    g.fill();
    g.restore();
    roundedRectPath(g, islandX, islandY, islandW, islandH, islandR);
    g.lineWidth = 4;
    g.strokeStyle = '#6a5b55';
    g.stroke();

    const grassX = islandX + 9;
    const grassY = islandY + 9;
    const grassW = islandW - 18;
    const grassH = islandH - 18;

    g.save();
    roundedRectPath(g, grassX, grassY, grassW, grassH, Math.max(16, islandR - 8));
    g.clip();

    const grassGrad = g.createRadialGradient(C.x, C.y - 40, 20, C.x, C.y, Math.max(W, H) * 0.7);
    grassGrad.addColorStop(0, '#b9ec8a');
    grassGrad.addColorStop(0.55, '#93d76d');
    grassGrad.addColorStop(1, '#76c45b');
    g.fillStyle = grassGrad;
    g.fillRect(grassX, grassY, grassW, grassH);

    // Broad lighter patches.
    const patches = [
      [0.13, 0.23, 0.13, '#b4eb8d'],
      [0.86, 0.22, 0.11, '#afe989'],
      [0.16, 0.82, 0.16, '#a9e883'],
      [0.84, 0.78, 0.14, '#b4eb8b'],
      [0.5, 0.09, 0.18, '#b3ed8c'],
      [0.5, 0.92, 0.17, '#a8e47f']
    ];
    g.fillStyle = 'rgba(255,255,255,0.10)';
    patches.forEach(([px, py, size]) => {
      g.beginPath();
      g.ellipse(W * px, H * py, Math.min(W, H) * size, Math.min(W, H) * size * 0.48, 0, 0, TAU);
      g.fill();
    });

    // Grass speckles and blades.
    for (let i = 0; i < 150; i += 1) {
      const x = grassX + ((Math.sin(i * 12.9898) * 43758.5453) % 1 + 1) % 1 * grassW;
      const y = grassY + ((Math.sin(i * 78.233) * 12345.678) % 1 + 1) % 1 * grassH;
      const len = 2 + (i % 4);
      g.strokeStyle = i % 3 === 0 ? 'rgba(63, 138, 62, 0.24)' : 'rgba(238, 255, 199, 0.28)';
      g.lineWidth = 1.2;
      g.beginPath();
      g.moveTo(x, y);
      g.lineTo(x + (i % 2 ? 1.5 : -1.5), y - len);
      g.stroke();
    }

    // Draw the eight candy roads.
    lanes.forEach((lane) => drawLaneOnBackground(g, lane));

    // Decorative plants and candy props.
    decor.forEach((item) => drawDecor(g, item));

    // Little path-side candy sprinkles are painted in drawLaneOnBackground.

    // Edge shading inside the island for depth.
    const edgeShade = g.createRadialGradient(C.x, C.y, Math.min(W, H) * 0.24, C.x, C.y, Math.max(W, H) * 0.7);
    edgeShade.addColorStop(0, 'rgba(46, 104, 70, 0)');
    edgeShade.addColorStop(1, 'rgba(46, 104, 70, 0.12)');
    g.fillStyle = edgeShade;
    g.fillRect(grassX, grassY, grassW, grassH);

    g.restore();

    // Sand rim pebbles.
    g.fillStyle = 'rgba(255, 250, 222, 0.64)';
    for (let i = 0; i < 40; i += 1) {
      const side = i % 4;
      let x;
      let y;
      if (side === 0) {
        x = rand(islandX + 20, islandX + islandW - 20);
        y = islandY + rand(3, 9);
      } else if (side === 1) {
        x = W - islandX - rand(3, 9);
        y = islandY + rand(20, islandH - 20);
      } else if (side === 2) {
        x = rand(islandX + 20, islandX + islandW - 20);
        y = H - islandY - rand(3, 9);
      } else {
        x = islandX + rand(3, 9);
        y = islandY + rand(20, islandH - 20);
      }
      drawEllipse(g, x, y, rand(1.2, 2.5), rand(0.8, 1.4), 'rgba(255,250,222,0.56)');
    }
  }

  function drawLaneOnBackground(g, lane) {
    const roadW = clamp(baseR * 0.72, 28, 39);
    const startR = baseR * 0.36;
    const endR = lane.length + 7;
    const sx = C.x + lane.dx * startR;
    const sy = C.y + lane.dy * startR;
    const ex = C.x + lane.dx * endR;
    const ey = C.y + lane.dy * endR;

    g.save();
    g.lineCap = 'round';

    // Soft drop shadow on grass.
    g.strokeStyle = 'rgba(66, 77, 58, 0.19)';
    g.lineWidth = roadW + 10;
    g.beginPath();
    g.moveTo(sx, sy + 4);
    g.lineTo(ex, ey + 4);
    g.stroke();

    // Chocolate outline.
    g.strokeStyle = '#6d5351';
    g.lineWidth = roadW + 8;
    g.beginPath();
    g.moveTo(sx, sy);
    g.lineTo(ex, ey);
    g.stroke();

    // Warm sandy road surface.
    const roadGrad = g.createLinearGradient(sx, sy, ex, ey);
    roadGrad.addColorStop(0, '#f8e7ba');
    roadGrad.addColorStop(0.55, '#f7dda5');
    roadGrad.addColorStop(1, '#f1cf92');
    g.strokeStyle = roadGrad;
    g.lineWidth = roadW;
    g.beginPath();
    g.moveTo(sx, sy);
    g.lineTo(ex, ey);
    g.stroke();

    // Cream center strip.
    g.strokeStyle = 'rgba(255, 248, 220, 0.48)';
    g.lineWidth = roadW * 0.35;
    g.beginPath();
    g.moveTo(sx + lane.dx * 12, sy + lane.dy * 12);
    g.lineTo(ex - lane.dx * 8, ey - lane.dy * 8);
    g.stroke();

    // Dotted frosting edges.
    const perpX = -lane.dy;
    const perpY = lane.dx;
    [1, -1].forEach((side) => {
      g.setLineDash([3, 15]);
      g.lineDashOffset = lane.index * 7;
      g.lineWidth = 3;
      g.strokeStyle = side === 1 ? 'rgba(255,255,255,0.56)' : 'rgba(255,255,255,0.38)';
      g.beginPath();
      g.moveTo(
        sx + perpX * side * (roadW * 0.39),
        sy + perpY * side * (roadW * 0.39)
      );
      g.lineTo(
        ex + perpX * side * (roadW * 0.39),
        ey + perpY * side * (roadW * 0.39)
      );
      g.stroke();
    });
    g.setLineDash([]);

    // Candy sprinkles and little pebbles along the lane.
    const sprinkleColors = ['#ff96b4', '#8ae0c4', '#a794ff', '#ffd169'];
    for (let i = 0; i < 11; i += 1) {
      const t = (i + 0.5) / 11;
      const rr = lerp(baseR + 32, lane.length - 14, t);
      const side = i % 2 === 0 ? 1 : -1;
      const off = side * roadW * rand(0.24, 0.38);
      const x = C.x + lane.dx * rr + perpX * off;
      const y = C.y + lane.dy * rr + perpY * off;
      g.save();
      g.translate(x, y);
      g.rotate(lane.angle + rand(-0.7, 0.7));
      g.strokeStyle = sprinkleColors[i % sprinkleColors.length];
      g.lineWidth = 2.2;
      g.lineCap = 'round';
      g.beginPath();
      g.moveTo(-3, 0);
      g.lineTo(3, 0);
      g.stroke();
      g.restore();
    }

    // Arrows pointing toward the center.
    g.strokeStyle = 'rgba(255,255,255,0.50)';
    g.lineWidth = 3;
    g.lineCap = 'round';
    g.lineJoin = 'round';
    const arrowSpacing = 64;
    for (let rr = baseR + 78; rr < lane.length - 48; rr += arrowSpacing) {
      const ax = C.x + lane.dx * rr;
      const ay = C.y + lane.dy * rr;
      const wing = 7;
      const tip = 8;
      g.beginPath();
      g.moveTo(ax - perpX * wing + lane.dx * tip, ay - perpY * wing + lane.dy * tip);
      g.lineTo(ax - lane.dx * 3, ay - lane.dy * 3);
      g.lineTo(ax + perpX * wing + lane.dx * tip, ay + perpY * wing + lane.dy * tip);
      g.stroke();
    }

    g.restore();
  }

  function drawDecor(g, d) {
    g.save();
    g.translate(d.x, d.y);
    g.rotate(d.rotation);
    g.scale(d.scale, d.scale);
    if (d.kind === 'flower') drawFlowerProp(g, d);
    else if (d.kind === 'tuft') drawTuftProp(g, d);
    else if (d.kind === 'bush') drawBushProp(g, d);
    else if (d.kind === 'rock') drawRockProp(g, d);
    else if (d.kind === 'mushroom') drawMushroomProp(g, d);
    else if (d.kind === 'lollipop') drawLollipopProp(g, d);
    else drawTreeProp(g, d);
    g.restore();
  }

  function drawFlowerProp(g, d) {
    const palette = ['#ffe27a', '#ff9eb9', '#b9a4ff', '#fff9e9'];
    const color = palette[Math.floor(d.shade * palette.length) % palette.length];
    g.strokeStyle = '#568d48';
    g.lineWidth = 1.5;
    g.beginPath();
    g.moveTo(0, 1);
    g.quadraticCurveTo(3, -6, 1, -10);
    g.stroke();
    for (let i = 0; i < 5; i += 1) {
      const a = (i / 5) * TAU;
      drawEllipse(g, 1 + Math.cos(a) * 4, -11 + Math.sin(a) * 4, 3.4, 2.5, color);
    }
    drawEllipse(g, 1, -11, 2.2, 2.2, '#f3a43a');
  }

  function drawTuftProp(g) {
    g.strokeStyle = 'rgba(58, 126, 52, 0.72)';
    g.lineWidth = 2;
    g.lineCap = 'round';
    for (let i = 0; i < 5; i += 1) {
      g.beginPath();
      g.moveTo(i * 2 - 4, 1);
      g.quadraticCurveTo(i * 2 - 5, -6 - (i % 2) * 3, i * 2 - 7 + (i % 3), -10 - (i % 3) * 2);
      g.stroke();
    }
  }

  function drawBushProp(g, d) {
    drawEllipse(g, 2, 3, 19, 6, 'rgba(62, 91, 46, 0.16)');
    const c1 = d.shade > 0.5 ? '#74c75f' : '#67bb57';
    const circles = [
      [-10, -7, 10],
      [0, -12, 12],
      [11, -7, 9],
      [2, -3, 13]
    ];
    g.fillStyle = c1;
    g.strokeStyle = '#426d3c';
    g.lineWidth = 2.4;
    circles.forEach(([x, y, r]) => {
      g.beginPath();
      g.arc(x, y, r, 0, TAU);
      g.fill();
      g.stroke();
    });
    g.fillStyle = 'rgba(223,255,177,0.40)';
    circles.slice(0, 3).forEach(([x, y, r]) => {
      g.beginPath();
      g.arc(x - r * 0.28, y - r * 0.32, r * 0.35, 0, TAU);
      g.fill();
    });
  }

  function drawRockProp(g) {
    drawEllipse(g, 2, 3, 13, 5, 'rgba(63, 84, 60, 0.18)');
    g.fillStyle = '#adc0b2';
    g.strokeStyle = '#647a70';
    g.lineWidth = 2.2;
    g.beginPath();
    g.moveTo(-11, 2);
    g.quadraticCurveTo(-13, -7, -5, -11);
    g.quadraticCurveTo(3, -14, 10, -7);
    g.quadraticCurveTo(15, -1, 9, 3);
    g.quadraticCurveTo(1, 6, -11, 2);
    g.fill();
    g.stroke();
    g.strokeStyle = 'rgba(238,255,244,0.45)';
    g.lineWidth = 2;
    g.beginPath();
    g.moveTo(-5, -6);
    g.lineTo(1, -8);
    g.stroke();
  }

  function drawMushroomProp(g, d) {
    drawEllipse(g, 1, 2, 11, 4, 'rgba(61, 83, 48, 0.16)');
    g.fillStyle = '#fff0d2';
    g.strokeStyle = '#6e5b49';
    g.lineWidth = 2;
    g.beginPath();
    roundedRectPath(g, -3, -8, 7, 11, 3);
    g.fill();
    g.stroke();
    g.fillStyle = d.shade > 0.5 ? '#ff7c82' : '#ff9a72';
    g.beginPath();
    g.ellipse(0, -10, 11, 7, 0, Math.PI, TAU);
    g.closePath();
    g.fill();
    g.stroke();
    g.fillStyle = 'rgba(255,245,210,0.86)';
    drawEllipse(g, -4, -12, 1.7, 1.2);
    drawEllipse(g, 4, -10.5, 1.3, 1);
    drawEllipse(g, 0, -13.5, 1.1, 0.8);
  }

  function drawTreeProp(g, d) {
    drawEllipse(g, 4, 4, 25, 8, 'rgba(53, 88, 48, 0.18)');
    g.fillStyle = '#9d6647';
    g.strokeStyle = '#66503e';
    g.lineWidth = 2.2;
    g.beginPath();
    roundedRectPath(g, -4, -26, 8, 31, 3);
    g.fill();
    g.stroke();
    g.fillStyle = d.shade > 0.5 ? '#79c960' : '#68b959';
    g.strokeStyle = '#3e6d3b';
    g.lineWidth = 2.4;
    const crown = [
      [-13, -29, 14],
      [5, -36, 16],
      [17, -26, 12],
      [0, -24, 17]
    ];
    crown.forEach(([x, y, r]) => {
      g.beginPath();
      g.arc(x, y, r, 0, TAU);
      g.fill();
      g.stroke();
    });
    g.fillStyle = 'rgba(233,255,180,0.45)';
    g.beginPath();
    g.ellipse(-5, -40, 7, 4, -0.4, 0, TAU);
    g.fill();
    g.fillStyle = '#ffd879';
    g.beginPath();
    g.arc(-14, -24, 2, 0, TAU);
    g.fill();
    g.fillStyle = '#ff9b9c';
    g.beginPath();
    g.arc(16, -33, 1.7, 0, TAU);
    g.fill();
  }

  function drawLollipopProp(g, d) {
    drawEllipse(g, 2, 4, 10, 4, 'rgba(53, 88, 48, 0.16)');
    g.strokeStyle = '#f8f0dd';
    g.lineWidth = 3.2;
    g.beginPath();
    g.moveTo(0, 2);
    g.lineTo(0, -20);
    g.stroke();
    g.strokeStyle = '#e4d4bd';
    g.lineWidth = 2;
    g.beginPath();
    g.moveTo(0, -4);
    g.lineTo(0, -18);
    g.stroke();
    const grad = g.createRadialGradient(-3, -28, 2, 0, -24, 13);
    grad.addColorStop(0, '#ffe4ec');
    grad.addColorStop(0.45, d.shade > 0.5 ? '#ff9fc3' : '#ffc981');
    grad.addColorStop(1, d.shade > 0.5 ? '#ef5e9b' : '#ff9d58');
    g.fillStyle = grad;
    g.strokeStyle = '#6f5358';
    g.lineWidth = 2.3;
    g.beginPath();
    g.arc(0, -25, 11, 0, TAU);
    g.fill();
    g.stroke();
    g.strokeStyle = 'rgba(255,255,255,0.72)';
    g.lineWidth = 1.9;
    g.beginPath();
    g.arc(0, -25, 6, -0.7, 2.5);
    g.stroke();
    g.beginPath();
    g.arc(0, -25, 3, 2.3, 5.2);
    g.stroke();
  }

  // ---------------------------------------------------------------------------
  // Dynamic artwork: portals, base, pads
  // ---------------------------------------------------------------------------
  function drawPortal(g, lane, time) {
    const pulse = 0.5 + Math.sin(time * 2.3 + lane.index * 1.7) * 0.5;
    const { x, y } = lane.portal;
    const radius = clamp(baseR * 0.3, 17, 24);

    g.save();
    g.translate(x, y);

    g.fillStyle = 'rgba(59, 42, 70, 0.18)';
    g.beginPath();
    g.ellipse(0, radius * 0.75, radius * 1.35, radius * 0.45, 0, 0, TAU);
    g.fill();

    g.strokeStyle = `${lane.color}99`;
    g.lineWidth = 3;
    g.setLineDash([4, 6]);
    g.lineDashOffset = -time * 18;
    g.beginPath();
    g.arc(0, 0, radius + 6 + pulse * 3, 0, TAU);
    g.stroke();
    g.setLineDash([]);

    g.fillStyle = '#4f3b6b';
    g.strokeStyle = '#3b2b4b';
    g.lineWidth = 3;
    g.beginPath();
    g.arc(0, 0, radius, 0, TAU);
    g.fill();
    g.stroke();

    const portalGrad = g.createRadialGradient(-radius * 0.25, -radius * 0.28, 2, 0, 0, radius);
    portalGrad.addColorStop(0, '#fff6df');
    portalGrad.addColorStop(0.25, lane.color);
    portalGrad.addColorStop(0.65, '#8d6dd4');
    portalGrad.addColorStop(1, '#3b2b57');
    g.fillStyle = portalGrad;
    g.beginPath();
    g.arc(0, 0, radius - 4, 0, TAU);
    g.fill();

    g.strokeStyle = 'rgba(255,255,255,0.74)';
    g.lineWidth = 2;
    g.beginPath();
    g.arc(0, 0, radius * 0.64, time * 1.7, time * 1.7 + Math.PI * 1.2);
    g.stroke();
    g.strokeStyle = 'rgba(255,255,255,0.4)';
    g.lineWidth = 1.5;
    g.beginPath();
    g.arc(0, 0, radius * 0.38, -time * 2.1, -time * 2.1 + Math.PI * 1.5);
    g.stroke();

    // Little candy posts framing the gate.
    const perpX = -lane.dy;
    const perpY = lane.dx;
    [1, -1].forEach((side) => {
      const px = perpX * side * (radius + 10);
      const py = perpY * side * (radius + 10);
      g.save();
      g.translate(px, py);
      g.strokeStyle = '#6e5354';
      g.lineWidth = 2;
      g.strokeStyle = '#f6efdd';
      g.lineWidth = 3;
      g.beginPath();
      g.moveTo(0, 10);
      g.lineTo(0, -9);
      g.stroke();
      g.fillStyle = side === 1 ? lane.color : '#ffdb8a';
      g.strokeStyle = '#4c3b52';
      g.lineWidth = 2;
      g.beginPath();
      g.arc(0, -14, 7, 0, TAU);
      g.fill();
      g.stroke();
      g.restore();
    });

    // Sparkle motes.
    for (let i = 0; i < 3; i += 1) {
      const a = time * 1.2 + i * 2.1 + lane.index;
      const rr = radius + 12 + Math.sin(time * 1.8 + i) * 4;
      g.fillStyle = 'rgba(255,247,206,0.82)';
      g.beginPath();
      g.arc(Math.cos(a) * rr, Math.sin(a) * rr * 0.72, 1.8, 0, TAU);
      g.fill();
    }

    g.restore();
  }

  function drawBase(g, time) {
    const x = C.x;
    const y = C.y;
    const bob = Math.sin(time * 1.9) * 2.2;
    const healthRatio = clamp(game.lives / game.maxLives, 0, 1);

    g.save();
    g.translate(x, y);

    // Ground shadow and a ring of little candy pebbles.
    g.fillStyle = 'rgba(56, 76, 48, 0.18)';
    g.beginPath();
    g.ellipse(4, baseR * 0.36 + 5, baseR * 1.22, baseR * 0.48, 0, 0, TAU);
    g.fill();

    // Frosting base.
    g.strokeStyle = '#5a4552';
    g.lineWidth = 3.4;
    g.fillStyle = '#ffd7e6';
    g.beginPath();
    g.arc(0, 0, baseR + 4, 0, TAU);
    g.fill();
    g.stroke();

    // Scalloped dollops around the rim.
    for (let i = 0; i < 12; i += 1) {
      const a = (i / 12) * TAU + 0.18;
      const rx = Math.cos(a) * (baseR - 3);
      const ry = Math.sin(a) * (baseR - 3);
      g.fillStyle = i % 2 === 0 ? '#fff2d0' : '#ffc5dc';
      g.strokeStyle = '#6a4c5a';
      g.lineWidth = 2.1;
      g.beginPath();
      g.arc(rx, ry, baseR * 0.18, 0, TAU);
      g.fill();
      g.stroke();
    }

    // Cake-like center tier.
    const cakeGrad = g.createRadialGradient(-baseR * 0.2, -baseR * 0.25, 3, 0, 0, baseR * 0.74);
    cakeGrad.addColorStop(0, '#fff7dc');
    cakeGrad.addColorStop(0.7, '#ffe6b7');
    cakeGrad.addColorStop(1, '#f5c989');
    g.fillStyle = cakeGrad;
    g.strokeStyle = '#6a4c5a';
    g.lineWidth = 3;
    g.beginPath();
    g.arc(0, 0, baseR * 0.72, 0, TAU);
    g.fill();
    g.stroke();

    // Little flags at either side.
    [-1, 1].forEach((side) => {
      const fx = side * (baseR * 0.82);
      const fy = -baseR * 0.2;
      g.save();
      g.translate(fx, fy);
      g.strokeStyle = '#f8f0dd';
      g.lineWidth = 2.4;
      g.beginPath();
      g.moveTo(0, baseR * 0.52);
      g.lineTo(0, -baseR * 0.42);
      g.stroke();
      g.fillStyle = side === 1 ? '#ff8fad' : '#8eddbe';
      g.strokeStyle = '#5b4754';
      g.lineWidth = 1.7;
      g.beginPath();
      g.moveTo(0, -baseR * 0.43);
      g.quadraticCurveTo(baseR * 0.24, -baseR * 0.36, baseR * 0.34, -baseR * 0.25);
      g.lineTo(0, -baseR * 0.12);
      g.closePath();
      g.fill();
      g.stroke();
      g.restore();
    });

    // Crystal dais.
    g.fillStyle = '#fff2bd';
    g.strokeStyle = '#6a4c5a';
    g.lineWidth = 2.7;
    g.beginPath();
    g.ellipse(0, -baseR * 0.1, baseR * 0.52, baseR * 0.25, 0, 0, TAU);
    g.fill();
    g.stroke();

    // The crystal itself.
    const cy = -baseR * 0.7 + bob;
    g.save();
    g.translate(0, cy);
    g.shadowColor = 'rgba(143, 240, 255, 0.62)';
    g.shadowBlur = 22;
    const crystalGrad = g.createLinearGradient(-18, -18, 18, 26);
