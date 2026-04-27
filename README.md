# zetabytetec.github.io
<!--Aplicativo para ler código html, css, javascript-->
<!DOCTYPE html>
<html lang="pt-br">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Zetabytetec</title>
  <link rel="stylesheet" href="style.css">
  <!-- TOPBAR -->
<header class="topbar">
  <div class="topbar-logo">
    <div class="logo-grid">
      <div class="logo-cell"></div><div class="logo-cell"></div><div class="logo-cell"></div>
      <div class="logo-cell"></div><div class="logo-cell"></div><div class="logo-cell"></div>
      <div class="logo-cell"></div><div class="logo-cell"></div><div class="logo-cell"></div>
    </div> 🛡️ Zetabytetec DevOps Lab</div>
  <div class="topbar-status">
    <span><span class="status-dot dot-green"></span>Systems Operational</span>
    <span><span class="status-dot dot-yellow"></span>Scan Running</span>
    <span style="color: var(--text-primary); font-size:11px;" id="clock"></span>
  </div>
  <div class="topbar-actions">
    <button class="btn" onclick="runScan()">⚡ Run Scan</button>
    <button class="btn btn-primary" onclick="deployPipeline()">🚀 Deploy</button>
  </div>
</header>

<!-- LAYOUT -->
<div class="layout">

  <!-- SIDEBAR -->
    <nav class="sidebar">
    <div class="sidebar-section">
      <div class="sidebar-label">Overview</div>
      <div class="nav-item active" onclick="setNav(this, 'dashboard')">📊 Dashboard</div>
      <div class="nav-item" onclick="setNav(this, 'dashboard')">🗺️ Threat Map</div>
      <div class="nav-item" onclick="setNav(this, 'dashboard')">📈 Metrics</div>
    </div>
    <div class="sidebar-section">
      <div class="sidebar-label">Security</div>
      <div class="nav-item" onclick="setNav(this, 'dashboard')">🔍 Vulnerability Scan <span class="nav-badge">7</span></div>
      <div class="nav-item" onclick="setNav(this, 'dashboard')">🔐 SAST / DAST</div>
      <div class="nav-item" onclick="setNav(this, 'dashboard')">🧱 Firewall Rules</div>
      <div class="nav-item" onclick="setNav(this, 'dashboard')">🪪 IAM Policies</div>
      <div class="nav-item" onclick="setNav(this, 'dashboard')">🔑 Secrets Manager</div>
    </div>
    <div class="sidebar-section">
      <div class="sidebar-label">CI/CD Pipeline</div>
      <div class="nav-item" onclick="setNav(this, 'dashboard')">⚙️ Pipelines <span class="nav-badge green">2</span></div>
      <div class="nav-item" onclick="setNav(this, 'dashboard')">📦 Artifacts</div>
      <div class="nav-item" onclick="setNav(this, 'dashboard')">🐳 Containers</div>
      <div class="nav-item" onclick="setNav(this, 'dashboard')">☸️ Kubernetes</div>
    </div>
    <div class="sidebar-section">
      <div class="sidebar-label">Compliance</div>
      <div class="nav-item" onclick="setNav(this, 'dashboard')">📋 SOC 2</div>
      <div class="nav-item" onclick="setNav(this, 'dashboard')">🔒 ISO 27001</div>
      <div class="nav-item" onclick="setNav(this, 'dashboard')">📝 Audit Logs</div>
    </div>
    <div class="sidebar-section">
      <div class="sidebar-label">Config</div>
      <div class="nav-item" onclick="setNav(this, 'dashboard')">⚙️ Settings</div>
      <div class="nav-item" onclick="setNav(this, 'dashboard')">🔔 Alerts</div>
      <div class="nav-item" onclick="setNav(this, 'dashboard')">👤 Team</div>
    </div>
  </nav>

  <!-- MAIN CONTENT -->
  <main class="main">

    <!-- PAGE HEADER -->
    <div class="page-header">
      <div>
        <div class="page-title">Security & DevOps Overview</div>
        <div class="page-subtitle">Last scan: 3 min ago &nbsp;·&nbsp; Environment: Production &nbsp;·&nbsp; Branch: main</div>
      </div>
      <div style="display:flex;gap:8px;align-items:center;">
        <span class="tag tag-blue">v2.4.1</span>
        <span class="tag tag-green">Healthy</span>
        <span class="tag tag-purple">CI/CD Active</span>
      </div>
    </div>

    <!-- METRICS -->
    <div class="metrics-grid">
      <div class="metric-card green">
        <div class="metric-icon">🛡️</div>
        <div class="metric-label">Security Score</div>
        <div class="metric-value green" id="scoreVal">87</div>
        <div class="metric-delta up">↑ +4 from last week</div>
      </div>
      <div class="metric-card red">
        <div class="metric-icon">⚠️</div>
        <div class="metric-label">Open Vulnerabilities</div>
        <div class="metric-value red" id="vulnVal">12</div>
        <div class="metric-delta down">↓ 3 new since yesterday</div>
      </div>
      <div class="metric-card blue">
        <div class="metric-icon">🚀</div>
        <div class="metric-label">Pipeline Runs Today</div>
        <div class="metric-value blue" id="pipeVal">34</div>
        <div class="metric-delta up">↑ 8 more than average</div>
      </div>
      <div class="metric-card yellow">
        <div class="metric-icon">🐳</div>
        <div class="metric-label">Containers Running</div>
        <div class="metric-value yellow" id="containerVal">18</div>
        <div class="metric-delta up">↑ 2 new deployments</div>
      </div>
    </div>

    <!-- CI/CD PIPELINE -->
    <div class="card-header">
      <span class="card-title">⚙️ CI/CD Pipeline — main branch</span>
      <span style="font-size:11px;color:var(--text-secondary);">Build #247 &nbsp;·&nbsp; Triggered by push</span>
    </div>
    <div class="pipeline-stages">
      <div class="pipeline-stage">
        <div class="stage-icon passed">✓</div>
        <div class="stage-name">Checkout</div>
        <div class="stage-time">0:08</div>
        <div class="stage-status passed">PASSED</div>
      </div>
      <div class="pipeline-stage">
        <div class="stage-icon passed">✓</div>
        <div class="stage-name">Build</div>
        <div class="stage-time">1:32</div>
        <div class="stage-status passed">PASSED</div>
      </div>
      <div class="pipeline-stage">
        <div class="stage-icon passed">✓</div>
        <div class="stage-name">Unit Tests</div>
        <div class="stage-time">0:54</div>
        <div class="stage-status passed">PASSED</div>
      </div>
      <div class="pipeline-stage">
        <div class="stage-icon running">⟳</div>
        <div class="stage-name">SAST Scan</div>
        <div class="stage-time">Running...</div>
        <div class="stage-status running">RUNNING</div>
      </div>
      <div class="pipeline-stage">
        <div class="stage-icon pending">○</div>
        <div class="stage-name">Container Build</div>
        <div class="stage-time">—</div>
        <div class="stage-status" style="color:var(--text-secondary)">PENDING</div>
      </div>
      <div class="pipeline-stage">
        <div class="stage-icon pending">○</div>
        <div class="stage-name">Deploy Staging</div>
        <div class="stage-time">—</div>
        <div class="stage-status" style="color:var(--text-secondary)">PENDING</div>
      </div>
      <div class="pipeline-stage">
        <div class="stage-icon pending">○</div>
        <div class="stage-name">DAST Scan</div>
        <div class="stage-time">—</div>
        <div class="stage-status" style="color:var(--text-secondary)">PENDING</div>
      </div>
      <div class="pipeline-stage">
        <div class="stage-icon pending">○</div>
        <div class="stage-name">Deploy Prod</div>
        <div class="stage-time">—</div>
        <div class="stage-status" style="color:var(--text-secondary)">PENDING</div>
      </div>
    </div>
  </div>

  <!-- VULNERABILITIES + SECURITY SCORE -->
  <div class="grid-3-1">
    <!-- VULNERABILITIES -->
    <div class="card">
      <div class="card-header">
        <span class="card-title">🔍 Vulnerability Report</span>
        <button class="btn" style="font-size:11px;" onclick="refreshVulns()">↻ Refresh</button>
      </div>
      <div style="padding: 0 18px 4px;">
        <div class="tabs" style="padding:0;">
          <div class="tab active" onclick="switchTab(event,'all')">All (12)</div>
          <div class="tab" onclick="switchTab(event,'critical')">Critical (2)</div>
          <div class="tab" onclick="switchTab(event,'high')">High (4)</div>
          <div class="tab" onclick="switchTab(event,'medium')">Medium (6)</div>
        </div>
      </div>
      <div class="tab-content active" id="tab-all">
        <table class="vuln-table">
          <thead>
            <tr>
              <th>CVE ID</th>
              <th>Component</th>
              <th>Severity</th>
              <th>CVSS</th>
              <th>Status</th>
            </tr>
          </thead>
          <tbody id="vuln-tbody">
            <tr>
              <td style="color:var(--accent-blue)">CVE-2024-3094</td>
              <td>xz-utils 5.6.0</td>
              <td><span class="severity-badge sev-critical">Critical</span></td>
              <td>10.0</td>
              <td><span style="color:var(--accent-red)">● Open</span></td>
            </tr>
            <tr>
              <td style="color:var(--accent-blue)">CVE-2024-6387</td>
              <td>OpenSSH 9.7</td>
              <td><span class="severity-badge sev-critical">Critical</span></td>
              <td>9.8</td>
              <td><span style="color:var(--accent-yellow)">● In Progress</span></td>
            </tr>
            <tr>
              <td style="color:var(--accent-blue)">CVE-2023-44487</td>
              <td>HTTP/2 Stack</td>
              <td><span class="severity-badge sev-high">High</span></td>
              <td>7.5</td>
              <td><span style="color:var(--accent-red)">● Open</span></td>
            </tr>
            <tr>
              <td style="color:var(--accent-blue)">CVE-2024-21626</td>
              <td>runc 1.1.11</td>
              <td><span class="severity-badge sev-high">High</span></td>
              <td>8.6</td>
              <td><span style="color:var(--accent-yellow)">● In Progress</span></td>
            </tr>
            <tr>
              <td style="color:var(--accent-blue)">CVE-2023-48795</td>
              <td>libssh2 1.11.0</td>
              <td><span class="severity-badge sev-medium">Medium</span></td>
              <td>5.9</td>
              <td><span style="color:var(--accent-red)">● Open</span></td>
            </tr>
            <tr>
              <td style="color:var(--accent-blue)">CVE-2024-0193</td>
              <td>linux-kernel 6.6</td>
              <td><span class="severity-badge sev-medium">Medium</span></td>
              <td>6.7</td>
              <td><span style="color:var(--accent-green)">● Patched</span></td>
            </tr>
          </tbody>
        </table>
      </div>
    </div>

    <!-- SECURITY SCORE CARD -->
    <div class="card">
      <div class="card-header"><span class="card-title">🔒 Security Score</span></div>
      <div class="card-body" style="text-align:center;">
        <div class="score-ring">
          <svg width="110" height="110" viewBox="0 0 110 110">
            <circle cx="55" cy="55" r="45" fill="none" stroke="var(--bg-tertiary)" stroke-width="10"/>
            <circle cx="55" cy="55" r="45" fill="none" stroke="var(--accent-green)" stroke-width="10"
              stroke-dasharray="283" stroke-dashoffset="37" stroke-linecap="round"
              style="transition:stroke-dashoffset 1s ease;"/>
          </svg>
          <div class="score-ring-text">
            <div class="score-num">87</div>
            <div class="score-label">/100</div>
          </div>
        </div>
        <div style="font-size:12px;color:var(--accent-green);margin-bottom:12px;font-weight:600;">Good</div>
        <div class="score-details">
          <div class="score-row">
            <span>Encryption</span>
            <div class="score-bar-outer"><div class="score-bar-inner" style="width:95%;background:var(--accent-green);"></div></div>
            <span style="color:var(--accent-green)">95</span>
          </div>
          <div class="score-row">
            <span>IAM</span>
            <div class="score-bar-outer"><div class="score-bar-inner" style="width:80%;background:var(--accent-blue);"></div></div>
            <span style="color:var(--accent-blue)">80</span>
          </div>
          <div class="score-row">
            <span>Patching</span>
            <div class="score-bar-outer"><div class="score-bar-inner" style="width:72%;background:var(--accent-yellow);"></div></div>
            <span style="color:var(--accent-yellow)">72</span>
          </div>
          <div class="score-row">
            <span>Network</span>
            <div class="score-bar-outer"><div class="score-bar-inner" style="width:90%;background:var(--accent-green);"></div></div>
            <span style="color:var(--accent-green)">90</span>
          </div>
          <div class="score-row">
            <span>Compliance</span>
            <div class="score-bar-outer"><div class="score-bar-inner" style="width:85%;background:var(--accent-green);"></div></div>
            <span style="color:var(--accent-green)">85</span>
          </div>
        </div>
      </div>
    </div>
  </div>

  <!-- TERMINAL + EVENTS -->
  <div class="grid-2">
    <!-- TERMINAL -->
    <div>
      <div style="font-size:12px;color:var(--text-secondary);margin-bottom:8px;">📟 Live Security Logs</div>
      <div class="terminal">
        <div class="terminal-bar">
          <div class="t-dot t-red"></div>
          <div class="t-dot t-yellow"></div>
          <div class="t-dot t-green"></div>
          <span class="t-title">security-monitor — bash</span>
        </div>
        <div class="terminal-body" id="terminal-body">
          <div class="log-line"><span class="log-time">[10:42:01]</span> <span class="log-success">[INFO]</span> Security daemon started</div>
          <div class="log-line"><span class="log-time">[10:42:03]</span> <span class="log-cmd">[CMD]</span> trivy image myapp:v2.4.1 --severity CRITICAL</div>
          <div class="log-line"><span class="log-time">[10:42:09]</span> <span class="log-info">[SCAN]</span> Scanning 312 dependencies...</div>
          <div class="log-line"><span class="log-time">[10:42:12]</span> <span class="log-warn">[WARN]</span> CVE-2024-3094 detected in xz-utils</div>
          <div class="log-line"><span class="log-time">[10:42:13]</span> <span class="log-error">[ALERT]</span> CRITICAL: Backdoor pattern detected</div>
          <div class="log-line"><span class="log-time">[10:42:14]</span> <span class="log-success">[OK]</span> SAST scan: 0 secrets exposed</div>
          <div class="log-line"><span class="log-time">[10:42:18]</span> <span class="log-info">[SCAN]</span> Running OWASP ZAP passive scan...</div>
          <div class="log-line"><span class="log-time">[10:42:22]</span> <span class="log-success">[OK]</span> TLS 1.3 enforced on all endpoints</div>
        </div>
      </div>
    </div>

    <!-- EVENTS FEED -->
    <div class="card">
      <div class="card-header"><span class="card-title">🔔 Security Events</span></div>
      <div class="card-body" id="events-feed">
        <div class="event-item">
          <div class="event-dot-wrap"><div class="event-dot" style="background:var(--accent-red)"></div></div>
          <div class="event-content">
            <div class="event-title">Critical vulnerability detected in xz-utils</div>
            <div class="event-meta">Container: api-service &nbsp;·&nbsp; Severity: CRITICAL</div>
          </div>
          <div class="event-time">3m ago</div>
        </div>
        <div class="event-item">
          <div class="event-dot-wrap"><div class="event-dot" style="background:var(--accent-green)"></div></div>
          <div class="event-content">
            <div class="event-title">Pipeline #247 — Unit tests passed</div>
            <div class="event-meta">Branch: main &nbsp;·&nbsp; 142 tests passed</div>
          </div>
          <div class="event-time">7m ago</div>
        </div>
        <div class="event-item">
          <div class="event-dot-wrap"><div class="event-dot" style="background:var(--accent-yellow)"></div></div>
          <div class="event-content">
            <div class="event-title">IAM policy change detected</div>
            <div class="event-meta">User: deploy-bot &nbsp;·&nbsp; Resource: S3 bucket</div>
          </div>
          <div class="event-time">12m ago</div>
        </div>
        <div class="event-item">
          <div class="event-dot-wrap"><div class="event-dot" style="background:var(--accent-blue)"></div></div>
          <div class="event-content">
            <div class="event-title">New container deployed to staging</div>
            <div class="event-meta">Image: myapp:v2.4.1-rc3 &nbsp;·&nbsp; Pods: 3/3</div>
          </div>
          <div class="event-time">21m ago</div>
        </div>
        <div class="event-item">
          <div class="event-dot-wrap"><div class="event-dot" style="background:var(--accent-green)"></div></div>
          <div class="event-content">
            <div class="event-title">SSL certificate renewed automatically</div>
            <div class="event-meta">Domain: api.infoseclab.io &nbsp;·&nbsp; Let's Encrypt</div>
          </div>
          <div class="event-time">1h ago</div>
        </div>
        <div class="event-item">
          <div class="event-dot-wrap"><div class="event-dot" style="background:var(--accent-red)"></div></div>
          <div class="event-content">
            <div class="event-title">Failed login attempt (brute force?)</div>
            <div class="event-meta">IP: 185.220.101.47 &nbsp;·&nbsp; 28 attempts blocked</div>
          </div>
          <div class="event-time">2h ago</div>
        </div>
      </div>
    </div>
  </div>

  <!-- CONTAINERS -->
  <div class="card" style="margin-top:16px;">
    <div class="card-header">
      <span class="card-title">🐳 Running Containers</span>
      <span style="font-size:11px;color:var(--accent-green);">18 healthy</span>
    </div>
    <div class="card-body">
      <div class="container-grid">
        <div class="container-item">
          <div class="container-name">api-gateway</div>
          <div class="container-status"><span class="status-dot dot-green" style="display:inline-block;width:7px;height:7px;border-radius:50%;background:var(--accent-green);"></span>Running · 3 replicas</div>
          <div class="container-cpu"><span style="color:var(--text-secondary);font-size:10px;">CPU 42%</span><div class="mini-bar-outer"><div class="mini-bar-inner" style="width:42%;background:var(--accent-green);"></div></div></div>
        </div>
        <div class="container-item">
          <div class="container-name">auth-service</div>
          <div class="container-status"><span style="display:inline-block;width:7px;height:7px;border-radius:50%;background:var(--accent-green);margin-right:5px;"></span>Running · 2 replicas</div>
          <div class="container-cpu"><span style="color:var(--text-secondary);font-size:10px;">CPU 18%</span><div class="mini-bar-outer"><div class="mini-bar-inner" style="width:18%;background:var(--accent-green);"></div></div></div>
        </div>
        <div class="container-item">
          <div class="container-name">vuln-scanner</div>
          <div class="container-status"><span style="display:inline-block;width:7px;height:7px;border-radius:50%;background:var(--accent-blue);margin-right:5px;animation:pulse 1s infinite;"></span>Scanning · 1 replica</div>
          <div class="container-cpu"><span style="color:var(--text-secondary);font-size:10px;">CPU 87%</span><div class="mini-bar-outer"><div class="mini-bar-inner" style="width:87%;background:var(--accent-yellow);"></div></div></div>
        </div>
        <div class="container-item">
          <div class="container-name">postgres-db</div>
          <div class="container-status"><span style="display:inline-block;width:7px;height:7px;border-radius:50%;background:var(--accent-green);margin-right:5px;"></span>Running · 1 replica</div>
          <div class="container-cpu"><span style="color:var(--text-secondary);font-size:10px;">CPU 9%</span><div class="mini-bar-outer"><div class="mini-bar-inner" style="width:9%;background:var(--accent-green);"></div></div></div>
        </div>
        <div class="container-item">
          <div class="container-name">redis-cache</div>
          <div class="container-status"><span style="display:inline-block;width:7px;height:7px;border-radius:50%;background:var(--accent-green);margin-right:5px;"></span>Running · 1 replica</div>
          <div class="container-cpu"><span style="color:var(--text-secondary);font-size:10px;">CPU 5%</span><div class="mini-bar-outer"><div class="mini-bar-inner" style="width:5%;background:var(--accent-green);"></div></div></div>
        </div>
        <div class="container-item">
          <div class="container-name">log-aggregator</div>
          <div class="container-status"><span style="display:inline-block;width:7px;height:7px;border-radius:50%;background:var(--accent-green);margin-right:5px;"></span>Running · 2 replicas</div>
          <div class="container-cpu"><span style="color:var(--text-secondary);font-size:10px;">CPU 34%</span><div class="mini-bar-outer"><div class="mini-bar-inner" style="width:34%;background:var(--accent-blue);"></div></div></div>
        </div>
      </div>
    </div>
  </div>

