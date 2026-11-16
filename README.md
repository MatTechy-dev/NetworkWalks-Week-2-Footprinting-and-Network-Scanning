# 🔐 Task 1: Cybersecurity Lab Environment Setup

**Project:** Virtual Cybersecurity and Ethical Hacking Laboratory  
**Author:** Mathew  
**Program:** Cybersecurity & Ethical Hacking Internship  
**Training Organization:** NetworkWalks  
**Host Device:** Dell Latitude E5570  
**Environment:** Kali Linux on Oracle VirtualBox  
**Purpose:** Cybersecurity learning, networking, reconnaissance, and authorized security testing.

---

## 📌 1. Project Overview

This project documents the process of setting up my personal virtual cybersecurity laboratory using Oracle VirtualBox and Kali Linux.

The purpose of this laboratory is to provide a controlled environment where I can learn cybersecurity fundamentals, understand networking concepts, practice reconnaissance, and develop practical skills in ethical hacking.

I configured a dedicated VirtualBox NAT Network to allow my virtual machine to obtain an IP address and access the internet. I also worked on troubleshooting network connectivity issues, understanding DHCP, and verifying communication between my virtual machine and external networks.

This laboratory will serve as the foundation for my future cybersecurity practical exercises.

## 🎯 2. Project Objectives

The main objectives of this task are to:

- Set up Oracle VirtualBox on my Windows laptop.
- Install and run Kali Linux as a virtual machine.
- Create and configure a VirtualBox NAT Network.
- Understand IPv4 addressing, subnet masks, gateways, and DNS.
- Configure Kali Linux to obtain an IP address automatically using DHCP.
- Test internet and network connectivity.
- Troubleshoot common virtual network configuration problems.
- Understand the importance of virtual machine snapshots.
- Prepare a controlled environment for future cybersecurity exercises.

## 💻 3. Laptop and Lab Specifications

| Component | Configuration |
|---|---|
| Host device | Dell Latitude E5570 |
| Host operating system | Windows |
| Virtualization software | Oracle VirtualBox |
| Guest operating system | Kali Linux |
| Network configuration | NAT Network |
| Network name | `NatNetwork` |
| IPv4 network prefix | `10.0.0.0/24` |
| Kali network interface | `eth0` |
| Connection profile | Wired connection 1 |
| IPv4 configuration | Automatic (DHCP) |
| Assigned Kali IP | `10.0.0.3` |
| Default gateway | `10.0.0.1` |
| DNS configuration | Verify from current system settings |

*Note: Hardware specifications, software versions, and network settings should be verified against the actual system before final submission.*

## 🏗️ 4. Lab Architecture

The laboratory uses Oracle VirtualBox to run Kali Linux on my Windows laptop.

```text
             Dell Latitude E5570
                 Windows Host
                      |
                      |
               Oracle VirtualBox
                      |
                      |
                  Kali Linux
                  (eth0)
                10.0.0.3
                      |
                      |
                 NatNetwork
                10.0.0.0/24
                      |
                      |
                Default Gateway
                  10.0.0.1
                      |
                      |
                  Internet
```

The NAT Network provides connectivity for virtual machines connected to it. It can also support communication between virtual machines on the same network.

Future exercises may involve adding intentionally vulnerable machines for authorized testing.

## ⚙️ 5. Implementation Procedure

### Step 1: Install Oracle VirtualBox

I installed Oracle VirtualBox on my Windows laptop to create and manage virtual machines.

VirtualBox provides a platform for running Kali Linux without replacing my existing Windows operating system.

### Step 2: Set Up Kali Linux

I imported and started Kali Linux in Oracle VirtualBox.

Kali Linux serves as my primary cybersecurity environment because it provides access to various tools used for networking, reconnaissance, vulnerability assessment, and security testing.

### Step 3: Configure the NAT Network

I created a dedicated NAT Network in VirtualBox with the following configuration:

| Setting | Value |
|---|---|
| Network name | `NatNetwork` |
| IPv4 prefix | `10.0.0.0/24` |
| DHCP | Enabled |
| Network type | NAT Network |

This configuration provides a shared virtual network for future lab machines.

### Step 4: Configure Kali Linux Networking

Initially, I experienced network connectivity problems because the Kali network connection had a manually assigned IP address that conflicted with another device on the network.

The conflicting address was:

`10.0.0.2`

I investigated the issue and changed the IPv4 configuration from manual addressing to automatic DHCP.

The connection profile was updated using NetworkManager.

After reconnecting the network interface, Kali Linux successfully obtained:

`10.0.0.3/24`

This resolved the IP address conflict.

### Step 5: Test Network Connectivity

After correcting the network configuration, I performed connectivity tests.

**Check network interface:**

```bash
ip addr show eth0
```

**Check routing information:**

```bash
ip route
```

**Test internet connectivity using an IP address:**

```bash
ping -c 4 8.8.8.8
```

**Test DNS resolution:**

```bash
ping -c 4 google.com
```

The connectivity tests returned four successful replies with no packet loss in each test.

This confirmed that Kali Linux could communicate with an external IP address and resolve domain names.

## 🔎 6. Lab Verification Results

| Test | Result |
|---|---|
| Kali Linux startup | Successful |
| VirtualBox NAT Network | Configured |
| DHCP configuration | Automatic |
| Kali IPv4 address | `10.0.0.3` |
| Gateway connectivity | Verify separately |
| External IP connectivity | Successful |
| DNS resolution | Successful |
| IP address conflict | Resolved |

## 🐞 7. Troubleshooting and Challenges

### Problem 1: Kali Linux Could Not Access the Internet

I initially experienced difficulties connecting Kali Linux to the internet.

After investigating the network configuration, I discovered that the connection was using a manually assigned IP address that was already in use.

### Problem 2: IP Address Conflict

The network logs indicated that `10.0.0.2` was already being used by another device.

**Solution:**

I changed the IPv4 method from manual to automatic (DHCP).

This allowed Kali Linux to obtain another available address, `10.0.0.3`.

### Problem 3: Network Connectivity Verification

After correcting the configuration, I used Linux networking commands and ping tests to verify the connection.

These troubleshooting activities helped me understand the importance of correct IP configuration and DHCP in virtual networking.

## 🧠 8. What I Learned

Through this exercise, I developed a better understanding of:

1. **Virtualization:** How to run another operating system inside my existing operating system.
2. **VirtualBox:** How to configure and manage virtual machines.
3. **NAT Networking:** How virtual machines connect through a shared virtual network.
4. **DHCP:** How devices automatically obtain IP addresses.
5. **IPv4 Addressing:** How IP addresses and subnet masks identify devices and networks.
6. **Default Gateway:** How network traffic is forwarded to external networks.
7. **DNS:** How domain names are resolved into
