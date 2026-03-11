import { useState, useRef, useCallback, useEffect } from "react";

const FONTS = `@import url('https://fonts.googleapis.com/css2?family=Syne:wght@400;500;600;700;800&family=JetBrains+Mono:wght@400;500&display=swap');`;

const STYLES = `
  * { margin: 0; padding: 0; box-sizing: border-box; }
  body { font-family: 'Syne', sans-serif; background: #090A0F; color: #E2E4ED; height: 100vh; overflow: hidden; }
  ::-webkit-scrollbar { width: 4px; height: 4px; }
  ::-webkit-scrollbar-track { background: transparent; }
  ::-webkit-scrollbar-thumb { background: #2A2D3E; border-radius: 4px; }

  .app { display: flex; flex-direction: column; height: 100vh; }

  /* TOPBAR */
  .topbar { display: flex; align-items: center; gap: 0; height: 52px; background: #0E1018; border-bottom: 1px solid #1E2130; padding: 0 16px; flex-shrink: 0; }
  .logo { display: flex; align-items: center; gap: 8px; margin-right: 24px; }
  .logo-icon { width: 28px; height: 28px; background: linear-gradient(135deg, #00D4AA, #0097FF); border-radius: 7px; display: flex; align-items: center; justify-content: center; font-size: 14px; }
  .logo-text { font-size: 15px; font-weight: 700; color: #F0F2FF; letter-spacing: -0.3px; }
  .topbar-divider { width: 1px; height: 28px; background: #1E2130; margin: 0 12px; }
  .tool-group { display: flex; align-items: center; gap: 2px; }
  .tool-btn { display: flex; align-items: center; gap: 6px; padding: 6px 10px; border-radius: 6px; border: none; background: transparent; color: #8B90A8; cursor: pointer; font-size: 12px; font-family: 'Syne', sans-serif; font-weight: 500; transition: all 0.15s; white-space: nowrap; }
  .tool-btn:hover { background: #1A1D2E; color: #D0D3E8; }
  .tool-btn.active { background: #1A2640; color: #00D4AA; }
  .tool-btn svg { flex-shrink: 0; }
  .view-toggle { display: flex; align-items: center; background: #141620; border-radius: 8px; padding: 3px; gap: 1px; }
  .view-btn { padding: 5px 12px; border-radius: 5px; border: none; background: transparent; color: #6B6F85; cursor: pointer; font-size: 12px; font-family: 'Syne', sans-serif; font-weight: 600; transition: all 0.15s; }
  .view-btn.active { background: #1E2238; color: #E2E4ED; }
  .spacer { flex: 1; }
  .action-btn { display: flex; align-items: center; gap: 7px; padding: 7px 14px; border-radius: 7px; border: none; cursor: pointer; font-size: 12px; font-family: 'Syne', sans-serif; font-weight: 600; transition: all 0.15s; }
  .action-btn.primary { background: linear-gradient(135deg, #00D4AA, #00AACC); color: #050709; }
  .action-btn.primary:hover { opacity: 0.9; transform: translateY(-1px); }
  .action-btn.secondary { background: #1A1D2E; color: #A0A4BC; border: 1px solid #252840; }
  .action-btn.secondary:hover { background: #1E2238; color: #D0D3E8; }
  .action-btn.ghost { background: transparent; color: #6B6F85; }
  .action-btn.github { background: #1A1D2E; color: #C8CADC; border: 1px solid #252840; }
  .action-btn.github:hover { background: #1E2238; border-color: #00D4AA44; color: #00D4AA; }

  /* MAIN LAYOUT */
  .main { display: flex; flex: 1; overflow: hidden; }

  /* LEFT SIDEBAR */
  .sidebar { width: 240px; background: #0E1018; border-right: 1px solid #1E2130; display: flex; flex-direction: column; flex-shrink: 0; overflow: hidden; }
  .sidebar-tabs { display: flex; border-bottom: 1px solid #1E2130; padding: 8px 8px 0; gap: 2px; }
  .sidebar-tab { padding: 7px 12px; border-radius: 6px 6px 0 0; border: none; background: transparent; color: #5A5E75; cursor: pointer; font-size: 11px; font-family: 'Syne', sans-serif; font-weight: 600; transition: all 0.15s; text-transform: uppercase; letter-spacing: 0.5px; }
  .sidebar-tab.active { background: #141825; color: #A0A4BC; border-bottom: 2px solid #00D4AA; margin-bottom: -1px; }
  .sidebar-content { flex: 1; overflow-y: auto; padding: 8px; }
  .sidebar-section { margin-bottom: 16px; }
  .sidebar-section-title { font-size: 10px; font-weight: 700; text-transform: uppercase; letter-spacing: 1px; color: #444860; padding: 4px 6px; margin-bottom: 4px; }

  /* FILE TREE */
  .file-item { display: flex; align-items: center; gap: 7px; padding: 6px 8px; border-radius: 6px; cursor: pointer; font-size: 12px; color: #7A7F98; transition: all 0.12s; font-family: 'JetBrains Mono', monospace; }
  .file-item:hover { background: #141825; color: #B0B4C8; }
  .file-item.active { background: #162030; color: #00D4AA; }
  .file-item .file-icon { width: 16px; height: 16px; flex-shrink: 0; }
  .file-ext { font-size: 10px; padding: 1px 5px; border-radius: 3px; margin-left: auto; font-weight: 600; }
  .ext-html { background: #1E2D1A; color: #6BDE8A; }
  .ext-css { background: #1A1E2D; color: #6B9EDE; }
  .ext-js { background: #2D271A; color: #DEBB6B; }

  /* UPLOAD ZONE */
  .upload-zone { border: 1.5px dashed #252840; border-radius: 10px; padding: 20px 12px; text-align: center; cursor: pointer; transition: all 0.2s; margin: 8px 0; }
  .upload-zone:hover { border-color: #00D4AA55; background: #0D1A1A; }
  .upload-zone-icon { font-size: 22px; margin-bottom: 6px; }
  .upload-zone p { font-size: 11px; color: #5A5E75; line-height: 1.5; }
  .upload-zone span { color: #00D4AA; }

  /* CANVAS AREA */
  .canvas-area { flex: 1; display: flex; flex-direction: column; overflow: hidden; background: #0A0C14; }
  .canvas-toolbar { display: flex; align-items: center; gap: 8px; padding: 8px 16px; background: #0E1018; border-bottom: 1px solid #1E2130; flex-shrink: 0; }
  .device-btn { padding: 5px 8px; border-radius: 5px; border: none; background: transparent; color: #5A5E75; cursor: pointer; transition: all 0.15s; }
  .device-btn:hover { color: #A0A4BC; background: #141825; }
  .device-btn.active { color: #00D4AA; background: #0D1E1E; }
  .url-bar { flex: 1; background: #141620; border: 1px solid #1E2130; border-radius: 7px; padding: 6px 14px; font-size: 12px; font-family: 'JetBrains Mono', monospace; color: #6B6F85; max-width: 400px; cursor: default; }
  .zoom-ctrl { display: flex; align-items: center; gap: 6px; font-size: 12px; color: #5A5E75; }
  .zoom-btn { width: 24px; height: 24px; border-radius: 5px; border: none; background: #141620; color: #8B90A8; cursor: pointer; font-size: 14px; display: flex; align-items: center; justify-content: center; transition: all 0.15s; }
  .zoom-btn:hover { background: #1A1D2E; color: #D0D3E8; }

  .canvas-wrapper { flex: 1; overflow: auto; display: flex; align-items: flex-start; justify-content: center; padding: 24px; }
  .canvas-frame { background: white; border-radius: 8px; box-shadow: 0 0 0 1px #1E2130, 0 20px 60px rgba(0,0,0,0.5); overflow: hidden; transition: all 0.3s; position: relative; }
  .canvas-frame iframe { display: block; border: none; }
  .canvas-frame.desktop { width: 1200px; }
  .canvas-frame.tablet { width: 768px; }
  .canvas-frame.mobile { width: 375px; }

  /* EMPTY STATE */
  .empty-state { flex: 1; display: flex; flex-direction: column; align-items: center; justify-content: center; gap: 16px; padding: 40px; }
  .empty-icon { width: 72px; height: 72px; background: linear-gradient(135deg, #00D4AA22, #0097FF22); border-radius: 20px; display: flex; align-items: center; justify-content: center; font-size: 32px; border: 1px solid #00D4AA33; }
  .empty-title { font-size: 20px; font-weight: 700; color: #E2E4ED; text-align: center; }
  .empty-sub { font-size: 13px; color: #5A5E75; text-align: center; max-width: 280px; line-height: 1.6; }
  .empty-actions { display: flex; gap: 10px; flex-wrap: wrap; justify-content: center; margin-top: 8px; }

  /* CODE EDITOR */
  .code-editor { flex: 1; display: flex; flex-direction: column; overflow: hidden; }
  .code-content { flex: 1; overflow: auto; }
  textarea.code-textarea { width: 100%; height: 100%; background: #090A0F; color: #B8C2E0; font-family: 'JetBrains Mono', monospace; font-size: 13px; line-height: 1.7; padding: 20px; border: none; outline: none; resize: none; tab-size: 2; }

  /* SPLIT VIEW */
  .split-view { flex: 1; display: flex; overflow: hidden; }
  .split-code { flex: 1; border-right: 1px solid #1E2130; overflow: hidden; display: flex; flex-direction: column; }
  .split-preview { flex: 1; overflow: hidden; }
  .split-label { padding: 8px 16px; font-size: 10px; font-weight: 700; text-transform: uppercase; letter-spacing: 1px; color: #444860; background: #0E1018; border-bottom: 1px solid #1E2130; }

  /* RIGHT PANEL */
  .right-panel { width: 260px; background: #0E1018; border-left: 1px solid #1E2130; display: flex; flex-direction: column; flex-shrink: 0; overflow: hidden; }
  .panel-header { padding: 14px 16px; border-bottom: 1px solid #1E2130; font-size: 11px; font-weight: 700; text-transform: uppercase; letter-spacing: 1px; color: #5A5E75; }
  .panel-body { flex: 1; overflow-y: auto; padding: 12px; }
  .prop-group { margin-bottom: 16px; }
  .prop-group-title { font-size: 10px; font-weight: 700; text-transform: uppercase; letter-spacing: 0.8px; color: #3A3E55; margin-bottom: 8px; padding: 0 2px; }
  .prop-row { display: flex; align-items: center; justify-content: space-between; margin-bottom: 6px; gap: 8px; }
  .prop-label { font-size: 11px; color: #6B6F85; flex-shrink: 0; width: 70px; }
  .prop-input { flex: 1; background: #141620; border: 1px solid #1E2130; border-radius: 5px; padding: 5px 8px; font-size: 11px; font-family: 'JetBrains Mono', monospace; color: #C0C4D8; outline: none; width: 100%; transition: border-color 0.15s; }
  .prop-input:focus { border-color: #00D4AA55; }
  .color-swatch { width: 26px; height: 26px; border-radius: 5px; border: 1px solid #2A2D3E; cursor: pointer; flex-shrink: 0; }
  .no-selection { display: flex; flex-direction: column; align-items: center; justify-content: center; height: 100%; gap: 10px; padding: 20px; text-align: center; }
  .no-selection-icon { font-size: 28px; opacity: 0.3; }
  .no-selection p { font-size: 12px; color: #444860; line-height: 1.5; }

  /* GITHUB MODAL */
  .modal-overlay { position: fixed; inset: 0; background: rgba(5,6,10,0.85); backdrop-filter: blur(8px); display: flex; align-items: center; justify-content: center; z-index: 1000; }
  .modal { background: #0E1018; border: 1px solid #1E2130; border-radius: 14px; padding: 28px; width: 480px; box-shadow: 0 40px 80px rgba(0,0,0,0.6); }
  .modal-title { font-size: 18px; font-weight: 700; color: #E8EAF8; margin-bottom: 6px; display: flex; align-items: center; gap: 10px; }
  .modal-sub { font-size: 13px; color: #5A5E75; margin-bottom: 24px; line-height: 1.5; }
  .modal-input { width: 100%; background: #141620; border: 1.5px solid #1E2130; border-radius: 8px; padding: 12px 14px; font-size: 13px; font-family: 'JetBrains Mono', monospace; color: #C0C4D8; outline: none; transition: all 0.15s; margin-bottom: 8px; }
  .modal-input:focus { border-color: #00D4AA55; background: #0F1622; }
  .modal-hint { font-size: 11px; color: #3A3E55; margin-bottom: 20px; line-height: 1.4; }
  .modal-hint code { color: #00D4AA; background: #0D1E1E; padding: 1px 6px; border-radius: 3px; }
  .modal-actions { display: flex; gap: 10px; justify-content: flex-end; }
  .modal-status { padding: 10px 14px; border-radius: 8px; font-size: 12px; margin-bottom: 16px; }
  .modal-status.loading { background: #1A1E2D; color: #6B9EDE; border: 1px solid #1E2845; }
  .modal-status.success { background: #0D1E1A; color: #00D4AA; border: 1px solid #00D4AA33; }
  .modal-status.error { background: #1E1010; color: #DE6B6B; border: 1px solid #3E1818; }

  /* LAYER ITEM */
  .layer-item { display: flex; align-items: center; gap: 7px; padding: 5px 8px; border-radius: 5px; cursor: pointer; font-size: 11px; color: #6B6F85; transition: all 0.12s; }
  .layer-item:hover { background: #141825; color: #B0B4C8; }
  .layer-item.selected { background: #162030; color: #00D4AA; }
  .layer-indent { padding-left: 20px; }
  .layer-tag { font-family: 'JetBrains Mono', monospace; font-size: 10px; }

  /* TOAST */
  .toast { position: fixed; bottom: 24px; right: 24px; background: #1A1D2E; border: 1px solid #252840; border-radius: 10px; padding: 12px 16px; display: flex; align-items: center; gap: 10px; font-size: 13px; color: #D0D3E8; box-shadow: 0 10px 30px rgba(0,0,0,0.4); z-index: 2000; animation: slideUp 0.3s ease; }
  @keyframes slideUp { from { transform: translateY(20px); opacity: 0; } to { transform: translateY(0); opacity: 1; } }
  .toast.success .toast-dot { background: #00D4AA; }
  .toast.error .toast-dot { background: #DE6B6B; }
  .toast-dot { width: 8px; height: 8px; border-radius: 50%; flex-shrink: 0; }

  /* SCROLLABLE AREA INSIDE CODE */
  .line-nums { position: absolute; left: 0; top: 0; padding: 20px 10px; color: #2A2D3E; font-family: 'JetBrains Mono', monospace; font-size: 13px; line-height: 1.7; user-select: none; text-align: right; min-width: 40px; }
`;

