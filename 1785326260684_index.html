<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>AI Wi-Fi Sentinel & Security Dashboard</title>
    <!-- Icons & Styling -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <!-- Chart.js -->
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <!-- QRCode.js -->
    <script src="https://cdnjs.cloudflare.com/ajax/libs/qrcodejs/1.0.0/qrcode.min.js"></script>
    <!-- jsPDF -->
    <script src="https://cdnjs.cloudflare.com/ajax/libs/jspdf/2.5.1/jspdf.umd.min.js"></script>

    <style>
        :root {
            --bg-dark: #0f172a;
            --card-bg: #1e293b;
            --accent-blue: #38bdf8;
            --accent-green: #22c55e;
            --accent-yellow: #eab308;
            --accent-red: #ef4444;
            --text-light: #f8fafc;
            --text-muted: #94a3b8;
            --border-color: #334155;
        }

        * { box-sizing: border-box; margin: 0; padding: 0; font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif; }
        body { background-color: var(--bg-dark); color: var(--text-light); padding: 20px; }

        .header { display: flex; justify-content: space-between; align-items: center; margin-bottom: 25px; padding-bottom: 15px; border-bottom: 1px solid var(--border-color); }
        .header h1 { font-size: 1.8rem; color: var(--accent-blue); display: flex; align-items: center; gap: 10px; }
        
        .grid-container { display: grid; grid-template-columns: repeat(auto-fit, minmax(320px, 1fr)); gap: 20px; }
        
        .card { background: var(--card-bg); border: 1px solid var(--border-color); border-radius: 12px; padding: 20px; box-shadow: 0 4px 15px rgba(0,0,0,0.3); }
        .card h2 { font-size: 1.2rem; margin-bottom: 15px; color: var(--text-light); display: flex; align-items: center; gap: 8px; border-bottom: 1px solid rgba(255,255,255,0.05); padding-bottom: 8px; }

        /* Form elements */
        .form-group { margin-bottom: 15px; }
        .form-group label { display: block; margin-bottom: 5px; font-size: 0.85rem; color: var(--text-muted); }
        .form-control { width: 100%; padding: 10px; border-radius: 6px; background: #0f172a; border: 1px solid var(--border-color); color: #fff; outline: none; }
        .form-control:focus { border-color: var(--accent-blue); }

        /* Password meter */
        .meter-bar { height: 8px; border-radius: 4px; background: #334155; margin-top: 8px; overflow: hidden; }
        .meter-fill { height: 100%; width: 0%; transition: width 0.3s, background-color 0.3s; }

        /* Score Display */
        .score-circle { width: 120px; height: 120px; border-radius: 50%; border: 8px solid var(--border-color); display: flex; flex-direction: column; align-items: center; justify-content: center; margin: 0 auto 15px; }
        .score-val { font-size: 2rem; font-weight: bold; }
        
        /* Badges */
        .badge { padding: 4px 8px; border-radius: 4px; font-size: 0.75rem; font-weight: bold; text-transform: uppercase; }
        .badge-danger { background: rgba(239, 68, 68, 0.2); color: var(--accent-red); border: 1px solid var(--accent-red); }
        .badge-warning { background: rgba(234, 179, 8, 0.2); color: var(--accent-yellow); border: 1px solid var(--accent-yellow); }
        .badge-success { background: rgba(34, 197, 94, 0.2); color: var(--accent-green); border: 1px solid var(--accent-green); }

        /* Device Table */
        .device-table { width: 100%; border-collapse: collapse; margin-top: 10px; font-size: 0.85rem; }
        .device-table th, .device-table td { padding: 8px; text-align: left; border-bottom: 1px solid var(--border-color); }
        .device-table th { color: var(--text-muted); font-weight: 600; }

        /* QR Container */
        #qrcode { display: flex; justify-content: center; padding: 15px; background: white; border-radius: 8px; margin-top: 10px; width: fit-content; margin-left: auto; margin-right: auto; }

        .btn { background: var(--accent-blue); color: #000; font-weight: bold; padding: 10px 15px; border: none; border-radius: 6px; cursor: pointer; width: 100%; margin-top: 10px; transition: opacity 0.2s; }
        .btn:hover { opacity: 0.9; }
        
        .recommendation-list { list-style: none; font-size: 0.85rem; }
        .recommendation-list li { margin-bottom: 8px; display: flex; align-items: flex-start; gap: 8px; }

        /* Signal Meter */
        .signal-meter { display: flex; align-items: flex-end; gap: 4px; height: 30px; }
        .signal-bar { flex: 1; background: var(--border-color); border-radius: 2px 2px 0 0; transition: background 0.3s; }
    </style>
</head>
<body>

    <div class="header">
        <h1><i class="fa-solid fa-wifi"></i> Wi-Fi Security Auditor 🛜<div id="live-time" style="color: var(--text-muted); font-size: 0.9rem;"></div>
    </div>

    <div class="grid-container">

        <!-- 1. Network Configuration & Health Dashboard -->
        <div class="card">
            <h2><i class="fa-solid fa-sliders"></i> Network Config & Telemetry</h2>
            <div class="form-group">
                <label>Network SSID</label>
                <input type="text" id="ssid" class="form-control" value="Home_Secure_WiFi" oninput="updateAudit()">
            </div>
            <div class="form-group">
                <label>Security Encryption Mode</label>
                <select id="security-type" class="form-control" onchange="updateAudit()">
                    <option value="OPEN">Open (No Password / Unencrypted)</option>
                    <option value="WEP">WEP (Legacy / Insecure)</option>
                    <option value="WPA">WPA Enterprise/Personal (Outdated)</option>
                    <option value="WPA2" selected>WPA2-PSK (AES)</option>
                    <option value="WPA3">WPA3-SAE (Modern Standard)</option>
                </select>
            </div>
            <div class="form-group">
                <label>Signal Strength (-dBm)</label>
                <input type="range" id="signal-slider" min="-90" max="-30" value="-55" class="form-control" oninput="updateSignalMeter(this.value)">
                <div style="display:flex; justify-content:space-between; margin-top: 5px;">
                    <span id="signal-value" style="font-size: 0.85rem; color: var(--accent-blue);">-55 dBm</span>
                    <div class="signal-meter" id="signal-bars">
                        <div class="signal-bar" style="height: 25%;"></div>
                        <div class="signal-bar" style="height: 50%;"></div>
                        <div class="signal-bar" style="height: 75%;"></div>
                        <div class="signal-bar" style="height: 100%;"></div>
                    </div>
                </div>
            </div>
        </div>

        <!-- 2. Password Strength Guidelines -->
        <div class="card">
            <h2><i class="fa-solid fa-key"></i> Password Analyzer</h2>
            <div class="form-group">
                <label>Enter Wi-Fi Password</label>
                <input type="password" id="wifi-password" class="form-control" placeholder="Type password..." oninput="updateAudit()">
            </div>
            <div>
                <span id="pass-strength-label" style="font-size: 0.85rem; font-weight: bold;">Strength: N/A</span>
                <div class="meter-bar"><div id="meter-fill" class="meter-fill"></div></div>
            </div>
            <ul class="recommendation-list" style="margin-top: 15px;">
                <li id="rule-length"><i class="fa-solid fa-circle-xmark" style="color:var(--accent-red)"></i> At least 12 characters</li>
                <li id="rule-cases"><i class="fa-solid fa-circle-xmark" style="color:var(--accent-red)"></i> Mixed case letters & numbers</li>
                <li id="rule-symbols"><i class="fa-solid fa-circle-xmark" style="color:var(--accent-red)"></i> Includes special symbols (!@#$)</li>
            </ul>
        </div>

        <!-- 3. AI Security Score & Detected Vulnerabilities -->
        <div class="card" style="text-align: center;">
            <h2><i class="fa-solid fa-brain"></i> AI Security Score</h2>
            <div class="score-circle" id="score-circle">
                <span class="score-val" id="score-val">0%</span>
                <span id="score-status" style="font-size:0.7rem; text-transform:uppercase;">Critical</span>
            </div>
            <div style="text-align: left; margin-top: 10px;">
                <h3 style="font-size: 0.9rem; margin-bottom: 5px; color: var(--text-muted);">Detected Weaknesses:</h3>
                <div id="vulnerability-tags" style="display: flex; flex-wrap: wrap; gap: 5px;"></div>
            </div>
        </div>

        <!-- 4. Security Recommendations -->
        <div class="card">
            <h2><i class="fa-solid fa-shield-halved"></i> Security Recommendations</h2>
            <ul class="recommendation-list" id="recommendation-list">
                <!-- Dynamically populated -->
            </ul>
        </div>

        <!-- 5. Connected Device Monitoring -->
        <div class="card">
            <h2><i class="fa-solid fa-network-wired"></i> Connected Device Inspector</h2>
            <table class="device-table">
                <thead>
                    <tr>
                        <th>Device Name</th>
                        <th>IP Address</th>
                        <th>Risk Level</th>
                    </tr>
                </thead>
                <tbody id="device-list">
                    <tr><td>Gateway Router</td><td>192.168.1.1</td><td><span class="badge badge-success">Safe</span></td></tr>
                    <tr><td>Smart TV (IoT)</td><td>192.168.1.102</td><td><span class="badge badge-warning">Medium</span></td></tr>
                    <tr><td>Unknown Host</td><td>192.168.1.145</td><td><span class="badge badge-danger">High</span></td></tr>
                </tbody>
            </table>
        </div>

        <!-- 6. QR Code & Export Tools -->
        <div class="card">
            <h2><i class="fa-solid fa-qrcode"></i> Fast Connect & Reports</h2>
            <div id="qrcode"></div>
            <button class="btn" onclick="generatePDFReport()"><i class="fa-solid fa-file-pdf"></i> Download PDF Security Report</button>
        </div>

    </div>

    <script>
        // Initialize Realtime Clock
        setInterval(() => {
            document.getElementById('live-time').innerText = new Date().toLocaleString();
        }, 1000);

        function updateSignalMeter(val) {
            document.getElementById('signal-value').innerText = val + " dBm";
            const bars = document.querySelectorAll('.signal-bar');
            let activeBars = 1;
            if (val > -50) activeBars = 4;
            else if (val > -65) activeBars = 3;
            else if (val > -80) activeBars = 2;

            bars.forEach((bar, index) => {
                if (index < activeBars) {
                    bar.style.background = 'var(--accent-blue)';
                } else {
                    bar.style.background = 'var(--border-color)';
                }
            });
        }

        function evaluatePassword(pwd) {
            let score = 0;
            const checks = {
                length: pwd.length >= 12,
                cases: /[a-z]/.test(pwd) && /[A-Z]/.test(pwd) && /[0-9]/.test(pwd),
                symbols: /[^a-zA-Z0-9]/.test(pwd)
            };

            // Update guidelines UI
            updateRuleUI('rule-length', checks.length);
            updateRuleUI('rule-cases', checks.cases);
            updateRuleUI('rule-symbols', checks.symbols);

            if (pwd.length > 0) score += 20;
            if (pwd.length >= 8) score += 20;
            if (checks.length) score += 20;
            if (checks.cases) score += 20;
            if (checks.symbols) score += 20;

            return { score, checks };
        }

        function updateRuleUI(elementId, passed) {
            const el = document.getElementById(elementId);
            if (passed) {
                el.innerHTML = `<i class="fa-solid fa-circle-check" style="color:var(--accent-green)"></i> ${el.innerText.substring(2)}`;
            } else {
                el.innerHTML = `<i class="fa-solid fa-circle-xmark" style="color:var(--accent-red)"></i> ${el.innerText.substring(2)}`;
            }
        }

        function updateAudit() {
            const ssid = document.getElementById('ssid').value;
            const secType = document.getElementById('security-type').value;
            const pwd = document.getElementById('wifi-password').value;

            const passAnalysis = evaluatePassword(pwd);
            let totalScore = passAnalysis.score * 0.5; // Password represents 50% of total score
            
            let vulnTags = [];
            let recommendations = [];

            // Encryption Protocol Weighting (50% of total score)
            switch (secType) {
                case 'OPEN':
                    vulnTags.push('<span class="badge badge-danger">Unencrypted Traffic</span>');
                    recommendations.push('<li><i class="fa-solid fa-triangle-exclamation" style="color:var(--accent-red)"></i> Upgrade immediately to WPA2 or WPA3 encryption. Open Wi-Fi exposes credentials.</li>');
                    break;
                case 'WEP':
                    vulnTags.push('<span class="badge badge-danger">Deprecated WEP Cipher</span>');
                    recommendations.push('<li><i class="fa-solid fa-triangle-exclamation" style="color:var(--accent-red)"></i> WEP can be compromised in seconds. Migrate to WPA3 or WPA2-AES immediately.</li>');
                    totalScore += 10;
                    break;
                case 'WPA':
                    vulnTags.push('<span class="badge badge-warning">Weak WPA1 Standard</span>');
                    recommendations.push('<li><i class="fa-solid fa-triangle-exclamation" style="color:var(--accent-yellow)"></i> Upgrade to WPA2/WPA3 to mitigate handshake decryption attacks.</li>');
                    totalScore += 25;
                    break;
                case 'WPA2':
                    totalScore += 40;
                    recommendations.push('<li><i class="fa-solid fa-circle-info" style="color:var(--accent-blue)"></i> Ensure Management Frame Protection (PMF) is enabled if supported by hardware.</li>');
                    break;
                case 'WPA3':
                    totalScore += 50;
                    recommendations.push('<li><i class="fa-solid fa-circle-check" style="color:var(--accent-green)"></i> Network uses modern WPA3 SAE resisting offline dictionary attacks.</li>');
                    break;
            }

            if (pwd.length < 8 && secType !== 'OPEN') {
                vulnTags.push('<span class="badge badge-danger">Short Password</span>');
                recommendations.push('<li><i class="fa-solid fa-key" style="color:var(--accent-red)"></i> Password is under 8 characters and prone to brute-force dictionary attacks.</li>');
            }

            // Update Meter Visuals
            const meterFill = document.getElementById('meter-fill');
            const passLabel = document.getElementById('pass-strength-label');
            meterFill.style.width = passAnalysis.score + '%';

            if (passAnalysis.score < 40) {
                meterFill.style.backgroundColor = 'var(--accent-red)';
                passLabel.innerText = 'Strength: Weak';
            } else if (passAnalysis.score < 80) {
                meterFill.style.backgroundColor = 'var(--accent-yellow)';
                passLabel.innerText = 'Strength: Moderate';
            } else {
                meterFill.style.backgroundColor = 'var(--accent-green)';
                passLabel.innerText = 'Strength: Strong';
            }

            // Update AI Circle Visuals
            totalScore = Math.round(totalScore);
            const scoreCircle = document.getElementById('score-circle');
            document.getElementById('score-val').innerText = totalScore + '%';

            if (totalScore < 40) {
                scoreCircle.style.borderColor = 'var(--accent-red)';
                document.getElementById('score-status').innerText = 'CRITICAL RISK';
            } else if (totalScore < 75) {
                scoreCircle.style.borderColor = 'var(--accent-yellow)';
                document.getElementById('score-status').innerText = 'MODERATE RISK';
            } else {
                scoreCircle.style.borderColor = 'var(--accent-green)';
                document.getElementById('score-status').innerText = 'SECURE';
            }

            document.getElementById('vulnerability-tags').innerHTML = vulnTags.length ? vulnTags.join('') : '<span class="badge badge-success">No Critical Flaws</span>';
            document.getElementById('recommendation-list').innerHTML = recommendations.join('');

            // Generate QR Code
            generateQRCode(ssid, pwd, secType);
        }

        function generateQRCode(ssid, pwd, type) {
            const qrContainer = document.getElementById("qrcode");
            qrContainer.innerHTML = "";
            if (!ssid) return;
            
            // Format Wi-Fi QR Code string standard: WIFI:T:WPA;S:mynetwork;P:mypass;;
            const qrString = `WIFI:T:${type};S:${ssid};P:${pwd};;`;
            new QRCode(qrContainer, {
                text: qrString,
                width: 110,
                height: 110,
                colorDark: "#0f172a",
                colorLight: "#ffffff",
                correctLevel: QRCode.CorrectLevel.H
            });
        }

        function generatePDFReport() {
            const { jsPDF } = window.jspdf;
            const doc = new jsPDF();

            const ssid = document.getElementById('ssid').value;
            const secType = document.getElementById('security-type').value;
            const score = document.getElementById('score-val').innerText;

            doc.setFontSize(18);
            doc.text("Wi-Fi Security & Vulnerability Audit Report", 14, 20);
            
            doc.setFontSize(11);
            doc.text(`Generated on: ${new Date().toLocaleString()}`, 14, 30);
            doc.text(`Network SSID: ${ssid}`, 14, 40);
            doc.text(`Encryption Type: ${secType}`, 14, 48);
            doc.text(`Overall AI Security Rating: ${score}`, 14, 56);

            doc.setFontSize(14);
            doc.text("Audit Recommendations:", 14, 70);
            
            doc.setFontSize(10);
            const items = document.querySelectorAll('#recommendation-list li');
            let y = 80;
            items.forEach((item) => {
                doc.text(`- ${item.innerText}`, 14, y);
                y += 8;
            });

            doc.save(`WiFi_Security_Report_${ssid}.pdf`);
        }

        // Initialize on Load
        updateSignalMeter(-55);
        updateAudit();
    </script>
</body>
</html>
