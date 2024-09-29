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
    WebServer->> Botnet: Error Response 


Step 1: Attacker sends the command.
Attacker initiates the attack.
Action is sending command to the Botnet and triggering the DDoS attack.

Step 2: Botnet Activation.
Botnet is a network of compromised bots
Action: The botnet will activate and floods the target with requests.

Step 3: Flooding requests.
Each botnet will send many requests to the web servers.
The target web server will potentially be overwhelmed by requests.

Step 4: Alerting the firewall
Server will recognize abnormal traffic and will send an alert to the firewall.

Step 5: Traffic Analysis
The firewall will analyze incoming traffic to find any malicious patterns/anomalies.

Step 6: Allow/Drop Requests

Step 7: Error Responses
The server will send error responses.

Step 8: Botnet Deactivation 
The botnet potentially deactivates after the attack is completed.