# User Guide for GPU Servers in Computer Science Department

**Date:** September 18, 2026

---

## [AIHOME GPU Server User Gudie](../AIhome/README.md)
## [GPU Server Guide](./Document/README.md)

# GPU Infrastructure

The Computer Science Department currently hosts the following GPU and big memory servers.

## 1. Dell PowerEdge R750XA GPU Server (1 Unit)

- CPU: 2 × Intel Xeon Silver 4309Y (2.8 GHz, 8 cores / 16 threads each)
- Memory: 503 GB RAM
- GPU: 2 × NVIDIA Ampere A100 (80 GB each)

## 2. Dell PowerEdge R740 GPU Servers (2 Units)

- CPU: 2 × Intel Xeon Gold 6130 (16 cores each)
- Memory: 187 GB RAM
- GPU: NVIDIA Tesla V100 (16 GB)

## 3. Dell PowerEdge R640 Compute Server (1 Unit)

- CPU: 2 × Intel Xeon Gold 6130 (16 cores each)
- Memory: 723 GB RAM
- GPU: None

### Shared Storage

All servers share approximately **8 TB** of storage.

---

# Accessing the GPU System

The GPU servers are maintained by the Computer Science Department and are available to faculty and students. The systems are preconfigured for Python, Machine Learning, and AI development.

## Login Credentials

Use your Lamar University credentials.

---

# Step 1: Establish a VPN Connection

Before connecting remotely, you must connect to the Lamar University VPN.

**VPN Information**

- URL: https://www.lamar.edu/it-services-and-support/remote-access-service.html
- Two-Factor Authentication Required
- Custom Port: `10443`
- Remote Gateway: `luvpn.lamar.edu`

---

# Step 2: Connect via SSH

You may use any SSH client, including:

- MobaXterm
  - https://mobaxterm.mobatek.net/
- PuTTY
  - https://putty.org/

After connecting to the VPN, SSH to one of the following systems.

## Server Information

| Hostname | IP Address |
|-----------|------------|
| aihome.bmt.lamar.edu | 140.158.131.1 |
| russell.bmt.lamar.edu | 140.158.131.5 |
| gpu2.bmt.lamar.edu | 140.158.131.2 |
| bigmem.bmt.lamar.edu | 140.158.131.133 |

### Example SSH Login

```bash
ssh username@aihome.bmt.lamar.edu
```

or

```bash
ssh username@140.158.131.1
```

---

# Initial Environment Setup

## Configure Conda for Bash (First Login Only)

Run the following command once after your first login:

```bash
conda init bash
```

This initializes Conda in your Bash shell.

Log out and log back in if required.

---

## Activate the Shared Environment

Run this command every time you log in:

```bash
conda activate AI
```

A successful activation will display:

```text
(AI)
```

in front of your shell prompt.

---

## Check Python Version

```bash
python -V
```

Current version:

```text
Python 3.10.14
```

---

## View Installed Packages

```bash
conda list
```

Common packages already installed include:

- TensorFlow-GPU
- NumPy
- SciPy
- Pandas
- Matplotlib
- Plotly
- Keras
- Scikit-Learn
- PyTorch
- Darts
- OpenCV

### Installing Additional Packages

Install packages in your home directory:

```bash
pip install --user package-name
```

You may also create your own Conda environments.

---

# Using Jupyter Notebook

## JupyterHub

JupyterHub is installed on:

- aihome
- russell
- gpu2
- bigmem

This provides browser-based access to Jupyter Notebooks.

## Access URLs

### AIHome

- http://aihome.bmt.lamar.edu:8000
- http://140.158.131.1:8000

### Russell

- http://russell.bmt.lamar.edu:8000
- http://140.158.131.5:8000

### BigMem

- http://bigmem.bmt.lamar.edu:8000
- http://140.158.131.133:8000

---

# Shared Home Directory

All four systems share the same user home directory.

This means that:

- Files created on one system are available on the others.
- User data is centrally stored.
- You can switch servers without copying files.

---

# Logging Into JupyterHub

1. Open a browser.
2. Navigate to a JupyterHub URL.
3. Log in using:

```text
Username: Your LU account name (without @lamar.edu)
Password: Your LU password
```

---

# Selecting the AI Environment

After logging into JupyterHub:

1. Select **AI (default)** when creating a notebook.

Or

2. Select the kernel from:

```text
Kernel → Change Kernel → AI (default)
```

The AI environment includes commonly used Machine Learning and Data Science packages.

---

# GPU and Memory Resources

## AIHome Server

AIHome provides:

- 2 × NVIDIA A100 GPUs
- 80 GB GPU memory per GPU

### Approximate Performance

| Specification | Value |
|--------------|--------|
| FP32 Performance | Up to 156 TFLOPS |
| FP64 Performance | Up to 19.5 TFLOPS |
| GPU Memory | 80 GB |

### Verify Available GPUs

Python example:

```python
import tensorflow as tf

print(tf.config.list_physical_devices('GPU'))
```

AIHome is recommended for:

- Deep Learning
- Large Language Models
- AI Training
- GPU-Accelerated Computing

---

## Russell Server

Russell provides:

- 3 × NVIDIA Tesla V100 GPUs
- 16 GB GPU memory per GPU

### Approximate Performance

| Specification | Value |
|--------------|--------|
| FP32 Performance | 15.7 TFLOPS |
| FP64 Performance | 7.8 TFLOPS |
| GPU Memory | 16 GB |

Users may compare performance across GPUs depending on workload requirements.

---

## BigMem Server

BigMem does not contain a GPU.

### Resources

- 723 GB RAM

BigMem is recommended for:

- Memory-intensive applications
- Large datasets
- Data preprocessing
- Large-scale simulations

---

# Recommended Usage

| Workload | Recommended Server |
|-----------|-------------------|
| Deep Learning Training | AIHome |
| GPU Computing | AIHome |
| General AI Experiments | Russell |
| Medium-Scale Model Training | Russell |
| Large Memory Applications | BigMem |
| Data Processing | BigMem |

---

# Support

For account access, software issues, or server-related questions, please contact the Computer Science Department support staff.
