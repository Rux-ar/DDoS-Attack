# DDoS-Attack

sequenceDiagram
    participant Attacker
    participant Botnet (Multiple Compromised Systems)
    participant WebServer
    participant Firewall
    
    Attacker->> Botnet: Send Attack Command
    activate Botnet
    Botnet->> WebServer: Flood of Requests (HTTP GET, etc.)
    loop for Multiple Requests
    WebServer->> Firewall: Alert - Traffic Overload
    Firewall->> WebServer: Analyze Traffic
    alt Normal Traffic
        Firewall->> WebServer: Allow Requests
    else DDoS Attack
        Firewall->> WebServer: Drop Excess Requests
    end
    deactivate Botnet
    WebServer->> Botnet: Error Response (e.g., 429 Too Many Requests)