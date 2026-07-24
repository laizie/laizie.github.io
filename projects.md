---
layout: page
title: Projects
description: Things I've built, shipped, and maintain.
---

<style>
/* ════════════════════════════════════════════════════════════
   LIGHT MODE  (default)
   ════════════════════════════════════════════════════════════ */
.projects-intro { color: #222 !important; font-size:1rem; margin:-1rem 0 2.5rem; border-left:3px solid #22c55e; padding-left:.85rem; }

.projects-grid  { display:grid; grid-template-columns:repeat(auto-fill,minmax(300px,1fr)); gap:1.75rem; }

.project-card   { background:#f4f5f7; border:1px solid #d0d5dd; border-radius:10px; padding:1.5rem 1.5rem 1.25rem; display:flex; flex-direction:column; gap:.9rem; position:relative; overflow:hidden; box-shadow:0 2px 6px rgba(0,0,0,.08); transition:transform .18s ease,box-shadow .18s ease; }
.project-card:hover { transform:translateY(-3px); box-shadow:0 8px 24px rgba(0,0,0,.14); }
.project-card::before { content:''; position:absolute; top:0; left:0; right:0; height:4px; border-radius:10px 10px 0 0; }

.card-lazee::before      { background:#22c55e; }
.card-packseats::before  { background:#cc0000; }
.card-studeo::before     { background:#f59e0b; }
.card-daycounter::before { background:#6366f1; }
.card-fluidsim::before   { background:#06b6d4; }
.card-gameoflife::before { background:#f43f5e; }

.project-card-header { display:flex; align-items:center; justify-content:space-between; gap:.5rem; }

.project-title  { margin:0 !important; font-size:1.15rem; font-weight:700; line-height:1.2; color:#0d0d0d !important; }
.project-title-link { color:inherit !important; text-decoration:none !important; }
/* Stretched link: makes the whole card clickable while keeping the action buttons usable */
.project-title-link::after { content:''; position:absolute; inset:0; z-index:1; }
.project-card { cursor:pointer; }

.project-badge  { font-size:.68rem; font-weight:700; letter-spacing:.06em; text-transform:uppercase; padding:.22rem .6rem; border-radius:999px; white-space:nowrap; flex-shrink:0; }
.badge-live { background:#dcfce7; color:#15803d; border:1px solid #bbf7d0; }
.badge-wip  { background:#fef9c3; color:#a16207; border:1px solid #fde68a; }
.badge-done { background:#ede9fe; color:#5b21b6; border:1px solid #ddd6fe; }

.project-date   { font-size:.78rem; color:#444 !important; margin:-.4rem 0 0; display:flex; align-items:center; gap:.35rem; }
.project-date::before { content:''; display:inline-block; width:6px; height:6px; border-radius:50%; flex-shrink:0; }
.card-lazee      .project-date::before { background:#22c55e; }
.card-packseats  .project-date::before { background:#cc0000; }
.card-studeo     .project-date::before { background:#f59e0b; }
.card-daycounter .project-date::before { background:#6366f1; }
.card-fluidsim   .project-date::before { background:#06b6d4; }
.card-gameoflife .project-date::before { background:#f43f5e; }

.project-desc   { font-size:.9rem; line-height:1.6; color:#1a1a1a !important; margin:0; flex:1; }

.project-tags   { display:flex; flex-wrap:wrap; gap:.35rem; }
.project-tag    { font-size:.7rem; padding:.18rem .5rem; background:#e8eaed; border:1px solid #c8cdd4; border-radius:4px; font-family:ui-monospace,monospace; color:#1a1a1a !important; }

.project-links  { display:flex; gap:.6rem; flex-wrap:wrap; padding-top:.75rem; border-top:1px solid #d0d5dd; margin-top:.25rem; }
.project-link   { font-size:.8rem; font-weight:600; padding:.3rem .85rem; border-radius:6px; text-decoration:none !important; transition:opacity .15s,transform .1s; display:inline-flex; align-items:center; gap:.3rem; position:relative; z-index:2; }
.project-link:hover { opacity:.8; transform:translateY(-1px); }
.link-appstore  { background:#22c55e; color:#fff !important; }
.link-download  { background:#f59e0b; color:#fff !important; }
.link-github    { background:#1e293b; color:#fff !important; }

/* ════════════════════════════════════════════════════════════
   DARK MODE  — OS preference (no explicit user choice yet)
              + body.dark-mode (user chose dark, or JS synced)
   ════════════════════════════════════════════════════════════ */
@media (prefers-color-scheme: dark) {
  .project-card    { background:rgba(255,255,255,.05); border-color:rgba(255,255,255,.1); box-shadow:0 1px 6px rgba(0,0,0,.4); }
  .project-card:hover { box-shadow:0 8px 28px rgba(0,0,0,.55); }
  .project-title   { color:#e2e8f0 !important; }
  .project-desc    { color:#b0bec5 !important; }
  .project-date    { color:rgba(255,255,255,.45) !important; }
  .project-tag     { background:rgba(255,255,255,.06); border-color:rgba(255,255,255,.14); color:#94a3b8 !important; }
  .project-links   { border-top-color:rgba(255,255,255,.1); }
  .projects-intro  { color:rgba(255,255,255,.5) !important; }
  .badge-live { background:rgba(34,197,94,.15);  color:#86efac; border-color:rgba(34,197,94,.3);  }
  .badge-wip  { background:rgba(245,158,11,.15); color:#fcd34d; border-color:rgba(245,158,11,.3); }
  .badge-done { background:rgba(99,102,241,.15); color:#a5b4fc; border-color:rgba(99,102,241,.3); }
  .link-github { background:rgba(255,255,255,.12); color:#e2e8f0 !important; }
}

body.dark-mode .project-card    { background:rgba(255,255,255,.05); border-color:rgba(255,255,255,.1); box-shadow:0 1px 6px rgba(0,0,0,.4); }
body.dark-mode .project-card:hover { box-shadow:0 8px 28px rgba(0,0,0,.55); }
body.dark-mode .project-title   { color:#e2e8f0 !important; }
body.dark-mode .project-desc    { color:#b0bec5 !important; }
body.dark-mode .project-date    { color:rgba(255,255,255,.45) !important; }
body.dark-mode .project-tag     { background:rgba(255,255,255,.06); border-color:rgba(255,255,255,.14); color:#94a3b8 !important; }
body.dark-mode .project-links   { border-top-color:rgba(255,255,255,.1); }
body.dark-mode .projects-intro  { color:rgba(255,255,255,.5) !important; }
body.dark-mode .badge-live { background:rgba(34,197,94,.15);  color:#86efac; border-color:rgba(34,197,94,.3);  }
body.dark-mode .badge-wip  { background:rgba(245,158,11,.15); color:#fcd34d; border-color:rgba(245,158,11,.3); }
body.dark-mode .badge-done { background:rgba(99,102,241,.15); color:#a5b4fc; border-color:rgba(99,102,241,.3); }
body.dark-mode .link-github { background:rgba(255,255,255,.12); color:#e2e8f0 !important; }

/* ════════════════════════════════════════════════════════════
   LIGHT OVERRIDE — user explicitly chose light via toggle
   while OS is still in dark mode
   ════════════════════════════════════════════════════════════ */
body.light-mode .project-card   { background:#f4f5f7; border-color:#d0d5dd; box-shadow:0 2px 6px rgba(0,0,0,.08); }
body.light-mode .project-card:hover { box-shadow:0 8px 24px rgba(0,0,0,.14); }
body.light-mode .project-title  { color:#0d0d0d !important; }
body.light-mode .project-desc   { color:#1a1a1a !important; }
body.light-mode .project-date   { color:#444 !important; }
body.light-mode .project-tag    { background:#e8eaed; border-color:#c8cdd4; color:#1a1a1a !important; }
body.light-mode .project-links  { border-top-color:#d0d5dd; }
body.light-mode .projects-intro { color:#222 !important; }
body.light-mode .badge-live { background:#dcfce7; color:#15803d; border-color:#bbf7d0; }
body.light-mode .badge-wip  { background:#fef9c3; color:#a16207; border-color:#fde68a; }
body.light-mode .badge-done { background:#ede9fe; color:#5b21b6; border-color:#ddd6fe; }
body.light-mode .link-github { background:#1e293b; color:#fff !important; }
</style>

<p class="projects-intro">A collection of personal projects I've built and maintain.</p>

<div class="projects-grid">

  <div class="project-card card-lazee">
    <div class="project-card-header">
      <h3 class="project-title"><a class="project-title-link" href="{{ '/projects/lazee/' | relative_url }}">Lazee</a></h3>
      <span class="project-badge badge-live">Live</span>
    </div>
    <p class="project-date">Nov 2025 – Present</p>
    <p class="project-desc">
      iOS strength training tracker for lifters who want a simple, fast way to log workouts.
      Built solo, published and actively maintained on the App Store.
    </p>
    <div class="project-tags">
      <span class="project-tag">Swift</span>
      <span class="project-tag">SwiftUI</span>
      <span class="project-tag">Xcode</span>
      <span class="project-tag">iOS</span>
    </div>
    <div class="project-links">
      <a class="project-link link-appstore" href="https://apps.apple.com/us/app/lazee/id6772380948" target="_blank">
        ↗ App Store
      </a>
    </div>
  </div>

  <div class="project-card card-packseats">
    <div class="project-card-header">
      <h3 class="project-title"><a class="project-title-link" href="{{ '/projects/packseats/' | relative_url }}">PackSeats</a></h3>
      <span class="project-badge badge-live">Live</span>
    </div>
    <p class="project-date">Jul 2026 – Present</p>
    <p class="project-desc">
      Self-hosted watcher that pings my phone the second a seat opens in a full NC State
      class, plus a conflict-aware schedule planner and an opt-in Telegram bot for friends.
      Polls the public catalog only, runs 24/7 on a free VM at $0.
    </p>
    <div class="project-tags">
      <span class="project-tag">Python</span>
      <span class="project-tag">Flask</span>
      <span class="project-tag">BeautifulSoup</span>
      <span class="project-tag">Telegram Bot</span>
      <span class="project-tag">systemd</span>
    </div>
    <div class="project-links">
      <a class="project-link link-github" href="https://github.com/laizie/packseats" target="_blank">
        ↗ GitHub
      </a>
    </div>
  </div>

  <div class="project-card card-studeo">
    <div class="project-card-header">
      <h3 class="project-title"><a class="project-title-link" href="{{ '/projects/studeo/' | relative_url }}">Studeo</a></h3>
      <span class="project-badge badge-live">Live</span>
    </div>
    <p class="project-date">May 2026 – Present</p>
    <p class="project-desc">
      Cross-platform desktop app (Windows &amp; Mac) for tracking assignments, classes, and
      lectures with a focused study area to help you stay concentrated and get work done.
      Released and available to download.
    </p>
    <div class="project-tags">
      <span class="project-tag">Electron</span>
      <span class="project-tag">React</span>
      <span class="project-tag">TypeScript</span>
      <span class="project-tag">Node.js</span>
    </div>
    <div class="project-links">
      <a class="project-link link-download" href="https://github.com/laizie/classtrack/releases" target="_blank">
        ↓ Download
      </a>
      <a class="project-link link-github" href="https://github.com/laizie/classtrack" target="_blank">
        ↗ GitHub
      </a>
    </div>
  </div>

  <div class="project-card card-fluidsim">
    <div class="project-card-header">
      <h3 class="project-title"><a class="project-title-link" href="{{ '/projects/fluidsim2d/' | relative_url }}">FluidSim2d</a></h3>
      <span class="project-badge badge-wip">WIP</span>
    </div>
    <p class="project-date">Jun 2026 – Present</p>
    <p class="project-desc">
      Real-time FLIP fluid simulation for a 2-inch round LED pocket watch. Prototyped in the
      browser with JavaScript, with the physics being ported to C++ to run on an ESP32 driving
      a circular addressable-LED matrix.
    </p>
    <div class="project-tags">
      <span class="project-tag">JavaScript</span>
      <span class="project-tag">HTML5 Canvas</span>
      <span class="project-tag">C++</span>
      <span class="project-tag">ESP32</span>
      <span class="project-tag">KiCad</span>
    </div>
    <div class="project-links">
      <a class="project-link link-github" href="https://github.com/laizie/FluidSim2d" target="_blank">
        ↗ GitHub
      </a>
    </div>
  </div>

  <div class="project-card card-daycounter">
    <div class="project-card-header">
      <h3 class="project-title"><a class="project-title-link" href="{{ '/projects/day-counter/' | relative_url }}">Day Counter Picture Frame</a></h3>
      <span class="project-badge badge-done">Completed</span>
    </div>
    <p class="project-date">Nov 2025 – Feb 2026</p>
    <p class="project-desc">
      Custom hardware device that counts elapsed days on dual seven-segment displays.
      3D-printed enclosure designed in Onshape, real-time clock module for midnight updates,
      and EEPROM persistence so it never loses count across power cycles.
    </p>
    <div class="project-tags">
      <span class="project-tag">Arduino</span>
      <span class="project-tag">C++</span>
      <span class="project-tag">Onshape</span>
      <span class="project-tag">3D Printing</span>
    </div>
    <div class="project-links">
      <a class="project-link link-github" href="https://github.com/laizie/Digital-Day-Counter-Picture-Frame" target="_blank">
        ↗ GitHub
      </a>
    </div>
  </div>

  <div class="project-card card-gameoflife">
    <div class="project-card-header">
      <h3 class="project-title"><a class="project-title-link" href="{{ '/projects/game-of-life/' | relative_url }}">Conway's Game of Life</a></h3>
      <span class="project-badge badge-done">Completed</span>
    </div>
    <p class="project-date">Jan 2026</p>
    <p class="project-desc">
      Conway's Game of Life implemented in Java with a Swing GUI. Built as a learning project
      to get hands-on with Java windowing and object-oriented design — split cleanly into
      grid, game-loop, and controller classes.
    </p>
    <div class="project-tags">
      <span class="project-tag">Java</span>
      <span class="project-tag">Swing</span>
      <span class="project-tag">AWT</span>
      <span class="project-tag">OOP</span>
    </div>
    <div class="project-links">
      <a class="project-link link-github" href="https://github.com/laizie/laizie-GameOfLife" target="_blank">
        ↗ GitHub
      </a>
    </div>
  </div>

</div>
