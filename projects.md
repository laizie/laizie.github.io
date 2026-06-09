---
layout: page
title: Projects
description: Things I've built, shipped, and maintain.
---

<style>
/* ── Design tokens — light defaults ─────────────────────── */
:root {
  --pc-bg:           #f4f5f7;
  --pc-border:       #d0d5dd;
  --pc-shadow:       0 2px 6px rgba(0,0,0,.08);
  --pc-shadow-hover: 0 8px 24px rgba(0,0,0,.14);
  --pc-title:        #0d0d0d;
  --pc-desc:         #1a1a1a;
  --pc-date:         #444;
  --pc-tag-bg:       #e8eaed;
  --pc-tag-border:   #c8cdd4;
  --pc-tag-color:    #1a1a1a;
  --pc-divider:      #d0d5dd;
  --pc-intro:        #222;
}

/* ── Dark mode overrides (body.dark-mode only — no media query) ── */
body.dark-mode {
  --pc-bg:           rgba(255,255,255,.05);
  --pc-border:       rgba(255,255,255,.1);
  --pc-shadow:       0 1px 6px rgba(0,0,0,.4);
  --pc-shadow-hover: 0 8px 28px rgba(0,0,0,.55);
  --pc-title:        #e2e8f0;
  --pc-desc:         #94a3b8;
  --pc-date:         rgba(255,255,255,.4);
  --pc-tag-bg:       rgba(255,255,255,.06);
  --pc-tag-border:   rgba(255,255,255,.14);
  --pc-tag-color:    #94a3b8;
  --pc-divider:      rgba(255,255,255,.1);
  --pc-intro:        rgba(255,255,255,.45);
}

/* ── Page header ─────────────────────────────────────────── */
.projects-intro {
  color: #222 !important;
  font-size: 1rem;
  margin: -1rem 0 2.5rem;
  border-left: 3px solid #22c55e;
  padding-left: 0.85rem;
}

/* ── Grid ─────────────────────────────────────────────────── */
.projects-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
  gap: 1.75rem;
}

/* ── Card ─────────────────────────────────────────────────── */
.project-card {
  background: var(--pc-bg);
  border: 1px solid var(--pc-border);
  border-radius: 10px;
  padding: 1.5rem 1.5rem 1.25rem;
  display: flex;
  flex-direction: column;
  gap: 0.9rem;
  position: relative;
  overflow: hidden;
  box-shadow: var(--pc-shadow);
  transition: transform 0.18s ease, box-shadow 0.18s ease;
}

.project-card::before {
  content: '';
  position: absolute;
  top: 0; left: 0; right: 0;
  height: 4px;
  border-radius: 10px 10px 0 0;
}

.project-card:hover {
  transform: translateY(-3px);
  box-shadow: var(--pc-shadow-hover);
}