</main>
</div>

<!-- FOOTER -->
<footer class="footer">
<span>Zetabytetec DevOps Lab &nbsp;·&nbsp; v2.4.1 &nbsp;·&nbsp; Environment: Production</span>
<span>Powered by CREAO &nbsp;·&nbsp; Build #247 &nbsp;·&nbsp; <span id="uptime">Uptime: 99.98%</span></span>
</footer>

<script>
// Clock
function updateClock() {
  const now = new Date();
  document.getElementById('clock').textContent = now.toLocaleTimeString();
}
setInterval(updateClock, 1000);
updateClock();

// Nav active state
function setNav(el, page) {
  document.querySelectorAll('.nav-item').forEach(n => n.classList.remove('active'));
  el.classList.add('active');
}

// Tab switch
function switchTab(e, name) {
  document.querySelectorAll('.tab').forEach(t => t.classList.remove('active'));
  document.querySelectorAll('.tab-content').forEach(t => t.classList.remove('active'));
  e.target.classList.add('active');
  const tc = document.getElementById('tab-' + name);
  if (tc) tc.classList.add('active');
}

// Run Scan animation
function runScan() {
  const btn = event.target;
  btn.textContent = '⏳ Scanning...';
  btn.disabled = true;
  addLog('[CMD]', 'trivy image --severity CRITICAL,HIGH .', 'log-cmd');
  addLog('[SCAN]', 'Initializing security scan...', 'log-info');
  setTimeout(() => {
    addLog('[SCAN]', 'Analyzing 518 packages...', 'log-info');
  }, 1000);
  setTimeout(() => {
    addLog('[OK]', 'Scan complete — 12 vulnerabilities found', 'log-success');
    btn.textContent = '⚡ Run Scan';
    btn.disabled = false;
  }, 3500);
}

