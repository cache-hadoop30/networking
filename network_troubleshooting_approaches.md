
# Network Troubleshooting Approaches Using the OSI Model

This document explains three common troubleshooting approaches — **Top-Down**, **Bottom-Up**, and **Hybrid** — applied to three real-world scenarios.

---

## 🧭 Scenario 1: No Internet Connection

### 🔹 Top-Down Approach
- Start at Layer 7: Check if websites load in a browser.
- Try other browsers or applications to isolate if app-related.
- Layer 3: Use ping or tracert to verify IP configuration and gateway.
- Layer 1: Verify cable connections and Wi-Fi link status.
- **Conclusion:** Unplugged cable or misconfigured DNS.

### 🔹 Bottom-Up Approach
- Layer 1: Inspect cables, connectors, and NIC lights.
- Layer 2: Verify link detection and MAC address on switch.
- Layer 3: Confirm IP and gateway setup using ipconfig.
- Layer 4: Test external connectivity (ping 8.8.8.8).
- **Conclusion:** DNS failure or cable issue.

### 🔹 Hybrid Approach
- Test website → fails.
- Check IP configuration → none assigned.
- Inspect cable → unplugged.
- Reconnect and verify internet access → works.
- **Conclusion:** Fault isolated quickly through flexible checking.

---

## 🧭 Scenario 2: Slow Internet

### 🔹 Top-Down Approach
- Layer 7: Check if only one website/app is slow or all.
- Layer 4: Run speed test or ping test to identify delay.
- Layer 3: Check routing, traceroute for latency.
- Layer 2–1: Inspect Wi-Fi signal or cable integrity.
- **Conclusion:** High latency caused by weak Wi-Fi signal.

### 🔹 Bottom-Up Approach
- Layer 1: Check cable or Wi-Fi signal strength.
- Layer 2: Verify duplex and speed mismatch on switch port.
- Layer 3: Check for routing loops or congested network.
- Layer 7: Test application loading time.
- **Conclusion:** Bottleneck found in physical layer or switch port.

### 🔹 Hybrid Approach
- Observe slow website loading → test ping → high latency.
- Jump to Layer 1 → Weak Wi-Fi detected.
- Move back to Layer 7 → Website loads fine after reconnecting.
- **Conclusion:** Hybrid saves time by jumping between likely layers.

---

## 🧭 Scenario 3: Can't Connect to Shared Printer

### 🔹 Top-Down Approach
- Layer 7: Verify printer appears in the OS or print queue.
- Layer 6–5: Check sharing permissions and driver availability.
- Layer 3: Ping printer’s IP address to test reachability.
- Layer 1–2: Ensure printer is powered on and connected to network.
- **Conclusion:** Access denied due to incorrect sharing permissions.

### 🔹 Bottom-Up Approach
- Layer 1: Check printer cable or power connection.
- Layer 2: Verify printer’s MAC address in switch or access point.
- Layer 3: Confirm correct IP configuration of printer.
- Layer 7: Print test page from computer.
- **Conclusion:** Printer offline due to network disconnection.

### 🔹 Hybrid Approach
- Ping printer → fails.
- Check cable connection → loose Ethernet cable.
- Reconnect → Ping success → test print works.
- **Conclusion:** Hybrid approach finds the issue faster.

---

## 📊 Summary Table

| Approach | Starting Layer | Typical Role | When to Use |
|-----------|----------------|---------------|--------------|
| **Top-Down** | Application (L7) | Helpdesk / SysAdmin | When issue appears at user/application side |
| **Bottom-Up** | Physical (L1) | Network Engineer | When hardware or connectivity is suspected |
| **Hybrid** | Flexible | Experienced Technician | When issue is complex or unclear |
