# AIHome Linux Server User Guide

**Computer Science Department Remote Computing Resources**  
**Updated: September 2026**

---

## 1. Overview

The Computer Science Department provides centralized Linux computing resources for coursework, research, machine learning, artificial intelligence (AI), data analytics, and high-performance computing (HPC).

**Primary Server**

| Server | Hostname | IP Address |
|----------|----------|----------|
| AIHome | `aihome.bmt.lamar.edu` | `140.158.131.1` |

Users access AIHome remotely using their Lamar University credentials through VPN and SSH.

---

## 2. System Resources

### AIHome Server

| Component | Specification |
|------------|--------------|
| Server Model | Dell PowerEdge R750XA |
| Processors | 2 × Intel Xeon Silver 4309Y |
| CPU Cores | 16 Cores / 32 Threads |
| Memory | 503 GB RAM |
| GPUs | 2 × NVIDIA A100 |
| GPU Memory | 80 GB per GPU |
| Storage | Shared 8 TB Storage |

### GPU Capabilities

- 80 GB GPU memory per GPU
- Up to 156 TFLOPS FP32 performance
- Up to 19.5 TFLOPS FP64 performance

Supported workloads:

- Deep Learning
- Artificial Intelligence
- Scientific Computing
- Data Analytics
- Large Language Models (LLMs)
  

---

## 3. Account Information

Use your Lamar University account credentials.

**Username**

```text
yourLUusername
```

**Password**

```text
Your Lamar University password
```

Do not include `@lamar.edu` in your username.

---

## 4. Remote Access Requirements

### Step 1: Connect to the Lamar University VPN

| Setting | Value |
|----------|----------|
| Remote Gateway | `luvpn.lamar.edu` |
| Port | `10443` |
| Authentication | Two-Step Authentication Required |

VPN Instructions:

<https://www.lamar.edu/it-services-and-support/remote-access-service.html>

### Important Notes

- VPN access is required for off-campus connections.
- Multi-factor authentication (MFA) is mandatory.
- Verify the VPN is connected before using SSH or JupyterHub.

---

## 5. SSH Access

### Windows Clients

- MobaXterm: <https://mobaxterm.mobatek.net>
- PuTTY: <https://www.putty.org>

### macOS and Linux

Use the built-in Terminal application.

### SSH Login Examples

```bash
ssh username@aihome.bmt.lamar.edu
```

or

```bash
ssh username@140.158.131.1
```

Example:

```bash
ssh jsmith@aihome.bmt.lamar.edu
```

## Warning:  <mark>If you cursor does NOT showed up. You just use Ctrl + C to continue</mark>  



---


### Log Out When Finished

```bash
exit
```

---


## Quick Start

Connect to VPN:

```text
Gateway: luvpn.lamar.edu
Port: 10443
```

SSH to AIHome:

```bash
ssh username@aihome.bmt.lamar.edu
```

Activate Python environment:

```bash
conda activate shared_env
```

Launch JupyterHub:

```text
http://aihome.bmt.lamar.edu:8000
```

Select **AI (Default)** and start working.