// Deploy pipeline
function deployPipeline() {
  addLog('[CMD]', 'kubectl rollout deploy/api-gateway --image=myapp:v2.4.1', 'log-cmd');
  addLog('[INFO]', 'Triggering deployment pipeline...', 'log-info');
  document.getElementById('pipeVal').textContent = parseInt(document.getElementById('pipeVal').textContent) + 1;
}

// Refresh vulns
function refreshVulns() {
  addLog('[SCAN]', 'Refreshing vulnerability database...', 'log-info');
  setTimeout(() => addLog('[OK]', 'Vulnerability data updated', 'log-success'), 1200);
}

// Add log line
function addLog(tag, msg, cls) {
  const body = document.getElementById('terminal-body');
  const time = new Date().toLocaleTimeString('en-US', {hour12:false});
  const line = document.createElement('div');
  line.className = 'log-line';
  line.innerHTML = `<span class="log-time">[${time}]</span> <span class="${cls}">[${tag}]</span> ${msg}`;
  body.appendChild(line);
  body.scrollTop = body.scrollHeight;
}

// Auto-add logs every 8s
const autoLogs = [
  ['INFO', 'Heartbeat check — all systems nominal', 'log-info'],
  ['OK', 'TLS certificates valid for 87 days', 'log-success'],
  ['SCAN', 'Dependency audit: 0 new CVEs', 'log-info'],
  ['WARN', 'Unusual traffic spike on /api/auth', 'log-warn'],
  ['OK', 'Firewall rule updated: block 185.220.x.x/24', 'log-success'],
  ['INFO', 'Container health check passed', 'log-info'],
  ['ALERT', 'Rate limit triggered on api-gateway', 'log-warn'],
  ['OK', 'Secrets rotation completed for DB credentials', 'log-success'],
];
let logIdx = 0;
setInterval(() => {
  const [tag, msg, cls] = autoLogs[logIdx % autoLogs.length];
  addLog(tag, msg, cls);
  logIdx++;
}, 8000);

