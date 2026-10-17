# Ticket: Desktop PC Erratically Losing Internet Due to IP Address Conflict with Wi-Fi Extenders

| Field | Details |
|---|---|
| **Ticket ID** | INC-0004 |
| **Category** | Networking |
| **Priority** | High (recurring loss of internet on main PC) |
| **Status** | Resolved |
| **Affected Device** | Main desktop PC (no Wi-Fi card, Ethernet only) |
| **Other Devices Involved** | Router, 2 Wi-Fi extenders |
| **Issue Type** | IP address conflict |
| **Connection Type** | Wired (Ethernet) |
| **Issue Duration** | Approximately 3 months |

---

## 1. Problem Description

A client's main desktop PC had been connecting to and disconnecting from the internet erratically for roughly **three months**.

**Reported symptoms:**

- The PC would sometimes connect and work perfectly.
- At other times it would connect, then drop and fail to reconnect.
- The only workaround was to unplug and reset the router, then plug it back in. This worked on some occasions and failed on others.
- The PC has **no Wi-Fi card**, so it relies entirely on a wired Ethernet connection.

**Impact:** The client's main computer had unreliable internet for months, and the router had to be repeatedly power-cycled to try to restore it.

---

## 2. Initial Assessment

Intermittent connectivity on a wired PC could point to several causes:

- Router settings or router fault
- PC network settings or network adapter fault
- Faulty Ethernet cable or port
- A conflict elsewhere on the network (such as duplicate IP addresses)

**Plan:** Rule out the PC, cabling, and router one at a time, then examine the wider network for anything interfering.

---

## 3. Troubleshooting Steps

1. **Checked all router settings and all PC network settings.** Everything appeared correct.
2. **Tested a static IP address** on the PC with a direct, static connection to the router. The problem persisted.
3. **Replaced the Ethernet cable** with a different one. The problem persisted.
4. **Tried a USB-to-Ethernet adapter** in the PC to rule out the built-in network port. The problem persisted.
5. **Tested a different router.** The same problems occurred, ruling out the router as the cause.
6. **Worked methodically through the network and the router's settings** in detail, reviewing every connected device.
7. **Discovered two Wi-Fi extenders** on the network that appeared to be using the **same IP address as the PC**, causing an IP conflict.
8. **Disconnected both Wi-Fi extenders.**
9. **Restarted the PC.** It started up and connected to the network instantly, and the connection remained stable.
10. **Reconfigured both Wi-Fi extenders with static IP addresses** connecting to the router.
11. **Verified** that the PC had stable internet and that both Wi-Fi extenders were also online and working.

---

## 4. Resolution

Two Wi-Fi extenders were sharing an IP address with the main PC. When devices on the same network hold the same IP address, the router can't reliably tell them apart, which caused the PC's connection to drop intermittently. Disconnecting the extenders immediately stabilized the PC's connection. Reconnecting them with their own static IP addresses removed the conflict while keeping the extenders working.

**Root cause:** IP address conflict between the desktop PC and two Wi-Fi extenders.

**Fix applied:** Removed the extenders, confirmed the PC was stable, then reconfigured the extenders with static IP addresses so each device has a unique address.

**Result:** The PC and both Wi-Fi extenders all have working internet.

---

## 5. Recommendations for the Client

- Give network devices such as extenders, printers, and servers **static IP addresses** or DHCP reservations, so they never overlap with other devices.
- Keep a simple record of the devices on the network and their IP addresses.
- If connection problems return, check the router's connected-device list for duplicate or unfamiliar addresses before replacing hardware.
- Avoid adding new networking devices without confirming how they receive their IP address.

---

## 6. Skills Demonstrated

- Long-term, intermittent fault diagnosis
- Systematic elimination of hardware (cable, USB adapter, port, router)
- Router and PC network settings review
- IP address conflict identification and resolution
- Static IP configuration on network devices (Wi-Fi extenders)
- Verifying the fix across all affected devices

---

[← Back to ticket index](../README.md)