const IFRAME_SCRIPT = `
  <script>
    (function() {
      var style = document.createElement('style');
      style.textContent = '* { outline: none !important; } [data-selected] { outline: 2px solid #00D4AA !important; outline-offset: 2px !important; }';
      document.head.appendChild(style);
      var selected = null;
      document.addEventListener('click', function(e) {
        e.preventDefault();
        if (selected) selected.removeAttribute('data-selected');
        selected = e.target;
        selected.setAttribute('data-selected', '');
        var el = e.target;
        var info = {
          tag: el.tagName.toLowerCase(),
          id: el.id || '',
          className: el.className || '',
          textContent: el.innerText ? el.innerText.substring(0, 100) : '',
          styles: {
            color: window.getComputedStyle(el).color,
            backgroundColor: window.getComputedStyle(el).backgroundColor,
            fontSize: window.getComputedStyle(el).fontSize,
            fontWeight: window.getComputedStyle(el).fontWeight,
            padding: window.getComputedStyle(el).padding,
            margin: window.getComputedStyle(el).margin,
            width: window.getComputedStyle(el).width,
            height: window.getComputedStyle(el).height,
          }
        };
        window.parent.postMessage({ type: 'elementSelected', data: info }, '*');
      }, true);
    })();
  <\/script>
`;