/* ── Per-card accent colors ──────────────────────────────── */
.card-lazee::before      { background: #22c55e; }
.card-studeo::before     { background: #f59e0b; }
.card-daycounter::before { background: #6366f1; }

/* ── Card header row ─────────────────────────────────────── */
.project-card-header {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 0.5rem;
}

.project-card h3,
.project-title {
  margin: 0;
  font-size: 1.15rem;
  font-weight: 700;
  line-height: 1.2;
  color: #0d0d0d !important;
}

/* ── Status badges ───────────────────────────────────────── */
.project-badge {
  font-size: 0.68rem;
  font-weight: 700;
  letter-spacing: 0.06em;
  text-transform: uppercase;
  padding: 0.22rem 0.6rem;
  border-radius: 999px;
  white-space: nowrap;
  flex-shrink: 0;
}

.badge-live { background: #dcfce7; color: #15803d; border: 1px solid #bbf7d0; }
.badge-wip  { background: #fef9c3; color: #a16207; border: 1px solid #fde68a; }
.badge-done { background: #ede9fe; color: #5b21b6; border: 1px solid #ddd6fe; }


body.dark-mode .badge-live { background: rgba(34,197,94,.15);  color: #86efac; border-color: rgba(34,197,94,.3);  }
body.dark-mode .badge-wip  { background: rgba(245,158,11,.15); color: #fcd34d; border-color: rgba(245,158,11,.3); }
body.dark-mode .badge-done { background: rgba(99,102,241,.15); color: #a5b4fc; border-color: rgba(99,102,241,.3); }
body.dark-mode .project-card h3,
body.dark-mode .project-title    { color: #e2e8f0 !important; }
body.dark-mode .project-desc     { color: #b0bec5 !important; }
body.dark-mode .project-date     { color: rgba(255,255,255,.45) !important; }
body.dark-mode .project-tag      { color: #94a3b8 !important; }
body.dark-mode .projects-intro   { color: rgba(255,255,255,.5) !important; }

/* ── Date ────────────────────────────────────────────────── */
.project-date {
  font-size: 0.78rem;
  color: #444 !important;
  margin: -0.4rem 0 0;
  display: flex;
  align-items: center;
  gap: 0.35rem;
}

.project-date::before {
  content: '';
  display: inline-block;
  width: 6px; height: 6px;
  border-radius: 50%;
  flex-shrink: 0;
}

.card-lazee      .project-date::before { background: #22c55e; }
.card-studeo     .project-date::before { background: #f59e0b; }
.card-daycounter .project-date::before { background: #6366f1; }

/* ── Description ─────────────────────────────────────────── */
.project-desc {
  font-size: 0.9rem;
  line-height: 1.6;
  color: #1a1a1a !important;
  margin: 0;
  flex: 1;
}

/* ── Tech tags ───────────────────────────────────────────── */
.project-tags {
  display: flex;
  flex-wrap: wrap;
  gap: 0.35rem;
}

.project-tag {
  font-size: 0.7rem;
  padding: 0.18rem 0.5rem;
  background: var(--pc-tag-bg);
  border: 1px solid var(--pc-tag-border);
  border-radius: 4px;
  font-family: ui-monospace, monospace;
  color: #1a1a1a !important;
}

/* ── Links ───────────────────────────────────────────────── */
.project-links {
  display: flex;
  gap: 0.6rem;
  flex-wrap: wrap;
  padding-top: 0.75rem;
  border-top: 1px solid var(--pc-divider);
  margin-top: 0.25rem;
}

.project-link {
  font-size: 0.8rem;
  font-weight: 600;
  padding: 0.3rem 0.85rem;
  border-radius: 6px;
  text-decoration: none !important;
  transition: opacity 0.15s, transform 0.1s;
  display: inline-flex;
  align-items: center;
  gap: 0.3rem;
}

.project-link:hover { opacity: 0.8; transform: translateY(-1px); }

.link-appstore { background: #22c55e; color: #fff !important; }
.link-github   { background: #1e293b; color: #fff !important; }

body.dark-mode .link-github { background: rgba(255,255,255,.12); color: #e2e8f0 !important; }
</style>

<p class="projects-intro">A collection of personal projects I've built and maintain.</p>

<div class="projects-grid">

  <div class="project-card card-lazee">
    <div class="project-card-header">
      <h3 class="project-title" style="color:#0d0d0d;margin:0;">Lazee</h3>
      <span class="project-badge badge-live">Live</span>
    </div>
    <p class="project-date">Nov 2025 – Present</p>
    <p class="project-desc">
      iOS strength training tracker for lifters who want a simple, fast way to log workouts.
      No clutter, no subscriptions. Built solo, published and actively maintained on the App Store.
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

  <div class="project-card card-studeo">
    <div class="project-card-header">
      <h3 class="project-title" style="color:#0d0d0d;margin:0;">Studeo</h3>
      <span class="project-badge badge-wip">WIP</span>
    </div>
    <p class="project-date">May 2026 – Present</p>
    <p class="project-desc">
      Cross-platform desktop app (Windows &amp; Mac) for tracking assignments, classes, and
      lectures — with a focused study area to help you stay concentrated and get work done.
    </p>
    <div class="project-tags">
      <span class="project-tag">Electron</span>
      <span class="project-tag">React</span>
      <span class="project-tag">TypeScript</span>
      <span class="project-tag">Node.js</span>
    </div>
    <div class="project-links">
      <a class="project-link link-github" href="https://github.com/laizie/classtrack" target="_blank">
        ↗ GitHub
      </a>
    </div>
  </div>

  <div class="project-card card-daycounter">
    <div class="project-card-header">
      <h3 class="project-title" style="color:#0d0d0d;margin:0;">Day Counter Picture Frame</h3>
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

</div>
