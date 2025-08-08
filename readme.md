<!DOCTYPE html>
<html>
<head>
    <title>Auto-Healing Microservices System</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            line-height: 1.6;
            max-width: 900px;
            margin: 0 auto;
            padding: 20px;
            color: #333;
        }
        h1, h2, h3 {
            color: #2c3e50;
        }
        code {
            background: #f4f4f4;
            padding: 2px 5px;
            border-radius: 3px;
            font-family: monospace;
        }
        pre {
            background: #f4f4f4;
            padding: 10px;
            border-radius: 5px;
            overflow-x: auto;
        }
        table {
            width: 100%;
            border-collapse: collapse;
            margin: 20px 0;
        }
        th, td {
            border: 1px solid #ddd;
            padding: 8px;
            text-align: left;
        }
        th {
            background-color: #f2f2f2;
        }
        img.responsive {
            max-width: 100%;
            border: 1px solid #ccc;
            border-radius: 5px;
        }
        .architecture {
            text-align: center;
            margin: 20px 0;
        }
        .small {
            font-size: 0.9em;
            color: #555;
        }
    </style>
</head>
<body>
    <h1>🛡️ Auto-Healing Microservices System</h1>
    <p><em>A self-healing microservice architecture with Docker, Flask, Prometheus, and Grafana</em></p>

    <div class="architecture">
        <h2>📦 System Architecture</h2>
        <img src="Self-Healing Microservices Workflow.png" alt="System Architecture Diagram" class="responsive">
    </div>

    <h2>🚀 Quick Start</h2>
    <pre><code># Clone and deploy
git clone https://github.com/Dasmat13/autohealing-microservices.git
cd autohealing-microservices
docker-compose up -d --build</code></pre>

    <h2>🌐 Access Endpoints</h2>
    <table>
        <tr>
            <th>Component</th>
            <th>URL</th>
            <th>Credentials</th>
        </tr>
        <tr>
            <td>Service A</td>
            <td><code>http://localhost/a</code></td>
            <td>-</td>
        </tr>
        <tr>
            <td>Service B</td>
            <td><code>http://localhost/b</code></td>
            <td>-</td>
        </tr>
        <tr>
            <td>Prometheus</td>
            <td><code>http://localhost:9090</code></td>
            <td>-</td>
        </tr>
        <tr>
            <td>Grafana</td>
            <td><code>http://localhost:3000</code></td>
            <td>admin:admin</td>
        </tr>
    </table>

    <h2>🔧 Key Features</h2>
    <ul>
        <li><strong>Self-healing</strong>: Watchtower auto-restarts failed containers</li>
        <li><strong>Monitoring</strong>: Prometheus scrapes metrics every 15s</li>
        <li><strong>Visualization</strong>: Pre-configured Grafana dashboards</li>
        <li><strong>Load Balancing</strong>: Nginx distributes traffic</li>
    </ul>

    <h2 id="grafana-setup">📊 Grafana & Prometheus — Quick Setup Notes</h2>
    <ol>
        <li>Open Grafana: <code>http://localhost:3000</code> (admin/admin)</li>
        <li>Add Prometheus data source: URL → <code>http://prometheus:9090</code> and click <strong>Save & Test</strong></li>
        <li>Import dashboards:
            <ul>
                <li>Docker metrics dashboard: Grafana dashboard ID <strong>893</strong> (requires <code>cadvisor</code> scraping)</li>
                <li>Or import custom dashboard JSON (service metrics) — see <code>grafana/flask-dashboard.json</code></li>
            </ul>
        </li>
        <li>If Grafana shows "No data": verify Prometheus targets at <code>http://localhost:9090/targets</code></li>
    </ol>

    <div class="architecture">
        <h2>📷 Prometheus Dashboard Screenshot</h2>
        <p class="small">(Save as <code>prometheus-dashboard.png</code> in repo root)</p>
        <img src="prometheus-dashboard.png" alt="Prometheus Dashboard Screenshot" class="responsive">
    </div>

    <div class="architecture">
        <h2>📷 Grafana Dashboard Screenshot</h2>
        <p class="small">(Save as <code>grafana-dashboard.png</code> in repo root)</p>
        <img src="grafana-dashboard.png" alt="Grafana Dashboard Screenshot" class="responsive">
    </div>

    <h2>🛠️ Troubleshooting</h2>
    <div class="architecture">
        <img src="trouble.png" alt="Troubleshooting Flowchart" class="responsive">
    </div>
    
    <p>Common fixes:</p>
    <pre><code># Rebuild single service
docker-compose up -d --build service-a

# Check container health
docker ps --filter "health=unhealthy"</code></pre>

    <h2>📚 Documentation</h2>
    <ul>
        <li><a href="./prometheus/README.md">Prometheus Configuration</a></li>
        <li><a href="./service-a/README.md">Flask Service Setup</a></li>
    </ul>

    <h2>📜 License</h2>
    <p>MIT © 2023 Dasmat13</p>
</body>
</html>