const SAMPLE_HTML = `<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>My Website</title>
  <style>
    * { margin: 0; padding: 0; box-sizing: border-box; }
    body { font-family: 'Inter', system-ui, sans-serif; background: #fff; }
    nav { background: #0f172a; padding: 16px 48px; display: flex; align-items: center; justify-content: space-between; }
    .nav-logo { color: #38bdf8; font-weight: 800; font-size: 20px; letter-spacing: -0.5px; }
    .nav-links { display: flex; gap: 32px; list-style: none; }
    .nav-links a { color: #94a3b8; text-decoration: none; font-size: 14px; font-weight: 500; }
    .nav-links a:hover { color: #e2e8f0; }
    .hero { padding: 100px 48px; background: linear-gradient(135deg, #0f172a 0%, #1e3a5f 100%); text-align: center; }
    .hero h1 { font-size: 64px; font-weight: 800; color: white; letter-spacing: -2px; line-height: 1.1; margin-bottom: 20px; }
    .hero h1 span { color: #38bdf8; }
    .hero p { font-size: 18px; color: #94a3b8; max-width: 500px; margin: 0 auto 40px; line-height: 1.7; }
    .hero-btn { background: #38bdf8; color: #0f172a; padding: 14px 32px; border-radius: 8px; text-decoration: none; font-weight: 700; font-size: 15px; display: inline-block; }
    .features { padding: 80px 48px; background: #f8fafc; }
    .features h2 { font-size: 36px; font-weight: 800; text-align: center; color: #0f172a; margin-bottom: 48px; }
    .cards { display: grid; grid-template-columns: repeat(3, 1fr); gap: 24px; max-width: 1000px; margin: 0 auto; }
    .card { background: white; padding: 28px; border-radius: 12px; box-shadow: 0 1px 3px rgba(0,0,0,0.06); }
    .card-icon { font-size: 28px; margin-bottom: 14px; }
    .card h3 { font-size: 17px; font-weight: 700; color: #0f172a; margin-bottom: 8px; }
    .card p { font-size: 14px; color: #64748b; line-height: 1.6; }
    footer { background: #0f172a; color: #475569; text-align: center; padding: 24px; font-size: 13px; }
  </style>
</head>
<body>
  <nav>
    <div class="nav-logo">⚡ Nexus</div>
    <ul class="nav-links">
      <li><a href="#">Home</a></li>
      <li><a href="#">About</a></li>
      <li><a href="#">Services</a></li>
      <li><a href="#">Contact</a></li>
    </ul>
  </nav>
  <section class="hero">
    <h1>Build Things<br><span>That Matter</span></h1>
    <p>A modern platform for creators and developers to ship ideas faster than ever before.</p>
    <a href="#" class="hero-btn">Get Started Free →</a>
  </section>
  <section class="features">
    <h2>Why Choose Nexus?</h2>
    <div class="cards">
      <div class="card">
        <div class="card-icon">🚀</div>
        <h3>Blazing Fast</h3>
        <p>Optimized for speed at every layer. Your users will notice the difference immediately.</p>
      </div>
      <div class="card">
        <div class="card-icon">🔒</div>
        <h3>Secure by Default</h3>
        <p>Enterprise-grade security built in from the ground up. Never compromise on safety.</p>
      </div>
      <div class="card">
        <div class="card-icon">🎨</div>
        <h3>Beautiful UI</h3>
        <p>Stunning components that look great out of the box. Customize everything to your brand.</p>
      </div>
    </div>
  </section>
  <footer>© 2025 Nexus. All rights reserved.</footer>
</body>
</html>`;

