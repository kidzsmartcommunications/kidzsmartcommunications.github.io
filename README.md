<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Kidzsmart — Creative Brief</title>
<style>
*,*::before,*::after{box-sizing:border-box;margin:0;padding:0}
:root{
  --font:system-ui,-apple-system,'Segoe UI',sans-serif;
  --bg:#f5f4f0;
  --surface:#ffffff;
  --border:#e0ddd5;
  --border2:#c8c5bc;
  --text:#1a1917;
  --muted:#6b6960;
  --hint:#9e9c94;
  --accent:#2563EB;
  --accent-bg:#eff4ff;
  --accent-border:#bfcfff;
  --green:#16a34a;
  --green-bg:#f0fdf4;
  --green-border:#86efac;
  --red:#dc2626;
  --radius:8px;
  --radius-lg:12px;
}
body{font-family:var(--font);background:var(--bg);color:var(--text);padding:2rem 1rem;font-size:14px;line-height:1.6;}
.page{max-width:960px;margin:0 auto;}

/* Header */
.brief-header{background:var(--text);color:#fff;border-radius:var(--radius-lg);padding:2rem 2rem 1.5rem;margin-bottom:1.5rem;}
.brief-header h1{font-size:24px;font-weight:700;letter-spacing:-0.03em;margin-bottom:4px;}
.brief-header p{font-size:13px;opacity:0.65;}
.header-meta{display:flex;gap:1.5rem;margin-top:1rem;flex-wrap:wrap;}
.header-meta span{font-size:12px;opacity:0.5;letter-spacing:0.05em;text-transform:uppercase;}
.req-badge{display:inline-block;background:#ef4444;color:#fff;font-size:10px;font-weight:700;padding:2px 6px;border-radius:4px;margin-left:6px;vertical-align:middle;}

/* Nav pills */
.section-nav{display:flex;gap:6px;flex-wrap:wrap;margin-bottom:1.5rem;position:sticky;top:0;background:var(--bg);padding:0.75rem 0;z-index:10;border-bottom:1px solid var(--border);}
.nav-pill{padding:5px 12px;border-radius:20px;border:1px solid var(--border);font-size:12px;color:var(--muted);cursor:pointer;background:var(--surface);transition:all .15s;white-space:nowrap;}
.nav-pill:hover{border-color:var(--border2);color:var(--text);}
.nav-pill.active{background:var(--text);color:#fff;border-color:var(--text);}

/* Sections */
.section{background:var(--surface);border:1px solid var(--border);border-radius:var(--radius-lg);padding:1.5rem;margin-bottom:1.25rem;scroll-margin-top:70px;}
.section-header{display:flex;align-items:center;gap:10px;margin-bottom:1.25rem;padding-bottom:1rem;border-bottom:1px solid var(--border);}
.section-num{width:28px;height:28px;border-radius:50%;background:var(--text);color:#fff;display:flex;align-items:center;justify-content:center;font-size:12px;font-weight:700;flex-shrink:0;}
.section-title{font-size:16px;font-weight:600;}
.section-sub{font-size:11px;color:var(--muted);margin-top:2px;}

/* Sub sections */
.sub-section{margin-bottom:1.5rem;}
.sub-section:last-child{margin-bottom:0;}
.sub-title{font-size:12px;font-weight:600;color:var(--muted);text-transform:uppercase;letter-spacing:0.07em;margin-bottom:10px;display:flex;align-items:center;gap:6px;}
.sub-title::after{content:'';flex:1;height:1px;background:var(--border);}

/* Form fields */
.field{margin-bottom:12px;}
.field label{font-size:12px;color:var(--muted);display:block;margin-bottom:4px;font-weight:500;}
.field input[type=text],.field input[type=email],.field input[type=tel],.field input[type=date],.field input[type=number],.field select,.field textarea{
  width:100%;padding:8px 10px;border:1px solid var(--border);border-radius:var(--radius);
  font-family:var(--font);font-size:13px;color:var(--text);background:var(--surface);
  transition:border .15s;
}
.field input:focus,.field select:focus,.field textarea:focus{outline:none;border-color:var(--accent);}
.field textarea{resize:vertical;min-height:72px;line-height:1.5;}
.grid-2{display:grid;grid-template-columns:1fr 1fr;gap:12px;}
.grid-3{display:grid;grid-template-columns:1fr 1fr 1fr;gap:12px;}
.full{grid-column:1/-1;}

/* Chips (multi-select) */
.chips{display:flex;flex-wrap:wrap;gap:6px;margin-top:2px;}
.chip{display:flex;align-items:center;gap:5px;padding:5px 10px;border-radius:20px;border:1px solid var(--border);font-size:12px;color:var(--muted);cursor:pointer;background:var(--surface);transition:all .15s;user-select:none;}
.chip:hover{border-color:var(--border2);color:var(--text);}
.chip.selected{background:var(--accent-bg);border-color:var(--accent-border);color:var(--accent);}
.chip .chk{width:13px;height:13px;border-radius:3px;border:1px solid currentColor;display:flex;align-items:center;justify-content:center;font-size:9px;flex-shrink:0;opacity:.5;}
.chip.selected .chk{opacity:1;background:var(--accent);border-color:var(--accent);color:#fff;}

/* Radio pills */
.radios{display:flex;flex-wrap:wrap;gap:6px;margin-top:4px;}
.rpill{padding:5px 11px;border-radius:20px;border:1px solid var(--border);font-size:12px;color:var(--muted);cursor:pointer;background:var(--surface);transition:all .15s;user-select:none;}
.rpill:hover{border-color:var(--border2);color:var(--text);}
.rpill.selected{background:var(--accent-bg);border-color:var(--accent-border);color:var(--accent);}

/* Contact rows */
.contact-block{border:1px solid var(--border);border-radius:var(--radius);padding:1rem;margin-bottom:10px;background:var(--bg);}
.contact-block-title{font-size:12px;font-weight:600;color:var(--muted);margin-bottom:10px;}

/* Table */
.brief-table{width:100%;border-collapse:collapse;font-size:12px;}
.brief-table th{background:var(--bg);text-align:left;padding:8px 10px;font-size:11px;font-weight:600;color:var(--muted);text-transform:uppercase;letter-spacing:.05em;border:1px solid var(--border);}
.brief-table td{padding:6px 8px;border:1px solid var(--border);}
.brief-table td input{border:none;width:100%;font-size:12px;font-family:var(--font);color:var(--text);background:transparent;padding:2px;}
.brief-table td input:focus{outline:none;}
.brief-table tr:nth-child(even) td{background:var(--bg);}
.add-row{margin-top:8px;padding:5px 12px;border:1px dashed var(--border);border-radius:var(--radius);font-size:12px;color:var(--muted);cursor:pointer;background:none;font-family:var(--font);width:100%;text-align:left;}
.add-row:hover{border-color:var(--border2);color:var(--text);}

/* USP fields */
.usp-row{display:flex;align-items:center;gap:8px;margin-bottom:8px;}
.usp-row .chip{flex-shrink:0;}
.usp-row input{flex:1;padding:6px 10px;border:1px solid var(--border);border-radius:var(--radius);font-size:12px;font-family:var(--font);}
.usp-row input:focus{outline:none;border-color:var(--accent);}

/* Approval path */
.approval-steps{display:flex;flex-wrap:wrap;gap:6px;}
.astep{padding:5px 12px;border-radius:20px;border:1px solid var(--border);font-size:12px;color:var(--muted);cursor:pointer;background:var(--surface);transition:all .15s;user-select:none;}
.astep:hover{border-color:var(--border2);color:var(--text);}
.astep.selected{background:var(--green-bg);border-color:var(--green-border);color:var(--green);}

/* Risk checkboxes */
.risk-list{display:flex;flex-direction:column;gap:6px;}
.risk-item{display:flex;align-items:flex-start;gap:8px;padding:8px 10px;border:1px solid var(--border);border-radius:var(--radius);cursor:pointer;transition:all .15s;}
.risk-item:hover{background:var(--bg);}
.risk-item.checked{background:var(--accent-bg);border-color:var(--accent-border);}
.risk-item .rchk{width:16px;height:16px;border-radius:3px;border:1px solid var(--border2);display:flex;align-items:center;justify-content:center;font-size:10px;flex-shrink:0;margin-top:1px;}
.risk-item.checked .rchk{background:var(--accent);border-color:var(--accent);color:#fff;}
.risk-text{font-size:13px;color:var(--muted);}
.risk-item.checked .risk-text{color:var(--text);}

/* Footer bar */
.footer-bar{background:var(--surface);border:1px solid var(--border);border-radius:var(--radius-lg);padding:1rem 1.5rem;margin-top:1.5rem;display:flex;align-items:center;justify-content:space-between;gap:1rem;flex-wrap:wrap;position:sticky;bottom:1rem;}
.completion{font-size:13px;color:var(--muted);}
.completion strong{color:var(--text);font-size:16px;}
.btn-row{display:flex;gap:8px;}
.btn{padding:9px 18px;border-radius:var(--radius);font-size:13px;font-family:var(--font);font-weight:500;cursor:pointer;transition:all .15s;}
.btn-outline{border:1px solid var(--border);background:var(--surface);color:var(--text);}
.btn-outline:hover{background:var(--bg);}
.btn-solid{border:none;background:var(--text);color:#fff;}
.btn-solid:hover{opacity:.85;}

/* Modal */
.modal{display:none;position:fixed;inset:0;background:rgba(0,0,0,.45);align-items:center;justify-content:center;z-index:100;padding:1rem;}
.modal.open{display:flex;}
.modal-box{background:var(--surface);border-radius:var(--radius-lg);padding:1.5rem;max-width:680px;width:100%;max-height:85vh;overflow-y:auto;}
.modal-box h2{font-size:16px;font-weight:600;margin-bottom:1rem;}
.modal-pre{font-size:11px;line-height:1.8;white-space:pre-wrap;background:var(--bg);padding:1rem;border-radius:var(--radius);border:1px solid var(--border);color:var(--muted);font-family:monospace;}
.modal-close{margin-top:1rem;padding:8px 16px;border-radius:var(--radius);border:1px solid var(--border);background:var(--surface);font-size:13px;cursor:pointer;font-family:var(--font);}
@media print{
  .section-nav,.footer-bar,.modal{display:none!important;}
  body{background:white;padding:0;margin:0;}
  .page{max-width:100%;padding:0;margin:0;}
  .brief-header{border-radius:0;margin-bottom:1rem;padding:1rem 1.5rem;}
  .section{border-radius:0;border-left:none;border-right:none;border-top:none;margin-bottom:0;padding:1rem 1.5rem;page-break-inside:avoid;}
  *{-webkit-print-color-adjust:exact;print-color-adjust:exact;}
}
@media(max-width:600px){.grid-2,.grid-3{grid-template-columns:1fr;}.full{grid-column:1;}.header-meta{gap:.75rem;}}
</style>
</head>
<body>
<div class="page">

<div class="brief-header">
  <h1>Kidzsmart — Creative Brief</h1>
  <p>Fill out the following client information to support the development of the creative strategy and plan. <span class="req-badge">* Required</span></p>
  <div class="header-meta">
    <span>Version 1.0</span>
    <span>© 2026 Kidzsmart Communications</span>
  </div>
</div>

<nav class="section-nav" id="nav">
  <div class="nav-pill active" onclick="scrollTo('s1')">1 Project</div>
  <div class="nav-pill" onclick="scrollTo('s2')">2 Contacts</div>
  <div class="nav-pill" onclick="scrollTo('s3')">3 Audience</div>
  <div class="nav-pill" onclick="scrollTo('s4')">4 Messaging</div>
  <div class="nav-pill" onclick="scrollTo('s5')">5 Strategy</div>
  <div class="nav-pill" onclick="scrollTo('s6')">6 Deliverables</div>
  <div class="nav-pill" onclick="scrollTo('s7')">7 Assets</div>
  <div class="nav-pill" onclick="scrollTo('s8')">8 Schedule</div>
  <div class="nav-pill" onclick="scrollTo('s9')">9 Distribution</div>
  <div class="nav-pill" onclick="scrollTo('s10')">10 Pricing</div>
  <div class="nav-pill" onclick="scrollTo('s11')">11 Risks</div>
</nav>

<!-- SECTION 1 -->
<div class="section" id="s1">
  <div class="section-header">
    <div class="section-num">1</div>
    <div><div class="section-title">Project &amp; Client Overview</div></div>
  </div>
  <div class="grid-2">
    <div class="field"><label>Project Title <span class="req-badge">*</span></label><input type="text" id="proj-title" placeholder="e.g. Kids Menu Social Campaign"></div>
    <div class="field"><label>Client / Brand Name <span class="req-badge">*</span></label><input type="text" id="proj-client" placeholder="e.g. NORMS Restaurants"></div>
    <div class="field"><label>Program / Campaign</label><input type="text" placeholder="e.g. Summer Kids Eat Free"></div>
    <div class="field"><label>Budget &amp; Currency</label><input type="text" placeholder="e.g. $5,000 CAD"></div>
    <div class="field"><label>Estimate / Quote #</label><input type="text" placeholder="EST-2025-001"></div>
    <div class="field"><label>PO # (if any)</label><input type="text" placeholder="PO-XXXX"></div>
  </div>

  <div class="sub-section">
    <div class="sub-title">Project Type (multi-select)</div>
    <div class="chips" data-multi="true">
      <div class="chip" data-val="print"><span class="chk">✓</span>Print</div>
      <div class="chip" data-val="packaging"><span class="chk">✓</span>Packaging / POS</div>
      <div class="chip" data-val="digital"><span class="chk">✓</span>Digital</div>
      <div class="chip" data-val="marketing"><span class="chk">✓</span>Marketing</div>
      <div class="chip" data-val="advertising"><span class="chk">✓</span>Advertising</div>
      <div class="chip" data-val="brand"><span class="chk">✓</span>Brand / Identity</div>
      <div class="chip" data-val="research"><span class="chk">✓</span>Research / Strategy</div>
      <div class="chip" data-val="video"><span class="chk">✓</span>Video / Photo</div>
    </div>
  </div>

  <div class="sub-section">
    <div class="sub-title">Initiative</div>
    <div class="chips" data-multi="true">
      <div class="chip" data-val="new"><span class="chk">✓</span>New Build</div>
      <div class="chip" data-val="refresh"><span class="chk">✓</span>Refresh / Update</div>
      <div class="chip" data-val="local"><span class="chk">✓</span>Localization / Adaptation</div>
      <div class="chip" data-val="resize"><span class="chk">✓</span>Resizes / Versioning</div>
      <div class="chip" data-val="evergreen"><span class="chk">✓</span>Evergreen / Retainer</div>
    </div>
  </div>

  <div class="sub-section">
    <div class="sub-title">Summary of Project</div>
    <div class="field"><textarea placeholder="Brief description of what we're making, why, and the goal..."></textarea></div>
  </div>

  <div class="sub-section">
    <div class="sub-title">Background / Business Context</div>
    <div class="field"><textarea placeholder="Market/category context, opportunity or challenges, past learnings/benchmarks..."></textarea></div>
  </div>

  <div class="sub-section">
    <div class="sub-title">Client Pain Points &amp; Challenges</div>
    <div class="field"><label>What's keeping you up at night? What problem do you need us to solve?</label><textarea placeholder="e.g. Kids menu sales have declined, we're not reaching parents on social, our creative feels dated..." style="min-height:90px;"></textarea></div>
    <div class="field"><label>What have you already tried that hasn't worked?</label><textarea placeholder="e.g. We ran a promotion last quarter but saw no lift, our last agency's creative didn't resonate with kids..."></textarea></div>
    <div class="field"><label>What does success look like for you?</label><textarea placeholder="e.g. More families choosing us on weekends, kids asking to come back, measurable increase in kids menu orders..."></textarea></div>
  </div>

  <div class="sub-section">
    <div class="sub-title">Objectives &amp; Brand Challenges (top 3–5, SMART)</div>
    <div class="field"><input type="text" placeholder="1."></div>
    <div class="field"><input type="text" placeholder="2."></div>
    <div class="field"><input type="text" placeholder="3."></div>
    <div class="field"><input type="text" placeholder="4."></div>
    <div class="field"><input type="text" placeholder="5."></div>
  </div>

  <div class="sub-section">
    <div class="sub-title">Competitive Landscape</div>
    <div class="grid-3">
      <div class="field"><label>Competitor 1</label><input type="text" placeholder="Brand name"></div>
      <div class="field"><label>Competitor 2</label><input type="text" placeholder="Brand name"></div>
      <div class="field"><label>Competitor 3</label><input type="text" placeholder="Brand name"></div>
    </div>
    <div class="field"><label>Our Differentiators</label><textarea placeholder="What we do better or uniquely..."></textarea></div>
  </div>

  <div class="sub-section">
    <div class="sub-title">Success Metrics / KPIs (multi-select)</div>
    <div class="chips" data-multi="true">
      <div class="chip"><span class="chk">✓</span>Awareness (reach/impressions)</div>
      <div class="chip"><span class="chk">✓</span>Engagement (CTR, saves/shares)</div>
      <div class="chip"><span class="chk">✓</span>Conversion (sign-ups, orders)</div>
      <div class="chip"><span class="chk">✓</span>Sales / Lift</div>
      <div class="chip"><span class="chk">✓</span>Retention / Loyalty</div>
      <div class="chip"><span class="chk">✓</span>Brand Health (NPS/recall)</div>
    </div>
    <div class="field" style="margin-top:10px;"><label>KPI Targets (up to 4)</label><textarea placeholder="e.g. Reach 50k impressions in 30 days, CTR > 2%..."></textarea></div>
  </div>
</div>

<!-- SECTION 2 -->
<div class="section" id="s2">
  <div class="section-header">
    <div class="section-num">2</div>
    <div><div class="section-title">Contacts &amp; Stakeholders</div></div>
  </div>

  <div class="sub-section">
    <div class="sub-title">Client Contacts</div>
    <div class="grid-2">
      <div class="field"><label>Project Lead</label><input type="text" placeholder="Name"></div>
      <div class="field"><label>Email / Phone</label><input type="text" placeholder="email@client.com / 000-000-0000"></div>
      <div class="field"><label>Day-to-Day Contact</label><input type="text" placeholder="Name"></div>
      <div class="field"><label>Email / Phone</label><input type="text" placeholder="email@client.com / 000-000-0000"></div>
      <div class="field"><label>Final Approver</label><input type="text" placeholder="Name"></div>
      <div class="field"><label>Email / Phone</label><input type="text" placeholder="email@client.com / 000-000-0000"></div>
      <div class="field"><label>Legal / Compliance</label><input type="text" placeholder="Name"></div>
      <div class="field"><label>Email / Phone</label><input type="text" placeholder="email@client.com / 000-000-0000"></div>
      <div class="field"><label>Finance / Billing</label><input type="text" placeholder="Name"></div>
      <div class="field"><label>Email / Phone</label><input type="text" placeholder="email@client.com / 000-000-0000"></div>
      <div class="field"><label>Licensor / Partner</label><input type="text" placeholder="Name"></div>
      <div class="field"><label>Email / Phone</label><input type="text" placeholder="email@client.com / 000-000-0000"></div>
    </div>
  </div>

  <div class="sub-section">
    <div class="sub-title">Kidzsmart Team</div>
    <div class="grid-2">
      <div class="field"><label>Account Lead (AE)</label><input type="text" placeholder="Name"></div>
      <div class="field"><label>Project Manager / Producer</label><input type="text" placeholder="Name"></div>
      <div class="field"><label>Creative Director</label><input type="text" placeholder="Name"></div>
      <div class="field"><label>Art / Design Lead</label><input type="text" placeholder="Name"></div>
      <div class="field"><label>Copy / Content Lead</label><input type="text" placeholder="Name"></div>
      <div class="field"><label>Dev / Tech Lead</label><input type="text" placeholder="Name (if digital)"></div>
      <div class="field"><label>QA / Accessibility Lead</label><input type="text" placeholder="Name"></div>
      <div class="field"><label>Sales Contact / Decision Maker</label><input type="text" placeholder="Name"></div>
    </div>
    <div class="grid-2">
      <div class="field"><label>Created By <span class="req-badge">*</span></label><input type="text" placeholder="Your name"></div>
      <div class="field"><label>Created On <span class="req-badge">*</span></label><input type="date"></div>
    </div>
  </div>

  <div class="sub-section">
    <div class="sub-title">Comms &amp; Cadence</div>
    <div class="field"><label>Communication Channel</label>
      <div class="chips" data-multi="true">
        <div class="chip"><span class="chk">✓</span>Email</div>
        <div class="chip"><span class="chk">✓</span>Teams Channel</div>
        <div class="chip"><span class="chk">✓</span>Both</div>
      </div>
    </div>
    <div class="grid-2">
      <div class="field"><label>Status Cadence</label>
        <div class="chips" data-multi="false">
          <div class="chip"><span class="chk">✓</span>Weekly</div>
          <div class="chip"><span class="chk">✓</span>Bi-weekly</div>
        </div>
      </div>
      <div class="field"><label>Day / Time</label><input type="text" placeholder="e.g. Tuesdays at 10am ET"></div>
      <div class="field"><label>File Location</label>
        <div class="chips" data-multi="false">
          <div class="chip"><span class="chk">✓</span>Teams</div>
          <div class="chip"><span class="chk">✓</span>FP</div>
          <div class="chip"><span class="chk">✓</span>Other</div>
        </div>
      </div>
      <div class="field"><label>PO / Finance Contact</label><input type="text" placeholder="Name + email"></div>
    </div>
  </div>

  <div class="sub-section">
    <div class="sub-title">Approval Path (tick all stages in scope)</div>
    <div class="approval-steps">
      <div class="astep">Brief sign-off (Client)</div>
      <div class="astep">Concept / Key Visual</div>
      <div class="astep">Round 1 Creative</div>
      <div class="astep">Round 2 / Pre-final</div>
      <div class="astep">Final Art / Pre-press</div>
      <div class="astep">Proofs / QA</div>
      <div class="astep">Go-Live / Release</div>
    </div>
    <div class="grid-2" style="margin-top:12px;">
      <div class="field"><label>Approver Count</label><input type="number" min="1" max="10" placeholder="e.g. 2"></div>
      <div class="field"><label>Turnaround SLA</label>
        <div class="chips" data-multi="false">
          <div class="chip"><span class="chk">✓</span>1 BD</div>
          <div class="chip"><span class="chk">✓</span>2 BD</div>
          <div class="chip"><span class="chk">✓</span>3 BD</div>
          <div class="chip"><span class="chk">✓</span>Other</div>
        </div>
      </div>
      <div class="field"><label>Primary Approver(s)</label><input type="text" placeholder="Names"></div>
      <div class="field"><label>Backup Approver</label><input type="text" placeholder="Name"></div>
    </div>
    <div class="field"><label>Feedback Rule</label>
      <div class="chips" data-multi="false">
        <div class="chip"><span class="chk">✓</span>Consolidated feedback in one round</div>
      </div>
    </div>
  </div>
</div>

<!-- SECTION 3 -->
<div class="section" id="s3">
  <div class="section-header">
    <div class="section-num">3</div>
    <div><div class="section-title">Audience &amp; Insights</div></div>
  </div>

  <div class="sub-section">
    <div class="sub-title">Primary Audience <span class="req-badge" style="text-transform:none;font-size:10px;">* multi-select for co-viewership</span></div>
    <div class="chips" data-multi="true">
      <div class="chip"><span class="chk">✓</span>Kids 2–4 (Toddlers/Preschool)</div>
      <div class="chip"><span class="chk">✓</span>Kids 5–7 (Early Primary)</div>
      <div class="chip"><span class="chk">✓</span>Kids 8–10 (Tween)</div>
      <div class="chip"><span class="chk">✓</span>Teens 11–13</div>
      <div class="chip"><span class="chk">✓</span>Parents / Caregivers</div>
      <div class="chip"><span class="chk">✓</span>Educators</div>
      <div class="chip"><span class="chk">✓</span>Restaurant / QSR Guests</div>
      <div class="chip"><span class="chk">✓</span>Retail / Grocery Decision-Makers</div>
      <div class="chip"><span class="chk">✓</span>B2B (Franchisees/Corporate)</div>
    </div>
    <div class="field" style="margin-top:8px;"><label>Other audience</label><input type="text" placeholder="Specify if not listed above"></div>
  </div>

  <div class="sub-section">
    <div class="sub-title">Secondary Audience (multi-select)</div>
    <div class="chips" data-multi="true">
      <div class="chip"><span class="chk">✓</span>Kids 2–4</div>
      <div class="chip"><span class="chk">✓</span>Kids 5–7</div>
      <div class="chip"><span class="chk">✓</span>Kids 8–10</div>
      <div class="chip"><span class="chk">✓</span>Teens 11–13</div>
      <div class="chip"><span class="chk">✓</span>Parents</div>
      <div class="chip"><span class="chk">✓</span>Educators</div>
      <div class="chip"><span class="chk">✓</span>QSR Guests</div>
      <div class="chip"><span class="chk">✓</span>Retail</div>
      <div class="chip"><span class="chk">✓</span>B2B</div>
    </div>
  </div>

  <div class="sub-section">
    <div class="sub-title">Geography / Markets (multi-select)</div>
    <div class="chips" data-multi="true">
      <div class="chip"><span class="chk">✓</span>Canada (EN)</div>
      <div class="chip"><span class="chk">✓</span>Canada (FR)</div>
      <div class="chip"><span class="chk">✓</span>USA</div>
      <div class="chip"><span class="chk">✓</span>UK</div>
      <div class="chip"><span class="chk">✓</span>EU</div>
      <div class="chip"><span class="chk">✓</span>APAC</div>
      <div class="chip"><span class="chk">✓</span>LATAM</div>
      <div class="chip"><span class="chk">✓</span>GCC</div>
      <div class="chip"><span class="chk">✓</span>Global</div>
    </div>
    <div class="field" style="margin-top:8px;"><label>Market notes</label><input type="text" placeholder="e.g. Focus on Southern California, chain-wide"></div>
  </div>

  <div class="sub-section">
    <div class="sub-title">Language &amp; Accessibility (multi-select)</div>
    <div class="chips" data-multi="true">
      <div class="chip"><span class="chk">✓</span>EN</div>
      <div class="chip"><span class="chk">✓</span>FR</div>
      <div class="chip"><span class="chk">✓</span>ES</div>
      <div class="chip"><span class="chk">✓</span>ZH Simplified</div>
      <div class="chip"><span class="chk">✓</span>Translation required</div>
      <div class="chip"><span class="chk">✓</span>WCAG A/AA</div>
      <div class="chip"><span class="chk">✓</span>Subtitles / Captions</div>
      <div class="chip"><span class="chk">✓</span>Alt text</div>
    </div>
  </div>

  <div class="sub-section">
    <div class="sub-title">Demographics &amp; Psychographics</div>
    <div class="grid-2">
      <div class="field"><label>Age range</label><input type="text" placeholder="e.g. 25–45"></div>
      <div class="field"><label>Gender mix</label><input type="text" placeholder="e.g. 70% female"></div>
      <div class="field"><label>HH Income</label><input type="text" placeholder="e.g. $50–80k"></div>
      <div class="field"><label>Family composition</label><input type="text" placeholder="e.g. 2 kids, dual income"></div>
    </div>
    <div class="field"><label>Mindsets (multi-select)</label>
      <div class="chips" data-multi="true" style="margin-top:6px;">
        <div class="chip"><span class="chk">✓</span>Value-seeker</div>
        <div class="chip"><span class="chk">✓</span>Premium</div>
        <div class="chip"><span class="chk">✓</span>Health-conscious</div>
        <div class="chip"><span class="chk">✓</span>Eco-minded</div>
        <div class="chip"><span class="chk">✓</span>Promo-driven</div>
        <div class="chip"><span class="chk">✓</span>Convenience-driven</div>
        <div class="chip"><span class="chk">✓</span>Adventurous / Explorer</div>
        <div class="chip"><span class="chk">✓</span>Education-focused</div>
        <div class="chip"><span class="chk">✓</span>Collectors / Loyalty</div>
      </div>
    </div>
  </div>

  <div class="sub-section">
    <div class="sub-title">Consumer / Shopper Insights</div>
    <div class="field"><label>Triggers (multi-select)</label>
      <div class="chips" data-multi="true" style="margin-top:6px;">
        <div class="chip"><span class="chk">✓</span>New / limited</div>
        <div class="chip"><span class="chk">✓</span>Seasonal</div>
        <div class="chip"><span class="chk">✓</span>Educational skills</div>
        <div class="chip"><span class="chk">✓</span>Fun / play</div>
        <div class="chip"><span class="chk">✓</span>Social-shareable</div>
      </div>
    </div>
    <div class="field"><label>Barriers (multi-select)</label>
      <div class="chips" data-multi="true" style="margin-top:6px;">
        <div class="chip"><span class="chk">✓</span>Price</div>
        <div class="chip"><span class="chk">✓</span>Time</div>
        <div class="chip"><span class="chk">✓</span>Access</div>
        <div class="chip"><span class="chk">✓</span>Complexity</div>
        <div class="chip"><span class="chk">✓</span>Dietary / restrictions</div>
        <div class="chip"><span class="chk">✓</span>Screen-time concerns</div>
      </div>
    </div>
    <div class="field"><label>Decision Path (multi-select)</label>
      <div class="chips" data-multi="true" style="margin-top:6px;">
        <div class="chip"><span class="chk">✓</span>Online research</div>
        <div class="chip"><span class="chk">✓</span>In-store impulse</div>
        <div class="chip"><span class="chk">✓</span>Word-of-mouth</div>
        <div class="chip"><span class="chk">✓</span>Social media</div>
        <div class="chip"><span class="chk">✓</span>Reviews</div>
      </div>
    </div>
    <div class="field"><label>Top insights</label><textarea placeholder="Key consumer insights as bullet points..."></textarea></div>
  </div>

  <div class="sub-section">
    <div class="sub-title">Positioning &amp; Tone</div>
    <div class="field"><label>Positioning Statement</label><textarea placeholder="For [target] who [need], [brand] is the [frame of reference] that [primary benefit], because [reason to believe]."></textarea></div>
    <div class="field"><label>Tone / Brand Character (multi-select)</label>
      <div class="chips" data-multi="true" style="margin-top:6px;">
        <div class="chip"><span class="chk">✓</span>Friendly</div>
        <div class="chip"><span class="chk">✓</span>Playful</div>
        <div class="chip"><span class="chk">✓</span>Educational</div>
        <div class="chip"><span class="chk">✓</span>Bold</div>
        <div class="chip"><span class="chk">✓</span>Premium</div>
        <div class="chip"><span class="chk">✓</span>Clean</div>
        <div class="chip"><span class="chk">✓</span>Energetic</div>
        <div class="chip"><span class="chk">✓</span>Trustworthy</div>
        <div class="chip"><span class="chk">✓</span>Whimsical</div>
        <div class="chip"><span class="chk">✓</span>Inclusive</div>
        <div class="chip"><span class="chk">✓</span>Adventurous</div>
        <div class="chip"><span class="chk">✓</span>Tech-forward</div>
        <div class="chip"><span class="chk">✓</span>Natural / Wholesome</div>
        <div class="chip"><span class="chk">✓</span>Community-driven</div>
        <div class="chip"><span class="chk">✓</span>Authoritative</div>
      </div>
    </div>
    <div class="field"><label>Tone notes</label><input type="text" placeholder="Any additional tone descriptors or notes..."></div>
  </div>
</div>

<!-- SECTION 4 -->
<div class="section" id="s4">
  <div class="section-header">
    <div class="section-num">4</div>
    <div><div class="section-title">Messaging &amp; Proof</div></div>
  </div>

  <div class="sub-section">
    <div class="sub-title">Top Messages (rank by priority, max 3)</div>
    <div class="grid-2">
      <div class="field"><label>Message 1 — Primary / Hero</label><input type="text" placeholder="e.g. Come dine with us"></div>
      <div class="field"><label>Char limit / Alt line</label><input type="text" placeholder="e.g. 60 chars / alternate headline"></div>
      <div class="field"><label>Message 2 — Support</label><input type="text" placeholder="Supporting message"></div>
      <div class="field"><label>Char limit / Alt line</label><input type="text" placeholder="e.g. 120 chars / alternate line"></div>
      <div class="field"><label>Message 3 — Support</label><input type="text" placeholder="Supporting message"></div>
      <div class="field"><label>Char limit / Alt line</label><input type="text" placeholder="e.g. 120 chars / alternate line"></div>
    </div>
  </div>

  <div class="sub-section">
    <div class="sub-title">Call to Action (multi-select)</div>
    <div class="chips" data-multi="true">
      <div class="chip"><span class="chk">✓</span>Buy Now</div>
      <div class="chip"><span class="chk">✓</span>Learn More</div>
      <div class="chip"><span class="chk">✓</span>RSVP / Book</div>
      <div class="chip"><span class="chk">✓</span>Download</div>
      <div class="chip"><span class="chk">✓</span>Visit In-store</div>
      <div class="chip"><span class="chk">✓</span>Subscribe / Join</div>
      <div class="chip"><span class="chk">✓</span>Try Me</div>
      <div class="chip"><span class="chk">✓</span>Enter to Win</div>
      <div class="chip"><span class="chk">✓</span>Contact Us</div>
      <div class="chip"><span class="chk">✓</span>Find a Location</div>
      <div class="chip"><span class="chk">✓</span>Come Dine With Us</div>
    </div>
    <div class="field" style="margin-top:8px;"><label>Custom CTA</label><input type="text" placeholder="e.g. Order your kids meal today"></div>
  </div>

  <div class="sub-section">
    <div class="sub-title">Unique Selling Points (USPs)</div>
    <div class="usp-row"><div class="chip" onclick="this.classList.toggle('selected')"><span class="chk">✓</span>Product / Feature advantage</div><input type="text" placeholder="Describe..."></div>
    <div class="usp-row"><div class="chip" onclick="this.classList.toggle('selected')"><span class="chk">✓</span>Value / Price</div><input type="text" placeholder="Describe..."></div>
    <div class="usp-row"><div class="chip" onclick="this.classList.toggle('selected')"><span class="chk">✓</span>Quality / Safety</div><input type="text" placeholder="Describe..."></div>
    <div class="usp-row"><div class="chip" onclick="this.classList.toggle('selected')"><span class="chk">✓</span>Sustainability / Ethics</div><input type="text" placeholder="Describe..."></div>
    <div class="usp-row"><div class="chip" onclick="this.classList.toggle('selected')"><span class="chk">✓</span>Education / Skill-building</div><input type="text" placeholder="Describe..."></div>
    <div class="usp-row"><div class="chip" onclick="this.classList.toggle('selected')"><span class="chk">✓</span>Service / Speed / Availability</div><input type="text" placeholder="Describe..."></div>
    <div class="usp-row"><div class="chip" onclick="this.classList.toggle('selected')"><span class="chk">✓</span>Personalization / Selection</div><input type="text" placeholder="Describe..."></div>
  </div>

  <div class="sub-section">
    <div class="sub-title">Reasons to Believe (RTBs)</div>
    <div class="chips" data-multi="true">
      <div class="chip"><span class="chk">✓</span>Feature / spec</div>
      <div class="chip"><span class="chk">✓</span>Data / stat</div>
      <div class="chip"><span class="chk">✓</span>Certification / compliance</div>
      <div class="chip"><span class="chk">✓</span>Award / press</div>
      <div class="chip"><span class="chk">✓</span>Case study / testimonial</div>
    </div>
  </div>

  <div class="sub-section">
    <div class="sub-title">Mandatory Copy &amp; Legal</div>
    <div class="chips" data-multi="true">
      <div class="chip"><span class="chk">✓</span>Brand / Campaign end line required</div>
      <div class="chip"><span class="chk">✓</span>Trademark / ® / ™ confirmed</div>
      <div class="chip"><span class="chk">✓</span>Licensor / Partner mandatories</div>
      <div class="chip"><span class="chk">✓</span>Age grading / Safety icons</div>
      <div class="chip"><span class="chk">✓</span>Nutrition / Allergen statements</div>
      <div class="chip"><span class="chk">✓</span>Sweepstakes / Contest rules</div>
    </div>
    <div class="field" style="margin-top:8px;"><label>Notes</label><textarea placeholder="Any mandatory copy details or legal notes..."></textarea></div>
  </div>
</div>

<!-- SECTION 5 -->
<div class="section" id="s5">
  <div class="section-header">
    <div class="section-num">5</div>
    <div><div class="section-title">Strategy &amp; Creative Direction</div></div>
  </div>

  <div class="sub-section">
    <div class="sub-title">Strategy Summary</div>
    <div class="grid-2">
      <div class="field"><label>Single-minded proposition</label><input type="text" placeholder="The one thing we want people to take away..."></div>
      <div class="field"><label>Desired response (think/feel/do)</label><input type="text" placeholder="e.g. Feel excited, visit the diner this week"></div>
      <div class="field"><label>Key insight (from Audience section)</label><input type="text" placeholder="e.g. Moms want easy wins with kids"></div>
      <div class="field"><label>Tied to KPI</label><input type="text" placeholder="e.g. Drives in-store visits metric"></div>
    </div>
  </div>

  <div class="sub-section">
    <div class="sub-title">Core Creative Theme / Big Idea</div>
    <div class="grid-2">
      <div class="field"><label>Working title</label><input type="text" placeholder="e.g. Where Little Appetites Come Alive"></div>
      <div class="field"><label>One-liner</label><input type="text" placeholder="Brief summary of the creative concept..."></div>
      <div class="field full"><label>Proof / RTB that supports the idea</label><input type="text" placeholder="What evidence backs this creative direction?"></div>
    </div>
  </div>

  <div class="sub-section">
    <div class="sub-title">Style &amp; Tone (multi-select)</div>
    <div class="chips" data-multi="true">
      <div class="chip"><span class="chk">✓</span>Clean / Modern</div>
      <div class="chip"><span class="chk">✓</span>Playful</div>
      <div class="chip"><span class="chk">✓</span>Educational</div>
      <div class="chip"><span class="chk">✓</span>Premium</div>
      <div class="chip"><span class="chk">✓</span>Bold</div>
      <div class="chip"><span class="chk">✓</span>Whimsical</div>
      <div class="chip"><span class="chk">✓</span>Natural / Wholesome</div>
      <div class="chip"><span class="chk">✓</span>Tech-forward</div>
      <div class="chip"><span class="chk">✓</span>Friendly</div>
    </div>
    <div class="field" style="margin-top:8px;"><label>Other style keywords</label><input type="text" placeholder="e.g. retro-cool, nostalgic, Googie vibes..."></div>
  </div>

  <div class="sub-section">
    <div class="sub-title">Visual Direction</div>
    <div class="grid-2">
      <div class="field"><label>Approach (multi-select)</label>
        <div class="chips" data-multi="true" style="margin-top:6px;">
          <div class="chip"><span class="chk">✓</span>Photography</div>
          <div class="chip"><span class="chk">✓</span>Illustration</div>
          <div class="chip"><span class="chk">✓</span>Mixed</div>
        </div>
      </div>
      <div class="field"><label>Illustration style</label>
        <div class="chips" data-multi="true" style="margin-top:6px;">
          <div class="chip"><span class="chk">✓</span>Line</div>
          <div class="chip"><span class="chk">✓</span>Flat</div>
          <div class="chip"><span class="chk">✓</span>3D</div>
          <div class="chip"><span class="chk">✓</span>Hand-drawn</div>
        </div>
      </div>
      <div class="field"><label>Photography type</label>
        <div class="chips" data-multi="true" style="margin-top:6px;">
          <div class="chip"><span class="chk">✓</span>Lifestyle</div>
          <div class="chip"><span class="chk">✓</span>Studio</div>
          <div class="chip"><span class="chk">✓</span>Product-led</div>
        </div>
      </div>
      <div class="field"><label>Iconography</label>
        <div class="chips" data-multi="true" style="margin-top:6px;">
          <div class="chip"><span class="chk">✓</span>Simple / Outline</div>
          <div class="chip"><span class="chk">✓</span>Filled</div>
        </div>
      </div>
      <div class="field"><label>Primary Color (HEX/PMS)</label><input type="text" placeholder="#RRGGBB or PMS 000"></div>
      <div class="field"><label>Secondary Color (HEX/PMS)</label><input type="text" placeholder="#RRGGBB or PMS 000"></div>
      <div class="field full"><label>Typography guidance</label><input type="text" placeholder="e.g. Use brand fonts from guide; headline in bold, body in regular..."></div>
    </div>
  </div>

  <div class="sub-section">
    <div class="sub-title">Accessibility &amp; Compliance</div>
    <div class="chips" data-multi="true">
      <div class="chip"><span class="chk">✓</span>Alt text on all key images (≤125 chars)</div>
      <div class="chip"><span class="chk">✓</span>WCAG captions on video</div>
      <div class="chip"><span class="chk">✓</span>Color contrast AA (≥4.5:1)</div>
      <div class="chip"><span class="chk">✓</span>Age-grading / safety icons</div>
      <div class="chip"><span class="chk">✓</span>Licensor approvals needed</div>
      <div class="chip"><span class="chk">✓</span>COPPA (kids &lt;13)</div>
      <div class="chip"><span class="chk">✓</span>CARU compliance</div>
    </div>
    <div class="field" style="margin-top:8px;"><label>Notes</label><textarea placeholder="Any specific compliance requirements or notes..."></textarea></div>
  </div>

  <div class="sub-section">
    <div class="sub-title">'Wow' / Hero Moment</div>
    <div class="chips" data-multi="true">
      <div class="chip"><span class="chk">✓</span>Interactivity / Collectability</div>
      <div class="chip"><span class="chk">✓</span>Before / After</div>
      <div class="chip"><span class="chk">✓</span>Try-Me</div>
      <div class="chip"><span class="chk">✓</span>Surprise / Reveal</div>
      <div class="chip"><span class="chk">✓</span>Learning Outcome</div>
      <div class="chip"><span class="chk">✓</span>Community / Sharing</div>
    </div>
    <div class="field" style="margin-top:8px;"><label>Describe the moment</label><textarea placeholder="What's the one unforgettable thing we want to create?"></textarea></div>
  </div>

  <div class="sub-section">
    <div class="sub-title">References</div>
    <div class="grid-2">
      <div class="field"><label>Visual examples supplied?</label>
        <div class="chips" data-multi="false" style="margin-top:6px;">
          <div class="chip"><span class="chk">✓</span>Yes</div>
          <div class="chip"><span class="chk">✓</span>No</div>
        </div>
      </div>
      <div class="field"><label>Reference links</label><input type="text" placeholder="https://..."></div>
      <div class="field full"><label>Mood board links / files</label><input type="text" placeholder="https:// or file path..."></div>
    </div>
  </div>
</div>

<!-- SECTION 6 -->
<div class="section" id="s6">
  <div class="section-header">
    <div class="section-num">6</div>
    <div><div class="section-title">Deliverables &amp; Scope</div></div>
  </div>

  <div class="sub-section">
    <div class="sub-title">Primary Categories (multi-select)</div>
    <div class="chips" data-multi="true">
      <div class="chip"><span class="chk">✓</span>Print</div>
      <div class="chip"><span class="chk">✓</span>Digital</div>
      <div class="chip"><span class="chk">✓</span>Marketing</div>
      <div class="chip"><span class="chk">✓</span>Advertising</div>
      <div class="chip"><span class="chk">✓</span>Brand / Identity</div>
      <div class="chip"><span class="chk">✓</span>Research / Strategy</div>
      <div class="chip"><span class="chk">✓</span>Packaging / POS</div>
      <div class="chip"><span class="chk">✓</span>Video / Photo</div>
    </div>
  </div>

  <div class="sub-section">
    <div class="sub-title">If Print (multi-select)</div>
    <div class="chips" data-multi="true">
      <div class="chip"><span class="chk">✓</span>Activity Book</div>
      <div class="chip"><span class="chk">✓</span>Menu</div>
      <div class="chip"><span class="chk">✓</span>Placemat</div>
      <div class="chip"><span class="chk">✓</span>Brochure / One-pager</div>
      <div class="chip"><span class="chk">✓</span>Poster / Banner</div>
      <div class="chip"><span class="chk">✓</span>POS / Signage</div>
      <div class="chip"><span class="chk">✓</span>Stickers / Labels</div>
      <div class="chip"><span class="chk">✓</span>Packaging</div>
      <div class="chip"><span class="chk">✓</span>Tradeshow / Booth</div>
    </div>
    <div style="margin-top:12px;"><div class="sub-title" style="font-size:11px;">Print Specs</div>
    <div class="grid-2">
      <div class="field"><label>Print Quantity (# units)</label><input type="text" placeholder="e.g. 10,000"></div>
      <div class="field"><label>Page count / # Versions</label><input type="text" placeholder="e.g. 4 pages / 2 versions"></div>
      <div class="field"><label>Trim size</label><input type="text" placeholder='e.g. 8.5" x 11"'></div>
      <div class="field"><label>Color</label>
        <div class="chips" data-multi="true" style="margin-top:4px;">
          <div class="chip"><span class="chk">✓</span>CMYK</div>
          <div class="chip"><span class="chk">✓</span>+Spot/PMS</div>
          <div class="chip"><span class="chk">✓</span>300 dpi</div>
        </div>
      </div>
      <div class="field"><label>Stock</label>
        <div class="chips" data-multi="true" style="margin-top:4px;">
          <div class="chip"><span class="chk">✓</span>Uncoated</div>
          <div class="chip"><span class="chk">✓</span>Silk</div>
          <div class="chip"><span class="chk">✓</span>Gloss</div>
        </div>
      </div>
      <div class="field"><label>Finishes (multi-select)</label>
        <div class="chips" data-multi="true" style="margin-top:4px;">
          <div class="chip"><span class="chk">✓</span>Aqueous</div>
          <div class="chip"><span class="chk">✓</span>UV</div>
          <div class="chip"><span class="chk">✓</span>Soft-touch</div>
          <div class="chip"><span class="chk">✓</span>Matte</div>
          <div class="chip"><span class="chk">✓</span>Gloss</div>
          <div class="chip"><span class="chk">✓</span>Foil</div>
          <div class="chip"><span class="chk">✓</span>Emboss / Deboss</div>
          <div class="chip"><span class="chk">✓</span>Die-cut</div>
          <div class="chip"><span class="chk">✓</span>Perforation</div>
        </div>
      </div>
      <div class="field"><label>Proofs</label>
        <div class="chips" data-multi="true" style="margin-top:4px;">
          <div class="chip"><span class="chk">✓</span>PDF soft</div>
          <div class="chip"><span class="chk">✓</span>Color-match hard proof</div>
          <div class="chip"><span class="chk">✓</span>Press check</div>
        </div>
      </div>
      <div class="field"><label>Ship to</label><input type="text" placeholder="Address / DC + attn:"></div>
    </div></div>
  </div>

  <div class="sub-section">
    <div class="sub-title">If Digital (multi-select)</div>
    <div class="chips" data-multi="true">
      <div class="chip"><span class="chk">✓</span>Website</div>
      <div class="chip"><span class="chk">✓</span>Landing / Microsite</div>
      <div class="chip"><span class="chk">✓</span>App (iOS/Android)</div>
      <div class="chip"><span class="chk">✓</span>Email / CRM</div>
      <div class="chip"><span class="chk">✓</span>Social (organic)</div>
      <div class="chip"><span class="chk">✓</span>Social Ads</div>
      <div class="chip"><span class="chk">✓</span>Display Ads (static/HTML5)</div>
      <div class="chip"><span class="chk">✓</span>Video / Motion</div>
      <div class="chip"><span class="chk">✓</span>Interactive PDF</div>
    </div>

    <div style="margin-top:12px;"><div class="sub-title" style="font-size:11px;">Social Channels &amp; Placements</div>
    <div class="grid-2">
      <div class="field"><label>Instagram</label>
        <div class="chips" data-multi="true" style="margin-top:4px;">
          <div class="chip"><span class="chk">✓</span>Feed</div><div class="chip"><span class="chk">✓</span>Reels</div><div class="chip"><span class="chk">✓</span>Stories</div><div class="chip"><span class="chk">✓</span>Explore</div>
        </div>
      </div>
      <div class="field"><label>Facebook</label>
        <div class="chips" data-multi="true" style="margin-top:4px;">
          <div class="chip"><span class="chk">✓</span>Feed</div><div class="chip"><span class="chk">✓</span>Reels</div><div class="chip"><span class="chk">✓</span>Stories</div><div class="chip"><span class="chk">✓</span>Right Column</div>
        </div>
      </div>
      <div class="field"><label>TikTok</label>
        <div class="chips" data-multi="true" style="margin-top:4px;">
          <div class="chip"><span class="chk">✓</span>In-feed</div><div class="chip"><span class="chk">✓</span>TopView</div><div class="chip"><span class="chk">✓</span>Spark (creator)</div>
        </div>
      </div>
      <div class="field"><label>YouTube</label>
        <div class="chips" data-multi="true" style="margin-top:4px;">
          <div class="chip"><span class="chk">✓</span>Shorts</div><div class="chip"><span class="chk">✓</span>In-stream skippable</div><div class="chip"><span class="chk">✓</span>Non-skippable</div><div class="chip"><span class="chk">✓</span>Bumper</div>
        </div>
      </div>
      <div class="field"><label>X (Twitter)</label>
        <div class="chips" data-multi="true" style="margin-top:4px;">
          <div class="chip"><span class="chk">✓</span>Image</div><div class="chip"><span class="chk">✓</span>Video</div><div class="chip"><span class="chk">✓</span>Carousel</div>
        </div>
      </div>
      <div class="field"><label>Pinterest / LinkedIn</label>
        <div class="chips" data-multi="true" style="margin-top:4px;">
          <div class="chip"><span class="chk">✓</span>Pins</div><div class="chip"><span class="chk">✓</span>LI Feed / Video</div>
        </div>
      </div>
    </div></div>

    <div style="margin-top:12px;"><div class="sub-title" style="font-size:11px;">Aspect Ratios &amp; Durations</div>
    <div class="grid-2">
      <div class="field"><label>Aspect Ratios (multi-select)</label>
        <div class="chips" data-multi="true" style="margin-top:4px;">
          <div class="chip"><span class="chk">✓</span>1:1 (1080×1080)</div>
          <div class="chip"><span class="chk">✓</span>4:5 (1080×1350)</div>
          <div class="chip"><span class="chk">✓</span>9:16 (1080×1920)</div>
          <div class="chip"><span class="chk">✓</span>16:9 (1920×1080)</div>
        </div>
      </div>
      <div class="field"><label>Video Durations (multi-select)</label>
        <div class="chips" data-multi="true" style="margin-top:4px;">
          <div class="chip"><span class="chk">✓</span>:07 Bumper</div>
          <div class="chip"><span class="chk">✓</span>:10 Interstitial</div>
          <div class="chip"><span class="chk">✓</span>:15 Short</div>
          <div class="chip"><span class="chk">✓</span>:30 Full</div>
          <div class="chip"><span class="chk">✓</span>2 min</div>
          <div class="chip"><span class="chk">✓</span>Short Form (2–10 min)</div>
        </div>
      </div>
    </div></div>

    <div style="margin-top:12px;"><div class="sub-title" style="font-size:11px;">Display Ads / IAB sizes (multi-select)</div>
    <div class="chips" data-multi="true">
      <div class="chip"><span class="chk">✓</span>300×250</div>
      <div class="chip"><span class="chk">✓</span>300×600</div>
      <div class="chip"><span class="chk">✓</span>160×600</div>
      <div class="chip"><span class="chk">✓</span>728×90</div>
      <div class="chip"><span class="chk">✓</span>970×250</div>
      <div class="chip"><span class="chk">✓</span>970×90</div>
      <div class="chip"><span class="chk">✓</span>320×50</div>
      <div class="chip"><span class="chk">✓</span>336×280</div>
    </div></div>

    <div class="grid-2" style="margin-top:12px;">
      <div class="field"><label>File Formats — Static</label>
        <div class="chips" data-multi="true" style="margin-top:4px;">
          <div class="chip"><span class="chk">✓</span>PNG</div><div class="chip"><span class="chk">✓</span>JPG</div><div class="chip"><span class="chk">✓</span>SVG</div>
        </div>
      </div>
      <div class="field"><label>File Formats — Motion</label>
        <div class="chips" data-multi="true" style="margin-top:4px;">
          <div class="chip"><span class="chk">✓</span>MP4 (H.264)</div><div class="chip"><span class="chk">✓</span>MOV</div><div class="chip"><span class="chk">✓</span>GIF</div>
        </div>
      </div>
      <div class="field"><label>Captions / Accessibility</label>
        <div class="chips" data-multi="true" style="margin-top:4px;">
          <div class="chip"><span class="chk">✓</span>WCAG captions (.srt/.vtt)</div>
          <div class="chip"><span class="chk">✓</span>Alt text (≤125 chars)</div>
        </div>
      </div>
      <div class="field"><label>Tracking</label>
        <div class="chips" data-multi="true" style="margin-top:4px;">
          <div class="chip"><span class="chk">✓</span>GA4 / UTMs</div>
          <div class="chip"><span class="chk">✓</span>Meta pixel</div>
          <div class="chip"><span class="chk">✓</span>Google tag</div>
          <div class="chip"><span class="chk">✓</span>TikTok pixel</div>
        </div>
      </div>
    </div>
  </div>

  <div class="sub-section">
    <div class="sub-title">Required Disciplines (multi-select)</div>
    <div class="chips" data-multi="true">
      <div class="chip"><span class="chk">✓</span>Strategy</div>
      <div class="chip"><span class="chk">✓</span>Creative Direction</div>
      <div class="chip"><span class="chk">✓</span>Copywriting</div>
      <div class="chip"><span class="chk">✓</span>Design</div>
      <div class="chip"><span class="chk">✓</span>Illustration</div>
      <div class="chip"><span class="chk">✓</span>Photography</div>
      <div class="chip"><span class="chk">✓</span>Motion / Animation</div>
      <div class="chip"><span class="chk">✓</span>Dev / Engineering</div>
      <div class="chip"><span class="chk">✓</span>QA / Testing</div>
      <div class="chip"><span class="chk">✓</span>Translation / Localization</div>
      <div class="chip"><span class="chk">✓</span>Accessibility (WCAG/AODA)</div>
    </div>
  </div>

  <div class="sub-section">
    <div class="sub-title">Overall Deliverables Table</div>
    <table class="brief-table" id="deliv-table">
      <thead><tr><th>Deliverable</th><th>Format / Spec</th><th>Qty / Versions</th><th>Language(s)</th><th>Due Date</th><th>Notes</th></tr></thead>
      <tbody>
        <tr><td><input type="text" placeholder="e.g. IG Feed Post"></td><td><input type="text" placeholder="1080×1080 PNG"></td><td><input type="text" placeholder="2"></td><td><input type="text" placeholder="EN"></td><td><input type="date"></td><td><input type="text" placeholder="Notes..."></td></tr>
        <tr><td><input type="text"></td><td><input type="text"></td><td><input type="text"></td><td><input type="text"></td><td><input type="date"></td><td><input type="text"></td></tr>
        <tr><td><input type="text"></td><td><input type="text"></td><td><input type="text"></td><td><input type="text"></td><td><input type="date"></td><td><input type="text"></td></tr>
      </tbody>
    </table>
    <button class="add-row" onclick="addRow('deliv-table',6)">+ Add deliverable</button>
  </div>
</div>

<!-- SECTION 7 -->
<div class="section" id="s7">
  <div class="section-header">
    <div class="section-num">7</div>
    <div><div class="section-title">Assets, Brand &amp; Compliance</div></div>
  </div>
  <div class="sub-section">
    <div class="sub-title">Brand Assets (multi-select)</div>
    <div class="chips" data-multi="true">
      <div class="chip"><span class="chk">✓</span>Brand guidelines (PDF)</div>
      <div class="chip"><span class="chk">✓</span>Logo pack (RGB/CMYK/SVG)</div>
      <div class="chip"><span class="chk">✓</span>Color palette (HEX/PMS)</div>
      <div class="chip"><span class="chk">✓</span>Typography (font files/licences)</div>
      <div class="chip"><span class="chk">✓</span>Icon / Illustration library</div>
      <div class="chip"><span class="chk">✓</span>Photography style / shot list</div>
      <div class="chip"><span class="chk">✓</span>Past campaign / key visuals</div>
      <div class="chip"><span class="chk">✓</span>Tone-of-voice guide</div>
    </div>
    <div class="field" style="margin-top:8px;"><label>Asset links / files</label><textarea placeholder="Paste file links, Dropbox/Drive URLs, Teams paths..."></textarea></div>
  </div>
  <div class="sub-section">
    <div class="sub-title">Compliance (multi-select)</div>
    <div class="chips" data-multi="true">
      <div class="chip"><span class="chk">✓</span>Alt text</div>
      <div class="chip"><span class="chk">✓</span>WCAG captions</div>
      <div class="chip"><span class="chk">✓</span>Contrast AA</div>
      <div class="chip"><span class="chk">✓</span>COPPA</div>
      <div class="chip"><span class="chk">✓</span>CARU</div>
      <div class="chip"><span class="chk">✓</span>CAP Code (UK)</div>
      <div class="chip"><span class="chk">✓</span>GDPR</div>
      <div class="chip"><span class="chk">✓</span>CCPA/CPRA</div>
      <div class="chip"><span class="chk">✓</span>CASL (email)</div>
      <div class="chip"><span class="chk">✓</span>Age-grading</div>
      <div class="chip"><span class="chk">✓</span>Safety icons</div>
      <div class="chip"><span class="chk">✓</span>CPSIA / EN71</div>
    </div>
  </div>
  <div class="sub-section">
    <div class="sub-title">Usage Rights</div>
    <div class="grid-2">
      <div class="field"><label>License type</label>
        <div class="chips" data-multi="false" style="margin-top:4px;">
          <div class="chip"><span class="chk">✓</span>Full buy-out</div>
          <div class="chip"><span class="chk">✓</span>Limited license</div>
        </div>
      </div>
      <div class="field"><label>Media (multi-select)</label>
        <div class="chips" data-multi="true" style="margin-top:4px;">
          <div class="chip"><span class="chk">✓</span>Print</div><div class="chip"><span class="chk">✓</span>OOH</div><div class="chip"><span class="chk">✓</span>Digital / Social</div><div class="chip"><span class="chk">✓</span>TV / Streaming</div><div class="chip"><span class="chk">✓</span>POS / Pack</div>
        </div>
      </div>
      <div class="field"><label>Territory (multi-select)</label>
        <div class="chips" data-multi="true" style="margin-top:4px;">
          <div class="chip"><span class="chk">✓</span>Canada</div><div class="chip"><span class="chk">✓</span>US</div><div class="chip"><span class="chk">✓</span>North America</div><div class="chip"><span class="chk">✓</span>Global</div>
        </div>
      </div>
      <div class="field"><label>Term</label>
        <div class="chips" data-multi="false" style="margin-top:4px;">
          <div class="chip"><span class="chk">✓</span>1 yr</div><div class="chip"><span class="chk">✓</span>2 yrs</div><div class="chip"><span class="chk">✓</span>Perpetual</div>
        </div>
      </div>
      <div class="field"><label>Exclusivity</label>
        <div class="chips" data-multi="false" style="margin-top:4px;">
          <div class="chip"><span class="chk">✓</span>Yes</div><div class="chip"><span class="chk">✓</span>No</div>
        </div>
      </div>
      <div class="field"><label>File Storage / Handoff Path</label><input type="text" placeholder="Teams/FP path..."></div>
    </div>
  </div>
</div>

<!-- SECTION 8 -->
<div class="section" id="s8">
  <div class="section-header">
    <div class="section-num">8</div>
    <div><div class="section-title">Schedule &amp; Milestones</div></div>
  </div>
  <div class="sub-section">
    <div class="sub-title">Key Dates</div>
    <div class="grid-2">
      <div class="field"><label>Proposal / Quote deadline <span class="req-badge">*</span></label><input type="date"></div>
      <div class="field"><label>Final agreement / PO in <span class="req-badge">*</span></label><input type="date"></div>
      <div class="field"><label>Asset intake complete</label><input type="date"></div>
      <div class="field"><label>Concepts due (R1)</label><input type="date"></div>
      <div class="field"><label>Client review R1 due</label><input type="date"></div>
      <div class="field"><label>Creative R2 / Pre-final</label><input type="date"></div>
      <div class="field"><label>Client review R2 due</label><input type="date"></div>
      <div class="field"><label>Final art / Pre-press</label><input type="date"></div>
      <div class="field"><label>QA complete (digital)</label><input type="date"></div>
      <div class="field"><label>Go-live / Launch <span class="req-badge">*</span></label><input type="date"></div>
      <div class="field"><label>Media flight start</label><input type="date"></div>
      <div class="field"><label>Media flight end</label><input type="date"></div>
    </div>
  </div>
  <div class="sub-section">
    <div class="sub-title">Approval Settings</div>
    <div class="grid-2">
      <div class="field"><label>Turnaround SLA</label>
        <div class="chips" data-multi="false" style="margin-top:4px;">
          <div class="chip"><span class="chk">✓</span>1 BD</div>
          <div class="chip"><span class="chk">✓</span>2 BD</div>
          <div class="chip"><span class="chk">✓</span>3 BD</div>
        </div>
      </div>
      <div class="field"><label>Feedback policy</label>
        <div class="chips" data-multi="false" style="margin-top:4px;">
          <div class="chip"><span class="chk">✓</span>Consolidated each round</div>
          <div class="chip"><span class="chk">✓</span>Single approver gate</div>
        </div>
      </div>
      <div class="field"><label>Revision rounds included</label>
        <div class="chips" data-multi="true" style="margin-top:4px;">
          <div class="chip"><span class="chk">✓</span>R1</div>
          <div class="chip"><span class="chk">✓</span>R2</div>
        </div>
      </div>
      <div class="field"><label>Client blackouts / OOO</label><input type="text" placeholder="e.g. Client OOO July 4–8"></div>
    </div>
  </div>
  <div class="sub-section">
    <div class="sub-title">Dependencies (multi-select)</div>
    <div class="chips" data-multi="true">
      <div class="chip"><span class="chk">✓</span>Licensor approval</div>
      <div class="chip"><span class="chk">✓</span>Legal / Claims review</div>
      <div class="chip"><span class="chk">✓</span>Translations</div>
      <div class="chip"><span class="chk">✓</span>Accessibility (WCAG)</div>
      <div class="chip"><span class="chk">✓</span>Retailer spec sign-off</div>
      <div class="chip"><span class="chk">✓</span>App Store / Play review</div>
      <div class="chip"><span class="chk">✓</span>Printer slot / paper stock hold</div>
    </div>
  </div>
  <div class="sub-section">
    <div class="sub-title">Workback Tracker</div>
    <table class="brief-table" id="wb-table">
      <thead><tr><th>Milestone</th><th>Owner</th><th>Due</th><th>Status</th><th>Notes</th></tr></thead>
      <tbody>
        <tr><td><input type="text" placeholder="e.g. Brief sign-off"></td><td><input type="text" placeholder="Name"></td><td><input type="date"></td><td><input type="text" placeholder="Not started"></td><td><input type="text" placeholder=""></td></tr>
        <tr><td><input type="text"></td><td><input type="text"></td><td><input type="date"></td><td><input type="text"></td><td><input type="text"></td></tr>
        <tr><td><input type="text"></td><td><input type="text"></td><td><input type="date"></td><td><input type="text"></td><td><input type="text"></td></tr>
        <tr><td><input type="text"></td><td><input type="text"></td><td><input type="date"></td><td><input type="text"></td><td><input type="text"></td></tr>
      </tbody>
    </table>
    <button class="add-row" onclick="addRow('wb-table',5)">+ Add milestone</button>
  </div>
</div>

<!-- SECTION 9 -->
<div class="section" id="s9">
  <div class="section-header">
    <div class="section-num">9</div>
    <div><div class="section-title">Distribution, Channels &amp; Retail</div></div>
  </div>
  <div class="grid-2">
    <div class="field"><label>Bill-to company</label><input type="text" placeholder="Company name"></div>
    <div class="field"><label>PO #</label><input type="text" placeholder="PO-XXXX"></div>
    <div class="field"><label>Billing contact / email</label><input type="text" placeholder="Name + email"></div>
    <div class="field"><label>Currency</label>
      <div class="chips" data-multi="false" style="margin-top:4px;">
        <div class="chip"><span class="chk">✓</span>CAD</div>
        <div class="chip"><span class="chk">✓</span>USD</div>
        <div class="chip"><span class="chk">✓</span>Other</div>
      </div>
    </div>
    <div class="field"><label>Payment terms</label>
      <div class="chips" data-multi="false" style="margin-top:4px;">
        <div class="chip"><span class="chk">✓</span>50/50 deposit/final</div>
        <div class="chip"><span class="chk">✓</span>Net 15</div>
        <div class="chip"><span class="chk">✓</span>Net 30</div>
      </div>
    </div>
    <div class="field"><label>Tax status</label>
      <div class="chips" data-multi="false" style="margin-top:4px;">
        <div class="chip"><span class="chk">✓</span>Taxable</div>
        <div class="chip"><span class="chk">✓</span>Exempt</div>
      </div>
    </div>
  </div>
  <div class="sub-section" style="margin-top:1rem;">
    <div class="sub-title">Retail Partners (multi-select)</div>
    <div class="chips" data-multi="true">
      <div class="chip"><span class="chk">✓</span>Walmart</div>
      <div class="chip"><span class="chk">✓</span>Costco</div>
      <div class="chip"><span class="chk">✓</span>Amazon</div>
      <div class="chip"><span class="chk">✓</span>Grocery</div>
      <div class="chip"><span class="chk">✓</span>QSR</div>
      <div class="chip"><span class="chk">✓</span>Specialty</div>
    </div>
  </div>
  <div class="sub-section">
    <div class="sub-title">Media Channels (multi-select)</div>
    <div class="chips" data-multi="true">
      <div class="chip"><span class="chk">✓</span>TV / CTV / OTT</div>
      <div class="chip"><span class="chk">✓</span>OLV / YouTube</div>
      <div class="chip"><span class="chk">✓</span>Social (paid)</div>
      <div class="chip"><span class="chk">✓</span>Social (organic)</div>
      <div class="chip"><span class="chk">✓</span>Display / HTML5</div>
      <div class="chip"><span class="chk">✓</span>Email / CRM</div>
      <div class="chip"><span class="chk">✓</span>PR / Influencer</div>
      <div class="chip"><span class="chk">✓</span>Experiential / Event</div>
    </div>
  </div>
</div>

<!-- SECTION 10 -->
<div class="section" id="s10">
  <div class="section-header">
    <div class="section-num">10</div>
    <div><div class="section-title">Pricing &amp; Invoicing</div></div>
  </div>
  <div class="grid-2">
    <div class="field"><label>Estimate total</label><input type="text" placeholder="e.g. $12,500 CAD"></div>
    <div class="field"><label>Units / case price (if print)</label><input type="text" placeholder="e.g. $0.85/unit"></div>
    <div class="field"><label>Scope includes</label>
      <div class="chips" data-multi="true" style="margin-top:4px;">
        <div class="chip"><span class="chk">✓</span>R1</div>
        <div class="chip"><span class="chk">✓</span>R2</div>
      </div>
    </div>
    <div class="field"><label>Buy-out / source files</label>
      <div class="chips" data-multi="false" style="margin-top:4px;">
        <div class="chip"><span class="chk">✓</span>Included</div>
        <div class="chip"><span class="chk">✓</span>Additional fee</div>
      </div>
    </div>
    <div class="field"><label>Currency</label>
      <div class="chips" data-multi="false" style="margin-top:4px;">
        <div class="chip"><span class="chk">✓</span>CAD</div>
        <div class="chip"><span class="chk">✓</span>USD</div>
      </div>
    </div>
    <div class="field"><label>Terms</label>
      <div class="chips" data-multi="false" style="margin-top:4px;">
        <div class="chip"><span class="chk">✓</span>50% deposit to start</div>
        <div class="chip"><span class="chk">✓</span>Net 15</div>
        <div class="chip"><span class="chk">✓</span>Net 30</div>
        <div class="chip"><span class="chk">✓</span>Milestone billing</div>
      </div>
    </div>
    <div class="field"><label>Invoicing cadence</label>
      <div class="chips" data-multi="true" style="margin-top:4px;">
        <div class="chip"><span class="chk">✓</span>Kickoff</div>
        <div class="chip"><span class="chk">✓</span>Milestones</div>
        <div class="chip"><span class="chk">✓</span>Final delivery</div>
        <div class="chip"><span class="chk">✓</span>Monthly</div>
      </div>
    </div>
    <div class="field"><label>Vendor setup docs needed</label>
      <div class="chips" data-multi="true" style="margin-top:4px;">
        <div class="chip"><span class="chk">✓</span>W-9</div>
        <div class="chip"><span class="chk">✓</span>Direct deposit form</div>
        <div class="chip"><span class="chk">✓</span>Void cheque</div>
      </div>
    </div>
  </div>
</div>

<!-- SECTION 11 -->
<div class="section" id="s11">
  <div class="section-header">
    <div class="section-num">11</div>
    <div><div class="section-title">Risks, Assumptions &amp; Notes</div></div>
  </div>
  <div class="sub-section">
    <div class="sub-title">Risks / Constraints (tick all that apply)</div>
    <div class="risk-list">
      <div class="risk-item" onclick="this.classList.toggle('checked')"><div class="rchk">✓</div><div class="risk-text">Multi-approver feedback may exceed SLA</div></div>
      <div class="risk-item" onclick="this.classList.toggle('checked')"><div class="rchk">✓</div><div class="risk-text">Licensor / legal review timing</div></div>
      <div class="risk-item" onclick="this.classList.toggle('checked')"><div class="rchk">✓</div><div class="risk-text">Retailer / spec changes after design lock</div></div>
      <div class="risk-item" onclick="this.classList.toggle('checked')"><div class="rchk">✓</div><div class="risk-text">Translation / localization delays</div></div>
      <div class="risk-item" onclick="this.classList.toggle('checked')"><div class="rchk">✓</div><div class="risk-text">Asset gaps (logos, claims, barcodes)</div></div>
      <div class="risk-item" onclick="this.classList.toggle('checked')"><div class="rchk">✓</div><div class="risk-text">Printer capacity / paper stock availability</div></div>
      <div class="risk-item" onclick="this.classList.toggle('checked')"><div class="rchk">✓</div><div class="risk-text">Platform approvals (App Store / Play)</div></div>
      <div class="risk-item" onclick="this.classList.toggle('checked')"><div class="rchk">✓</div><div class="risk-text">Accessibility compliance (WCAG / alt / captions)</div></div>
      <div class="risk-item" onclick="this.classList.toggle('checked')"><div class="rchk">✓</div><div class="risk-text">Shipping / logistics or weather impacts</div></div>
    </div>
    <div class="field" style="margin-top:10px;"><label>Mitigation notes</label><textarea placeholder="How will we mitigate each flagged risk?"></textarea></div>
  </div>
  <div class="sub-section">
    <div class="sub-title">Assumptions</div>
    <div class="field"><textarea placeholder="e.g. Consolidated feedback within 2 BD per round&#10;Max 2 creative rounds (R1/R2)&#10;All mandatories provided by [date]&#10;Client provides product facts/claims for RTBs&#10;Translations supplied/approved by client unless scoped&#10;Buy-out/usage terms as agreed in Section 7"></textarea></div>
  </div>
  <div class="sub-section">
    <div class="sub-title">Additional Notes</div>
    <div class="field"><textarea placeholder="Anything else the team needs to know before we begin..."></textarea></div>
  </div>
</div>

<div class="footer-bar">
  <div class="completion">Sections: <strong id="filled-count">0</strong> / 11 touched</div>
  <div class="btn-row">
    <button class="btn btn-outline" onclick="window.print()">Print / PDF</button>
    <button class="btn btn-solid" onclick="showSummary()">Export summary ↗</button>
  </div>
</div>

</div><!-- /page -->

<div class="modal" id="summary-modal">
  <div class="modal-box">
    <h2>Brief summary</h2>
    <pre class="modal-pre" id="summary-text"></pre>
    <button class="modal-close" onclick="document.getElementById('summary-modal').classList.remove('open')">Close</button>
  </div>
</div>

<script>
// Chips toggle
document.querySelectorAll('.chips .chip').forEach(chip => {
  chip.addEventListener('click', () => {
    const multi = chip.closest('.chips')?.dataset.multi !== 'false';
    if (!multi) {
      chip.closest('.chips').querySelectorAll('.chip').forEach(c => c.classList.remove('selected'));
    }
    chip.classList.toggle('selected');
    updateCount();
  });
});

// Approval steps
document.querySelectorAll('.astep').forEach(s => {
  s.addEventListener('click', () => s.classList.toggle('selected'));
});

// Add table rows
function addRow(tableId, cols) {
  const tb = document.getElementById(tableId).querySelector('tbody');
  const tr = document.createElement('tr');
  for (let i = 0; i < cols; i++) {
    const td = document.createElement('td');
    const inp = document.createElement('input');
    inp.type = i === cols - 2 && tableId === 'wb-table' ? 'date' : 'text';
    td.appendChild(inp);
    tr.appendChild(td);
  }
  tb.appendChild(tr);
}

// Nav active state
function scrollTo(id) {
  document.getElementById(id)?.scrollIntoView({behavior:'smooth'});
}

// Track sections touched
function updateCount() {
  const sections = document.querySelectorAll('.section');
  let touched = 0;
  sections.forEach(s => {
    const hasInput = [...s.querySelectorAll('input,textarea')].some(i => i.value.trim());
    const hasChip = s.querySelector('.chip.selected');
    const hasStep = s.querySelector('.astep.selected');
    const hasRisk = s.querySelector('.risk-item.checked');
    if (hasInput || hasChip || hasStep || hasRisk) touched++;
  });
  document.getElementById('filled-count').textContent = touched;
}

document.querySelectorAll('input,textarea').forEach(el => el.addEventListener('input', updateCount));

// Scroll spy nav
const sections = document.querySelectorAll('.section');
const navPills = document.querySelectorAll('.nav-pill');
window.addEventListener('scroll', () => {
  let current = '';
  sections.forEach(s => { if (window.scrollY >= s.offsetTop - 100) current = s.id; });
  navPills.forEach((p, i) => p.classList.toggle('active', `s${i+1}` === current));
}, {passive:true});

// Export summary
function showSummary() {
  const get = id => document.getElementById(id)?.value || '—';
  const chips = (selector) => [...document.querySelectorAll(`${selector} .chip.selected`)].map(c => c.textContent.trim()).join(', ') || '—';

  const lines = [
    'KIDZSMART — CREATIVE BRIEF SUMMARY',
    '═'.repeat(44),
    '',
    '1. PROJECT',
    `   Title:      ${get('proj-title')}`,
    `   Client:     ${get('proj-client')}`,
    '',
    '3. AUDIENCE',
    `   Primary:    ${chips('#s3 .sub-section:nth-child(1) .chips')}`,
    `   Geography:  ${chips('#s3 .sub-section:nth-child(3) .chips')}`,
    '',
    '4. MESSAGING',
    `   CTAs:       ${chips('#s4 .sub-section:nth-child(2) .chips')}`,
    '',
    '5. STRATEGY',
    `   Style:      ${chips('#s5 .sub-section:nth-child(2) .chips')}`,
    '',
    '6. DELIVERABLES',
    `   Categories: ${chips('#s6 .sub-section:nth-child(1) .chips')}`,
    `   Disciplines:${chips('#s6 .sub-section:nth-last-child(2) .chips')}`,
    '',
    '7. COMPLIANCE',
    `   Flags:      ${chips('#s7 .sub-section:nth-child(2) .chips')}`,
    '',
    '11. RISKS',
    `   Flagged:    ${[...document.querySelectorAll('.risk-item.checked .risk-text')].map(r=>r.textContent).join(' | ') || '—'}`,
    '',
    '─'.repeat(44),
    'Generated by Kidzsmart Creative Brief Tool',
  ];
  document.getElementById('summary-text').textContent = lines.join('\n');
  document.getElementById('summary-modal').classList.add('open');
}
</script>
</body>
</html>