// Animate metric counters on load
function animateCounter(id, target) {
  let cur = 0;
  const el = document.getElementById(id);
  const step = Math.ceil(target / 30);
  const timer = setInterval(() => {
    cur = Math.min(cur + step, target);
    el.textContent = cur;
    if (cur >= target) clearInterval(timer);
  }, 40);
}
animateCounter('scoreVal', 87);
animateCounter('vulnVal', 12);
animateCounter('pipeVal', 34);
animateCounter('containerVal', 18);
</script>

</body>
</html>
    <div class="card" style="margin-bottom:16px;">


   <!--CSS-->

    :root {
      --bg-primary: #0d1117;
      --bg-secondary: #161b22;
      --bg-tertiary: #21262d;
      --border: #30363d;
      --text-primary: #e6edf3;
      --text-secondary: #8b949e;
      --accent-green: #3fb950;
      --accent-blue: #58a6ff;
      --accent-purple: #bc8cff;
      --accent-yellow: #d29922;
      --accent-red: #f85149;
      --accent-cyan: #39d5e5;
      --glow-green: rgba(63,185,80,0.15);
      --glow-blue: rgba(88,166,255,0.15);
      --glow-red: rgba(248,81,73,0.15);
    }

    * { margin: 0; padding: 0; box-sizing: border-box; }

    body {
      font-family: 'JetBrains Mono', 'Courier New', monospace;
      background: var(--bg-primary);
      color: var(--text-primary);
      min-height: 100vh;
      overflow-x: hidden;
    }

    /* SCROLLBAR */
    ::-webkit-scrollbar { width: 6px; }
    ::-webkit-scrollbar-track { background: var(--bg-primary); }
    ::-webkit-scrollbar-thumb { background: var(--border); border-radius: 3px; }

    /* TOPBAR */
    .topbar {
      background: var(--bg-secondary);
      border-bottom: 1px solid var(--border);
      padding: 12px 24px;
      display: flex;
      align-items: center;
      justify-content: space-between;
      position: sticky;
      top: 0;
      z-index: 100;
    }
    .topbar-logo {
      display: flex;
      align-items: center;
      gap: 10px;
      font-size: 18px;
      font-weight: 700;
      color: var(--accent-green);
      letter-spacing: 1px;
    }
    .topbar-logo .icon { font-size: 22px; }
    .topbar-status {
      display: flex;
      align-items: center;
      gap: 18px;
      font-size: 12px;
      color: var(--text-secondary);
    }
    .status-dot {
      width: 8px; height: 8px;
      border-radius: 50%;
      display: inline-block;
      margin-right: 5px;
      animation: pulse 2s infinite;
    }
    .dot-green { background: var(--accent-green); box-shadow: 0 0 6px var(--accent-green); }
    .dot-yellow { background: var(--accent-yellow); box-shadow: 0 0 6px var(--accent-yellow); }
    .dot-red { background: var(--accent-red); box-shadow: 0 0 6px var(--accent-red); }

    @keyframes pulse {
      0%, 100% { opacity: 1; }
      50% { opacity: 0.4; }
    }

    .topbar-actions { display: flex; gap: 10px; }
    .btn {
      padding: 6px 14px;
      border-radius: 6px;
      border: 1px solid var(--border);
      background: var(--bg-tertiary);
      color: var(--text-primary);
      font-size: 12px;
      cursor: pointer;
      font-family: inherit;
      transition: all 0.2s;
    }
    .btn:hover { border-color: var(--accent-blue); color: var(--accent-blue); }
    .btn-primary { background: var(--accent-green); color: var(--bg-primary); border-color: var(--accent-green); font-weight: 700; }
    .btn-primary:hover { background: #52d46a; color: var(--bg-primary); }

    /* LAYOUT */
    .layout {
      display: grid;
      grid-template-columns: 220px 1fr;
      min-height: calc(100vh - 57px);
    }

    /* SIDEBAR */
    .sidebar {
      background: var(--bg-secondary);
      border-right: 1px solid var(--border);
      padding: 20px 0;
    }
    .sidebar-section { margin-bottom: 24px; }
    .sidebar-label {
      padding: 4px 16px;
      font-size: 10px;
      color: var(--text-secondary);
      letter-spacing: 2px;
      text-transform: uppercase;
    }
    .nav-item {
      display: flex;
      align-items: center;
      gap: 10px;
      padding: 9px 16px;
      font-size: 13px;
      cursor: pointer;
      transition: all 0.15s;
      border-left: 3px solid transparent;
      color: var(--text-secondary);
    }
    .nav-item:hover { background: var(--bg-tertiary); color: var(--text-primary); }
    .nav-item.active {
      background: var(--glow-green);
      border-left-color: var(--accent-green);
      color: var(--accent-green);
    }
    .nav-badge {
      margin-left: auto;
      background: var(--accent-red);
      color: white;
      border-radius: 10px;
      padding: 1px 7px;
      font-size: 10px;
      font-weight: 700;
    }
    .nav-badge.green { background: var(--accent-green); }

    /* MAIN */
    .main { padding: 24px; overflow-y: auto; }

    /* PAGE HEADER */
    .page-header {
      display: flex;
      justify-content: space-between;
      align-items: flex-start;
      margin-bottom: 24px;
    }
    .page-title { font-size: 22px; font-weight: 700; color: var(--text-primary); }
    .page-subtitle { font-size: 12px; color: var(--text-secondary); margin-top: 4px; }

    /* METRIC CARDS */
    .metrics-grid {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      gap: 16px;
      margin-bottom: 24px;
    }
    .metric-card {
      background: var(--bg-secondary);
      border: 1px solid var(--border);
      border-radius: 10px;
      padding: 18px;
      position: relative;
      overflow: hidden;
      transition: border-color 0.2s;
    }
    .metric-card:hover { border-color: var(--accent-blue); }
    .metric-card::before {
      content: '';
      position: absolute;
      top: 0; left: 0; right: 0;
      height: 2px;
    }
    .metric-card.green::before { background: linear-gradient(90deg, var(--accent-green), transparent); }
    .metric-card.red::before { background: linear-gradient(90deg, var(--accent-red), transparent); }
    .metric-card.blue::before { background: linear-gradient(90deg, var(--accent-blue), transparent); }
    .metric-card.yellow::before { background: linear-gradient(90deg, var(--accent-yellow), transparent); }
    .metric-label { font-size: 11px; color: var(--text-secondary); text-transform: uppercase; letter-spacing: 1px; margin-bottom: 10px; }
    .metric-value { font-size: 32px; font-weight: 700; line-height: 1; }
    .metric-value.green { color: var(--accent-green); }
    .metric-value.red { color: var(--accent-red); }
    .metric-value.blue { color: var(--accent-blue); }
    .metric-value.yellow { color: var(--accent-yellow); }
    .metric-delta { font-size: 11px; margin-top: 8px; }
    .metric-delta.up { color: var(--accent-green); }
    .metric-delta.down { color: var(--accent-red); }
    .metric-icon {
      position: absolute;
      top: 14px; right: 16px;
      font-size: 28px;
      opacity: 0.15;
    }

    /* GRID 2-COL */
    .grid-2 {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 16px;
      margin-bottom: 24px;
    }
    .grid-3-1 {
      display: grid;
      grid-template-columns: 2fr 1fr;
      gap: 16px;
      margin-bottom: 24px;
    }

    /* CARD */
    .card {
      background: var(--bg-secondary);
      border: 1px solid var(--border);
      border-radius: 10px;
      overflow: hidden;
    }
    .card-header {
      padding: 14px 18px;
      border-bottom: 1px solid var(--border);
      display: flex;
      justify-content: space-between;
      align-items: center;
    }
    .card-title { font-size: 13px; font-weight: 600; color: var(--text-primary); }
    .card-body { padding: 18px; }

    /* PIPELINE */
    .pipeline-stages {
      display: flex;
      align-items: center;
      gap: 0;
      padding: 14px 18px;
      overflow-x: auto;
    }
    .pipeline-stage {
      flex: 1;
      min-width: 100px;
      text-align: center;
      position: relative;
    }
    .pipeline-stage:not(:last-child)::after {
      content: '→';
      position: absolute;
      right: -8px;
      top: 50%;
      transform: translateY(-60%);
      color: var(--text-secondary);
      font-size: 18px;
      z-index: 2;
    }
    .stage-icon {
      width: 44px; height: 44px;
      border-radius: 50%;
      margin: 0 auto 8px;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 20px;
      border: 2px solid;
    }
    .stage-icon.passed { border-color: var(--accent-green); background: var(--glow-green); }
    .stage-icon.running {
      border-color: var(--accent-blue);
      background: var(--glow-blue);
      animation: spin 1.5s linear infinite;
    }
    .stage-icon.failed { border-color: var(--accent-red); background: var(--glow-red); }
    .stage-icon.pending { border-color: var(--border); background: var(--bg-tertiary); opacity: 0.5; }
    @keyframes spin { from { transform: rotate(0deg); } to { transform: rotate(360deg); } }
    .stage-name { font-size: 11px; color: var(--text-secondary); }
    .stage-time { font-size: 10px; color: var(--text-secondary); margin-top: 2px; }
    .stage-status { font-size: 10px; font-weight: 700; margin-top: 3px; }
    .stage-status.passed { color: var(--accent-green); }
    .stage-status.running { color: var(--accent-blue); }
    .stage-status.failed { color: var(--accent-red); }

    /* VULNERABILITIES TABLE */
    .vuln-table { width: 100%; border-collapse: collapse; font-size: 12px; }
    .vuln-table th {
      text-align: left;
      padding: 8px 12px;
      color: var(--text-secondary);
      font-size: 10px;
      text-transform: uppercase;
      letter-spacing: 1px;
      border-bottom: 1px solid var(--border);
    }
    .vuln-table td { padding: 10px 12px; border-bottom: 1px solid var(--border); }
    .vuln-table tr:last-child td { border-bottom: none; }
    .vuln-table tr:hover td { background: var(--bg-tertiary); }
    .severity-badge {
      padding: 2px 8px;
      border-radius: 4px;
      font-size: 10px;
      font-weight: 700;
      text-transform: uppercase;
    }
    .sev-critical { background: rgba(248,81,73,0.2); color: var(--accent-red); border: 1px solid var(--accent-red); }
    .sev-high { background: rgba(210,153,34,0.2); color: var(--accent-yellow); border: 1px solid var(--accent-yellow); }
    .sev-medium { background: rgba(88,166,255,0.2); color: var(--accent-blue); border: 1px solid var(--accent-blue); }
    .sev-low { background: rgba(63,185,80,0.2); color: var(--accent-green); border: 1px solid var(--accent-green); }

    /* TERMINAL LOG */
    .terminal {
      background: #0a0c10;
      border: 1px solid var(--border);
      border-radius: 8px;
      font-size: 12px;
      overflow: hidden;
    }
    .terminal-bar {
      background: var(--bg-tertiary);
      padding: 8px 14px;
      display: flex;
      align-items: center;
      gap: 7px;
    }
    .t-dot { width: 11px; height: 11px; border-radius: 50%; }
    .t-red { background: #ff5f57; }
    .t-yellow { background: #ffbd2e; }
    .t-green { background: #28ca41; }
    .t-title { margin-left: 10px; font-size: 11px; color: var(--text-secondary); }
    .terminal-body { padding: 14px; max-height: 240px; overflow-y: auto; }
    .log-line { line-height: 1.8; }
    .log-time { color: var(--text-secondary); }
    .log-info { color: var(--accent-blue); }
    .log-warn { color: var(--accent-yellow); }
    .log-error { color: var(--accent-red); }
    .log-success { color: var(--accent-green); }
    .log-cmd { color: var(--accent-cyan); }

    /* SECURITY SCORE */
    .score-ring {
      width: 110px; height: 110px;
      position: relative;
      margin: 0 auto 12px;
    }
    .score-ring svg { transform: rotate(-90deg); }
    .score-ring-text {
      position: absolute;
      top: 50%; left: 50%;
      transform: translate(-50%, -50%);
      text-align: center;
    }
    .score-num { font-size: 28px; font-weight: 700; color: var(--accent-green); }
    .score-label { font-size: 10px; color: var(--text-secondary); }
    .score-details { font-size: 11px; color: var(--text-secondary); }
    .score-row { display: flex; justify-content: space-between; margin-bottom: 8px; align-items: center; }
    .score-bar-outer { width: 80px; height: 5px; background: var(--bg-tertiary); border-radius: 3px; overflow: hidden; }
    .score-bar-inner { height: 100%; border-radius: 3px; }

    /* EVENTS FEED */
    .event-item { display: flex; gap: 12px; padding: 10px 0; border-bottom: 1px solid var(--border); }
    .event-item:last-child { border-bottom: none; }
    .event-dot-wrap { padding-top: 3px; }
    .event-dot { width: 9px; height: 9px; border-radius: 50%; }
    .event-content { flex: 1; }
    .event-title { font-size: 12px; color: var(--text-primary); margin-bottom: 2px; }
    .event-meta { font-size: 11px; color: var(--text-secondary); }
    .event-time { font-size: 10px; color: var(--text-secondary); white-space: nowrap; }

    /* CONTAINER GRID */
    .container-grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 10px; }
    .container-item {
      background: var(--bg-tertiary);
      border: 1px solid var(--border);
      border-radius: 8px;
      padding: 12px;
      font-size: 11px;
    }
    .container-name { font-weight: 700; color: var(--text-primary); margin-bottom: 5px; }
    .container-status { display: flex; align-items: center; gap: 5px; color: var(--text-secondary); }
    .container-cpu { margin-top: 8px; }
    .mini-bar-outer { height: 4px; background: var(--bg-secondary); border-radius: 2px; margin-top: 3px; }
    .mini-bar-inner { height: 100%; border-radius: 2px; }

    /* TABS */
    .tabs { display: flex; gap: 0; border-bottom: 1px solid var(--border); padding: 0 18px; }
    .tab {
      padding: 10px 16px;
      font-size: 12px;
      cursor: pointer;
      color: var(--text-secondary);
      border-bottom: 2px solid transparent;
      transition: all 0.15s;
    }
    .tab:hover { color: var(--text-primary); }
    .tab.active { color: var(--accent-blue); border-bottom-color: var(--accent-blue); }
    .tab-content { display: none; padding: 16px 18px; }
    .tab-content.active { display: block; }

    /* SCAN PROGRESS */
    .scan-item { margin-bottom: 14px; }
    .scan-name { font-size: 12px; color: var(--text-primary); margin-bottom: 4px; display: flex; justify-content: space-between; }
    .progress-outer { height: 8px; background: var(--bg-tertiary); border-radius: 4px; overflow: hidden; }
    .progress-inner {
      height: 100%;
      border-radius: 4px;
      background: linear-gradient(90deg, var(--accent-green), var(--accent-cyan));
      animation: grow 2s ease forwards;
      width: 0;
    }
    @keyframes grow { to { width: var(--target-width); } }

    /* FOOTER */
    .footer {
      background: var(--bg-secondary);
      border-top: 1px solid var(--border);
      padding: 10px 24px;
      display: flex;
      justify-content: space-between;
      font-size: 11px;
      color: var(--text-secondary);
    }

    /* RESPONSIVE */
    @media (max-width: 900px) {
      .layout { grid-template-columns: 1fr; }
      .sidebar { display: none; }
      .metrics-grid { grid-template-columns: repeat(2, 1fr); }
      .grid-2, .grid-3-1 { grid-template-columns: 1fr; }
      .container-grid { grid-template-columns: repeat(2, 1fr); }
    }

    /* ANIMATED BACKGROUND GRID */
    .topbar-logo .logo-grid {
      display: grid;
      grid-template-columns: repeat(3, 5px);
      gap: 2px;
    }
    .logo-cell {
      width: 5px; height: 5px;
      background: var(--accent-green);
      border-radius: 1px;
      animation: blink 3s infinite;
    }
    .logo-cell:nth-child(odd) { animation-delay: 0.5s; }
    .logo-cell:nth-child(3n) { animation-delay: 1s; }
    @keyframes blink { 0%,80%,100%{opacity:1} 40%{opacity:0.2} }

    .tag { padding: 2px 7px; border-radius: 4px; font-size: 10px; }
    .tag-blue { background: rgba(88,166,255,0.15); color: var(--accent-blue); }
    .tag-green { background: rgba(63,185,80,0.15); color: var(--accent-green); }
    .tag-purple { background: rgba(188,140,255,0.15); color: var(--accent-purple); }

  