function Icon({ name, size = 14 }) {
  const icons = {
    upload: <svg width={size} height={size} fill="none" stroke="currentColor" viewBox="0 0 24 24"><path strokeLinecap="round" strokeLinejoin="round" strokeWidth={2} d="M4 16v1a3 3 0 003 3h10a3 3 0 003-3v-1m-4-8l-4-4m0 0L8 8m4-4v12"/></svg>,
    github: <svg width={size} height={size} fill="currentColor" viewBox="0 0 24 24"><path d="M12 0C5.37 0 0 5.37 0 12c0 5.31 3.435 9.795 8.205 11.385.6.105.825-.255.825-.57 0-.285-.015-1.23-.015-2.235-3.015.555-3.795-.735-4.035-1.41-.135-.345-.72-1.41-1.23-1.695-.42-.225-1.02-.78-.015-.795.945-.015 1.62.87 1.845 1.23 1.08 1.815 2.805 1.305 3.495.99.105-.78.42-1.305.765-1.605-2.67-.3-5.46-1.335-5.46-5.925 0-1.305.465-2.385 1.23-3.225-.12-.3-.54-1.53.12-3.18 0 0 1.005-.315 3.3 1.23.96-.27 1.98-.405 3-.405s2.04.135 3 .405c2.295-1.56 3.3-1.23 3.3-1.23.66 1.65.24 2.88.12 3.18.765.84 1.23 1.905 1.23 3.225 0 4.605-2.805 5.625-5.475 5.925.435.375.81 1.095.81 2.22 0 1.605-.015 2.895-.015 3.3 0 .315.225.69.825.57A12.02 12.02 0 0024 12c0-6.63-5.37-12-12-12z"/></svg>,
    desktop: <svg width={size} height={size} fill="none" stroke="currentColor" viewBox="0 0 24 24"><rect x="2" y="3" width="20" height="14" rx="2" strokeWidth={1.5}/><line x1="8" y1="21" x2="16" y2="21" strokeWidth={1.5}/><line x1="12" y1="17" x2="12" y2="21" strokeWidth={1.5}/></svg>,
    tablet: <svg width={size} height={size} fill="none" stroke="currentColor" viewBox="0 0 24 24"><rect x="4" y="2" width="16" height="20" rx="2" strokeWidth={1.5}/><line x1="12" y1="18" x2="12.01" y2="18" strokeWidth={2} strokeLinecap="round"/></svg>,
    mobile: <svg width={size} height={size} fill="none" stroke="currentColor" viewBox="0 0 24 24"><rect x="5" y="2" width="14" height="20" rx="2" strokeWidth={1.5}/><line x1="12" y1="18" x2="12.01" y2="18" strokeWidth={2} strokeLinecap="round"/></svg>,
    file: <svg width={size} height={size} fill="none" stroke="currentColor" viewBox="0 0 24 24"><path strokeLinecap="round" strokeLinejoin="round" strokeWidth={1.5} d="M9 12h6m-6 4h6m2 5H7a2 2 0 01-2-2V5a2 2 0 012-2h5.586a1 1 0 01.707.293l5.414 5.414a1 1 0 01.293.707V19a2 2 0 01-2 2z"/></svg>,
    layers: <svg width={size} height={size} fill="none" stroke="currentColor" viewBox="0 0 24 24"><path strokeLinecap="round" strokeLinejoin="round" strokeWidth={1.5} d="M12 2L2 7l10 5 10-5-10-5zM2 17l10 5 10-5M2 12l10 5 10-5"/></svg>,
    eye: <svg width={size} height={size} fill="none" stroke="currentColor" viewBox="0 0 24 24"><path strokeLinecap="round" strokeLinejoin="round" strokeWidth={1.5} d="M15 12a3 3 0 11-6 0 3 3 0 016 0z"/><path strokeLinecap="round" strokeLinejoin="round" strokeWidth={1.5} d="M2.458 12C3.732 7.943 7.523 5 12 5c4.478 0 8.268 2.943 9.542 7-1.274 4.057-5.064 7-9.542 7-4.477 0-8.268-2.943-9.542-7z"/></svg>,
    code: <svg width={size} height={size} fill="none" stroke="currentColor" viewBox="0 0 24 24"><path strokeLinecap="round" strokeLinejoin="round" strokeWidth={1.5} d="M10 20l4-16m4 4l4 4-4 4M6 16l-4-4 4-4"/></svg>,
    download: <svg width={size} height={size} fill="none" stroke="currentColor" viewBox="0 0 24 24"><path strokeLinecap="round" strokeLinejoin="round" strokeWidth={2} d="M4 16v1a3 3 0 003 3h10a3 3 0 003-3v-1m-4-4l-4 4m0 0l-4-4m4 4V4"/></svg>,
    close: <svg width={size} height={size} fill="none" stroke="currentColor" viewBox="0 0 24 24"><path strokeLinecap="round" strokeLinejoin="round" strokeWidth={2} d="M6 18L18 6M6 6l12 12"/></svg>,
    refresh: <svg width={size} height={size} fill="none" stroke="currentColor" viewBox="0 0 24 24"><path strokeLinecap="round" strokeLinejoin="round" strokeWidth={1.5} d="M4 4v5h.582m15.356 2A8.001 8.001 0 004.582 9m0 0H9m11 11v-5h-.581m0 0a8.003 8.003 0 01-15.357-2m15.357 2H15"/></svg>,
    plus: <svg width={size} height={size} fill="none" stroke="currentColor" viewBox="0 0 24 24"><path strokeLinecap="round" strokeLinejoin="round" strokeWidth={2} d="M12 4v16m8-8H4"/></svg>,
    cursor: <svg width={size} height={size} fill="none" stroke="currentColor" viewBox="0 0 24 24"><path strokeLinecap="round" strokeLinejoin="round" strokeWidth={1.5} d="M15 15l-2 5L9 9l11 4-5 2zm0 0l5 5"/></svg>,
    save: <svg width={size} height={size} fill="none" stroke="currentColor" viewBox="0 0 24 24"><path strokeLinecap="round" strokeLinejoin="round" strokeWidth={1.5} d="M8 7H5a2 2 0 00-2 2v9a2 2 0 002 2h14a2 2 0 002-2V9a2 2 0 00-2-2h-3m-1 4l-3 3m0 0l-3-3m3 3V4"/></svg>,
  };
  return icons[name] || null;
}

