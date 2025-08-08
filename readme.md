<!DOCTYPE html>
<html>
<head>
    <title>Auto-Healing Microservices System</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            line-height: 1.6;
            max-width: 800px;
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
        img {
            max-width: 100%;
        }
        .architecture {
            text-align: center;
            margin: 20px 0;
        }
    </style>
</head>
<body>
    <h1>🛡️ Auto-Healing Microservices System</h1>
    <p><em>A self-healing microservice architecture with Docker, Flask, Prometheus, and Grafana</em></p>

    <div class="architecture">
        <h2>📦 System Architecture</h2>
        <img src="Self-Healing Microservices Workflow.png" alt="System Architecture Diagram">
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

    <h2>🛠️ Troubleshooting</h2>
    <div class="architecture">
        <img src="trouble.png" alt="Troubleshooting Flowchart">
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