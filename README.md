# ⚡ Xray High-Performance Scanner

A multi-threaded, high-speed IP scanner and latency tester for Xray/V2Ray configurations. Written in C# (.NET), designed for finding clean IPs with low latency.

> **Developed by [mhmmd_ah1]**


![Platform](https://img.shields.io/badge/platform-Windows-lightgrey)
![Language](https://img.shields.io/badge/language-C%23-purple)

## 🚀 Features

* **Smart Sorting:** Automatically sorts valid IPs by **Lowest Ping** first.
* **VLESS Generator:** Generates full `vless://` links .
* **Port Independence:** Scans IPs based on your config port.
* **Range Generator:** Built-in CIDR to IP converter (e.g., `104.16.0.0/24`).
* **Real-time Saving:** Results are saved instantly to prevent data loss.
* **Core Integrity:** Uses the official `xray.exe` core for accurate real-world connectivity tests.

## 📋 Prerequisites

1.  **Windows OS** (Windows 10/11 recommended).
2.  **.NET 6.0 Runtime** (or higher).
3.  **Xray Core:** You must place `xray.exe` in the same folder as the scanner.

## 🛠️ Configuration

### 1. `appsettings.json` (Scanner Settings)
Control how the scanner behaves (threads, timeouts, output).

| Key | Description | Recommended |
| :--- | :--- | :--- |
| `Concurrency` | Number of simultaneous threads. Higher = Faster (depends on CPU). | `16` or `32` |
| `OverallTimeoutMs` | Maximum time (ms) to wait for a connection before skipping. | `5000` |
| `OutputFileName` | File name for saving results. | `valid_proxies.txt` |
| `SaveAsVlessLink` | `true`: Saves full `vless://` links.<br>`false`: Saves just `IP:Port`. | `true` |
| `LinkRemark` | The name tag added to generated links (e.g., `Scan-IP`). | `Scanner` |

### 2. `template.json` (Server Config)
Put your server details here. The scanner injects found IPs into this template.

| Key | Description |
| :--- | :--- |
| `uuid` | Your VLESS User ID. |
| `port` | **Important:** The port you want to scan/connect to (e.g., 443). |
| `sni` | Your SNI/Domain (e.g., `google.com`). |
| `wsHost` | Host header (usually same as SNI). |
| `wsPath` | The WebSocket path (e.g., `/` or `/ws`). |

## 📦 How to Use

1.  Download the latest release or build the source.
2.  Ensure `xray.exe`, `appsettings.json`, and `template.json` are in the folder.
3.  Run `Scanner.exe`.
4.  **Option 2:** Generate IPs from a CIDR range (e.g., `192.168.0.0/24`).
5.  **Option 1:** Start the scan.
6.  Wait for the scan to finish. Results will be sorted by **Ping** in `valid_proxies.txt`.

## ⚠️ Disclaimer

This tool is created for educational purposes and network analysis only. The developer  is not responsible for any misuse.




#contact : 
@probabblynot  @mohmmd_ah1