function Toast({ toast }) {
  if (!toast) return null;
  return (
    <div className={`toast ${toast.type}`}>
      <div className="toast-dot" />
      {toast.message}
    </div>
  );
}

function parseGithubUrl(url) {
  const match = url.match(/github\.com\/([^/]+)\/([^/]+)/);
  if (!match) return null;
  return { owner: match[1], repo: match[2].replace(/\.git$/, '') };
}

export default function WebsiteEditor() {
  const [files, setFiles] = useState({ "index.html": SAMPLE_HTML });
  const [activeFile, setActiveFile] = useState("index.html");
  const [view, setView] = useState("visual");
  const [device, setDevice] = useState("desktop");
  const [zoom, setZoom] = useState(100);
  const [sidebarTab, setSidebarTab] = useState("files");
  const [selectedEl, setSelectedEl] = useState(null);
  const [githubModal, setGithubModal] = useState(false);
  const [repoUrl, setRepoUrl] = useState("");
  const [cloneStatus, setCloneStatus] = useState(null);
  const [toast, setToast] = useState(null);
  const [layers, setLayers] = useState([]);
  const iframeRef = useRef(null);
  const fileInputRef = useRef(null);
  const toastTimer = useRef(null);

  const showToast = (message, type = "success") => {
    if (toastTimer.current) clearTimeout(toastTimer.current);
    setToast({ message, type });
    toastTimer.current = setTimeout(() => setToast(null), 3000);
  };

  useEffect(() => {
    const handler = (e) => {
      if (e.data?.type === "elementSelected") setSelectedEl(e.data.data);
    };
    window.addEventListener("message", handler);
    return () => window.removeEventListener("message", handler);
  }, []);

  const getIframeSrc = useCallback(() => {
    const html = files[activeFile] || "";
    return html + (html.includes("</body>") ? IFRAME_SCRIPT.replace("</body>", "") : IFRAME_SCRIPT);
  }, [files, activeFile]);

  const handleFileUpload = (e) => {
    const uploaded = e.target.files;
    if (!uploaded?.length) return;
    const newFiles = { ...files };
    let count = 0;
    Array.from(uploaded).forEach(file => {
      const reader = new FileReader();
      reader.onload = (ev) => {
        newFiles[file.name] = ev.target.result;
        count++;
        if (count === uploaded.length) {
          setFiles({ ...newFiles });
          setActiveFile(uploaded[0].name);
          showToast(`${uploaded.length} file(s) uploaded`);
        }
      };
      reader.readAsText(file);
    });
    e.target.value = "";
  };

  const handleDrop = (e) => {
    e.preventDefault();
    const droppedFiles = e.dataTransfer.files;
    if (!droppedFiles?.length) return;
    const newFiles = { ...files };
    let count = 0;
    Array.from(droppedFiles).forEach(file => {
      const reader = new FileReader();
      reader.onload = (ev) => {
        newFiles[file.name] = ev.target.result;
        count++;
        if (count === droppedFiles.length) {
          setFiles({ ...newFiles });
          setActiveFile(droppedFiles[0].name);
          showToast(`${droppedFiles.length} file(s) uploaded`);
        }
      };
      reader.readAsText(file);
    });
  };

  const handleCloneRepo = async () => {
    const parsed = parseGithubUrl(repoUrl);
    if (!parsed) {
      setCloneStatus({ type: "error", message: "Invalid GitHub URL. Please check and try again." });
      return;
    }
    setCloneStatus({ type: "loading", message: `Cloning ${parsed.owner}/${parsed.repo}...` });
    try {
      const treeRes = await fetch(`https://api.github.com/repos/${parsed.owner}/${parsed.repo}/git/trees/HEAD?recursive=1`);
      if (!treeRes.ok) throw new Error("Repository not found or is private");
      const treeData = await treeRes.json();
      const webFiles = treeData.tree.filter(f => f.type === "blob" && (f.path.endsWith(".html") || f.path.endsWith(".css") || f.path.endsWith(".js")) && !f.path.includes("node_modules") && f.size < 500000);
      if (!webFiles.length) throw new Error("No HTML/CSS/JS files found in this repository");
      setCloneStatus({ type: "loading", message: `Fetching ${webFiles.length} files...` });
      const newFiles = {};
      await Promise.all(webFiles.slice(0, 20).map(async (file) => {
        const res = await fetch(`https://api.github.com/repos/${parsed.owner}/${parsed.repo}/contents/${file.path}`);
        const data = await res.json();
        if (data.content) {
          newFiles[file.path.split("/").pop()] = atob(data.content.replace(/\n/g, ""));
        }
      }));
      if (!Object.keys(newFiles).length) throw new Error("Could not fetch file contents");
      setFiles(prev => ({ ...prev, ...newFiles }));
      const firstHtml = Object.keys(newFiles).find(f => f.endsWith(".html")) || Object.keys(newFiles)[0];
      setActiveFile(firstHtml);
      setCloneStatus({ type: "success", message: `Cloned ${Object.keys(newFiles).length} files from ${parsed.owner}/${parsed.repo}` });
      setTimeout(() => { setGithubModal(false); setCloneStatus(null); setRepoUrl(""); showToast(`Cloned ${parsed.repo} successfully`); }, 1500);
    } catch (err) {
      setCloneStatus({ type: "error", message: err.message });
    }
  };

  const downloadFile = () => {
    const content = files[activeFile] || "";
    const blob = new Blob([content], { type: "text/plain" });
    const url = URL.createObjectURL(blob);
    const a = document.createElement("a");
    a.href = url; a.download = activeFile; a.click();
    URL.revokeObjectURL(url);
    showToast(`Downloaded ${activeFile}`);
  };

  const downloadAll = () => {
    Object.entries(files).forEach(([name, content]) => {
      const blob = new Blob([content], { type: "text/plain" });
      const url = URL.createObjectURL(blob);
      const a = document.createElement("a");
      a.href = url; a.download = name; a.click();
      URL.revokeObjectURL(url);
    });
    showToast(`Downloaded ${Object.keys(files).length} files`);
  };

  const getFileExt = (name) => name.split(".").pop();

  const getLayersFromHtml = (html) => {
    const parser = new DOMParser();
    const doc = parser.parseFromString(html, "text/html");
    const elements = [];
    const traverse = (el, depth = 0) => {
      if (el.nodeType !== 1) return;
      const tag = el.tagName.toLowerCase();
      if (["script", "style", "meta", "link", "head"].includes(tag)) return;
      elements.push({ tag, id: el.id, className: el.className, depth });
      Array.from(el.children).forEach(child => traverse(child, depth + 1));
    };
    traverse(doc.body);
    return elements.slice(0, 50);
  };

  useEffect(() => {
    if (files[activeFile] && activeFile.endsWith(".html")) {
      setLayers(getLayersFromHtml(files[activeFile]));
    }
  }, [activeFile, files]);

  const iframeHeight = device === "desktop" ? 800 : device === "tablet" ? 1024 : 812;
  const activeContent = files[activeFile] || "";

  return (
    <>
      <style>{FONTS + STYLES}</style>
      <div className="app">
        {/* TOPBAR */}
        <div className="topbar">
          <div className="logo">
            <div className="logo-icon">✦</div>
            <span className="logo-text">Forge</span>
          </div>
          <div className="topbar-divider" />
          <div className="tool-group">
            <button className="tool-btn active"><Icon name="cursor" /> Select</button>
            <button className="tool-btn"><Icon name="plus" /> Add Element</button>
          </div>
          <div className="topbar-divider" />
          <div className="view-toggle">
            <button className={`view-btn ${view === "visual" ? "active" : ""}`} onClick={() => setView("visual")}>Visual</button>
            <button className={`view-btn ${view === "split" ? "active" : ""}`} onClick={() => setView("split")}>Split</button>
            <button className={`view-btn ${view === "code" ? "active" : ""}`} onClick={() => setView("code")}>Code</button>
          </div>
          <div className="spacer" />
          <div className="tool-group" style={{ gap: 8 }}>
            <button className="action-btn github" onClick={() => setGithubModal(true)}>
              <Icon name="github" size={13} /> Clone Repo
            </button>
            <button className="action-btn secondary" onClick={() => fileInputRef.current?.click()}>
              <Icon name="upload" size={13} /> Upload
            </button>
            <button className="action-btn secondary" onClick={downloadAll}>
              <Icon name="download" size={13} /> Export
            </button>
            <button className="action-btn primary" onClick={() => showToast("Project saved!", "success")}>
              <Icon name="save" size={13} /> Save
            </button>
          </div>
        </div>

        <div className="main">
          {/* LEFT SIDEBAR */}
          <div className="sidebar">
            <div className="sidebar-tabs">
              <button className={`sidebar-tab ${sidebarTab === "files" ? "active" : ""}`} onClick={() => setSidebarTab("files")}>Files</button>
              <button className={`sidebar-tab ${sidebarTab === "layers" ? "active" : ""}`} onClick={() => setSidebarTab("layers")}>Layers</button>
            </div>
            <div className="sidebar-content">
              {sidebarTab === "files" && (
                <>
                  <div className="sidebar-section">
                    <div className="sidebar-section-title">Project Files</div>
                    {Object.keys(files).map(name => (
                      <div key={name} className={`file-item ${activeFile === name ? "active" : ""}`} onClick={() => setActiveFile(name)}>
                        <span className="file-icon"><Icon name="file" size={13} /></span>
                        <span style={{ flex: 1, overflow: "hidden", textOverflow: "ellipsis", whiteSpace: "nowrap" }}>{name}</span>
                        <span className={`file-ext ext-${getFileExt(name)}`}>{getFileExt(name)}</span>
                      </div>
                    ))}
                  </div>
                  <div
                    className="upload-zone"
                    onClick={() => fileInputRef.current?.click()}
                    onDrop={handleDrop}
                    onDragOver={(e) => e.preventDefault()}
                  >
                    <div className="upload-zone-icon">📁</div>
                    <p><span>Click to upload</span> or drag & drop HTML, CSS, JS files</p>
                  </div>
                </>
              )}
              {sidebarTab === "layers" && (
                <div className="sidebar-section">
                  <div className="sidebar-section-title">DOM Layers</div>
                  {layers.length === 0 && <div style={{ color: "#3A3E55", fontSize: 11, padding: "8px 6px" }}>Select an HTML file to see layers</div>}
                  {layers.map((layer, i) => (
                    <div key={i} className={`layer-item`} style={{ paddingLeft: 8 + layer.depth * 12 }}>
                      <span className="layer-tag" style={{ color: "#6B9EDE" }}>&lt;</span>
                      <span className="layer-tag">{layer.tag}</span>
                      {layer.id && <span style={{ color: "#00D4AA88", fontSize: 10 }}>#{layer.id}</span>}
                      {layer.className && typeof layer.className === "string" && layer.className.trim() && (
                        <span style={{ color: "#DE9B6B88", fontSize: 10 }}>
                          .{layer.className.trim().split(" ")[0]}
                        </span>
                      )}
                    </div>
                  ))}
                </div>
              )}
            </div>
          </div>

          {/* CANVAS / CODE / SPLIT */}
          {view === "visual" && (
            <div className="canvas-area">
              <div className="canvas-toolbar">
                <button className={`device-btn ${device === "desktop" ? "active" : ""}`} onClick={() => setDevice("desktop")} title="Desktop">
                  <Icon name="desktop" size={16} />
                </button>
                <button className={`device-btn ${device === "tablet" ? "active" : ""}`} onClick={() => setDevice("tablet")} title="Tablet">
                  <Icon name="tablet" size={16} />
                </button>
                <button className={`device-btn ${device === "mobile" ? "active" : ""}`} onClick={() => setDevice("mobile")} title="Mobile">
                  <Icon name="mobile" size={16} />
                </button>
                <div className="topbar-divider" />
                <div className="url-bar">{activeFile || "No file selected"}</div>
                <div className="spacer" />
                <div className="zoom-ctrl">
                  <button className="zoom-btn" onClick={() => setZoom(z => Math.max(25, z - 10))}>−</button>
                  <span style={{ minWidth: 36, textAlign: "center", fontFamily: "'JetBrains Mono', monospace", fontSize: 11 }}>{zoom}%</span>
                  <button className="zoom-btn" onClick={() => setZoom(z => Math.min(200, z + 10))}>+</button>
                </div>
                <button className="device-btn" onClick={() => { setSelectedEl(null); if (iframeRef.current) iframeRef.current.src = "about:blank"; setTimeout(() => { if (iframeRef.current) iframeRef.current.srcdoc = getIframeSrc(); }, 50); }}>
                  <Icon name="refresh" size={15} />
                </button>
              </div>
              {!activeFile ? (
                <div className="empty-state">
                  <div className="empty-icon">🎨</div>
                  <div className="empty-title">Start Building</div>
                  <div className="empty-sub">Upload HTML/CSS files, clone a GitHub repo, or start with a blank template to begin editing visually.</div>
                  <div className="empty-actions">
                    <button className="action-btn github" onClick={() => setGithubModal(true)}><Icon name="github" size={13} /> Clone Repo</button>
                    <button className="action-btn secondary" onClick={() => fileInputRef.current?.click()}><Icon name="upload" size={13} /> Upload Files</button>
                  </div>
                </div>
              ) : (
                <div className="canvas-wrapper">
                  <div className={`canvas-frame ${device}`} style={{ transform: `scale(${zoom / 100})`, transformOrigin: "top center" }}>
                    <iframe
                      ref={iframeRef}
                      srcDoc={getIframeSrc()}
                      width={device === "desktop" ? 1200 : device === "tablet" ? 768 : 375}
                      height={iframeHeight}
                      sandbox="allow-scripts allow-same-origin"
                      title="preview"
                    />
                  </div>
                </div>
              )}
            </div>
          )}

          {view === "code" && (
            <div className="code-editor">
              <div className="split-label" style={{ display: "flex", alignItems: "center", justifyContent: "space-between", paddingRight: 16 }}>
                <span>{activeFile || "No file selected"}</span>
                {activeFile && <button className="action-btn secondary" style={{ padding: "4px 10px" }} onClick={downloadFile}><Icon name="download" size={12} /> Download</button>}
              </div>
              <div className="code-content">
                <textarea
                  className="code-textarea"
                  value={activeContent}
                  onChange={(e) => setFiles(prev => ({ ...prev, [activeFile]: e.target.value }))}
                  spellCheck={false}
                  placeholder="// Upload or clone a file to start editing"
                />
              </div>
            </div>
          )}

          {view === "split" && (
            <div className="split-view">
              <div className="split-code">
                <div className="split-label">{activeFile || "No file"} — Code</div>
                <div className="code-content">
                  <textarea
                    className="code-textarea"
                    value={activeContent}
                    onChange={(e) => setFiles(prev => ({ ...prev, [activeFile]: e.target.value }))}
                    spellCheck={false}
                    placeholder="// Upload or clone a file to start editing"
                  />
                </div>
              </div>
              <div className="split-preview" style={{ display: "flex", flexDirection: "column" }}>
                <div className="split-label">Preview</div>
                <div style={{ flex: 1, overflow: "auto", background: "#0A0C14", padding: 16 }}>
                  {activeFile ? (
                    <iframe
                      srcDoc={getIframeSrc()}
                      style={{ width: "100%", height: "100%", border: "none", borderRadius: 6, background: "white" }}
                      sandbox="allow-scripts allow-same-origin"
                      title="preview-split"
                    />
                  ) : (
                    <div style={{ display: "flex", alignItems: "center", justifyContent: "center", height: "100%", color: "#3A3E55", fontSize: 13 }}>No file selected</div>
                  )}
                </div>
              </div>
            </div>
          )}

          {/* RIGHT PANEL */}
          {(view === "visual" || view === "split") && (
            <div className="right-panel">
              <div className="panel-header">Properties</div>
              <div className="panel-body">
                {!selectedEl ? (
                  <div className="no-selection">
                    <div className="no-selection-icon">🖱️</div>
                    <p>Click any element in the preview to inspect and edit its properties</p>
                  </div>
                ) : (
                  <>
                    <div className="prop-group">
                      <div className="prop-group-title">Element</div>
                      <div className="prop-row">
                        <span className="prop-label">Tag</span>
                        <input className="prop-input" value={selectedEl.tag} readOnly style={{ color: "#6B9EDE" }} />
                      </div>
                      {selectedEl.id && <div className="prop-row">
                        <span className="prop-label">ID</span>
                        <input className="prop-input" value={selectedEl.id} readOnly />
                      </div>}
                      {selectedEl.className && <div className="prop-row">
                        <span className="prop-label">Class</span>
                        <input className="prop-input" value={selectedEl.className} readOnly style={{ fontSize: 10 }} />
                      </div>}
                      {selectedEl.textContent && <div className="prop-row">
                        <span className="prop-label">Content</span>
                        <input className="prop-input" value={selectedEl.textContent.substring(0, 30)} readOnly />
                      </div>}
                    </div>
                    <div className="prop-group">
                      <div className="prop-group-title">Typography</div>
                      <div className="prop-row">
                        <span className="prop-label">Font Size</span>
                        <input className="prop-input" value={selectedEl.styles?.fontSize || ""} readOnly />
                      </div>
                      <div className="prop-row">
                        <span className="prop-label">Weight</span>
                        <input className="prop-input" value={selectedEl.styles?.fontWeight || ""} readOnly />
                      </div>
                      <div className="prop-row">
                        <span className="prop-label">Color</span>
                        <input className="prop-input" value={selectedEl.styles?.color || ""} readOnly />
                        <div className="color-swatch" style={{ background: selectedEl.styles?.color }} />
                      </div>
                    </div>
                    <div className="prop-group">
                      <div className="prop-group-title">Layout</div>
                      <div className="prop-row">
                        <span className="prop-label">Width</span>
                        <input className="prop-input" value={selectedEl.styles?.width || ""} readOnly />
                      </div>
                      <div className="prop-row">
                        <span className="prop-label">Height</span>
                        <input className="prop-input" value={selectedEl.styles?.height || ""} readOnly />
                      </div>
                      <div className="prop-row">
                        <span className="prop-label">Padding</span>
                        <input className="prop-input" value={selectedEl.styles?.padding || ""} readOnly />
                      </div>
                      <div className="prop-row">
                        <span className="prop-label">Margin</span>
                        <input className="prop-input" value={selectedEl.styles?.margin || ""} readOnly />
                      </div>
                    </div>
                    <div className="prop-group">
                      <div className="prop-group-title">Background</div>
                      <div className="prop-row">
                        <span className="prop-label">BG Color</span>
                        <input className="prop-input" value={selectedEl.styles?.backgroundColor || ""} readOnly />
                        <div className="color-swatch" style={{ background: selectedEl.styles?.backgroundColor }} />
                      </div>
                    </div>
                  </>
                )}
              </div>
            </div>
          )}
        </div>
      </div>

      {/* GITHUB MODAL */}
      {githubModal && (
        <div className="modal-overlay" onClick={(e) => { if (e.target === e.currentTarget) { setGithubModal(false); setCloneStatus(null); setRepoUrl(""); } }}>
          <div className="modal">
            <div className="modal-title">
              <Icon name="github" size={20} />
              Clone GitHub Repository
            </div>
            <p className="modal-sub">Paste a public GitHub repository URL to import HTML, CSS, and JS files directly into your project.</p>
            {cloneStatus && (
              <div className={`modal-status ${cloneStatus.type}`}>{cloneStatus.message}</div>
            )}
            <input
              className="modal-input"
              placeholder="https://github.com/username/repository"
              value={repoUrl}
              onChange={(e) => setRepoUrl(e.target.value)}
              onKeyDown={(e) => e.key === "Enter" && handleCloneRepo()}
              autoFocus
            />
            <p className="modal-hint">Only public repositories are supported. Web files (<code>.html</code>, <code>.css</code>, <code>.js</code>) will be imported.</p>
            <div className="modal-actions">
              <button className="action-btn secondary" onClick={() => { setGithubModal(false); setCloneStatus(null); setRepoUrl(""); }}>Cancel</button>
              <button className="action-btn primary" onClick={handleCloneRepo} disabled={!repoUrl.trim()}>
                <Icon name="github" size={13} /> Clone Repository
              </button>
            </div>
          </div>
        </div>
      )}

      <input ref={fileInputRef} type="file" multiple accept=".html,.css,.js" style={{ display: "none" }} onChange={handleFileUpload} />
      <Toast toast={toast} />
    </>
  );
}
