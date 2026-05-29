# Comparative-analysis-of-AES-Vs-Chacha20-for-real-time-sensor-data-encryption.-
![Python](https://img.shields.io/badge/Python-3.x-blue.svg)
![IoT Security](https://img.shields.io/badge/Security-IoT-success.svg)
![Google Colab](https://img.shields.io/badge/Environment-Google_Colab-orange.svg)

## 📌 Overview
This repository contains the research, implementation scripts, and performance evaluations for my BSc Honours Computer Science project conducted at the University of Limpopo. The project presents a comprehensive comparative analysis of the Advanced Encryption Standard (AES) and ChaCha20 algorithms, specifically evaluating their feasibility, performance, and security when encrypting real-time sensor data in resource-constrained Internet of Things (IoT) environments.

## 🎯 Research Objectives
* **Performance Evaluation:** Compare the encryption and decryption speeds of AES (GCM mode) and ChaCha20-Poly1305.
* **Payload Impact Analysis:** Analyze performance across small IoT data packets (1KB, 5KB, 10KB) and large aggregated payloads (1MB - 10MB).
* **Hardware Acceleration Assessment:** Evaluate throughput efficiency on systems with and without AES-NI hardware acceleration.
* **Security Analysis:** Investigate the security strengths, weaknesses, and side-channel attack vulnerabilities of each algorithm in an IoT context.

## 🛠️ Methodology & Tech Stack
The experiments were executed in a controlled, reproducible simulation environment, avoiding the overhead of physical hardware limits while mirroring real-time data constraints:
* **Environment:** Google Colab
* **Data Generation:** Synthetic IoT sensor data (temperature, humidity, pressure) generated using `NumPy`, `Pandas`, and `os.urandom`.
* **Cryptography Libraries:** * `PyCryptodome` (for AES-128 GCM implementation)
  * `PyNaCl` (for ChaCha20-Poly1305 implementation)
* **Data Visualization:** `Matplotlib` and `Seaborn`
* **Evaluation METRICS:**
  * <img width="1613" height="674" alt="image" src="https://github.com/user-attachments/assets/f95cf073-c4c0-46ef-9746-1a86a4aed28d" />
  * <img width="668" height="661" alt="image" src="https://github.com/user-attachments/assets/d404503a-4bc3-4dd6-a126-2b6f548416c1" />



## 📈 Visual Results

<!-- 🖼️ ADD YOUR IMAGES HERE: Replace 'path/to/your/image.png' with the actual file paths once you upload the images to your GitHub repository (e.g., 'images/figure3.png'). -->

### 1. Encryption and Decryption Time for Small Payloads

<img width="1629" height="640" alt="image" src="https://github.com/user-attachments/assets/03a38dac-3240-4ec0-8cc4-9684840b470e" />

### 2.Comparison of AES vs. ChaCha20 on 1KB, 2KB, 5KB, and 10KB payloads.
 <img width="1023" height="605" alt="image" src="https://github.com/user-attachments/assets/79b805fe-e3c0-4d88-9cc3-460a4500e1a8" />

### 3. Decryption of AES Vs Chacha20 on 1KB, 2KB, 5KB, and 10KB payloads.
<img width="1265" height="736" alt="image" src="https://github.com/user-attachments/assets/3d4ebd6f-3a02-4987-8e0e-9bfa0c5dfc3c" />


### 3. Encryption Throughput for Large Payloads
> *Throughput (MB/s) comparison including hardware-accelerated AES-NI on 1MB, 5MB, and 10MB payloads.*
> <img width="1165" height="613" alt="image" src="https://github.com/user-attachments/assets/6de76b91-a53a-4ff0-9c05-7f7ebe9c490d" />



## 📊 Key Findings
1. **Small Payloads (IoT Edge Devices):** ChaCha20 demonstrated superior performance in purely software-based environments, processing 10KB payloads in ~1.4ms compared to software-based AES's 4.0ms. Its stream cipher design makes it highly optimized for microcontrollers lacking specialized hardware.
2. **Large Payloads (IoT Gateways/Servers):** When leveraging **AES-NI hardware acceleration**, AES significantly outperformed ChaCha20, achieving throughputs exceeding 850 MB/s. Without AES-NI, however, ChaCha20 maintained a 3-4x performance lead.
3. **Security & Integrity:** Both algorithms preserved data integrity perfectly. AES is incredibly robust but requires hardware optimizations to mitigate cache-timing and side-channel attacks. ChaCha20 offers inherent resistance to timing attacks but demands strict, flawless nonce management.

## 💡 Conclusion
The research indicates that the choice of encryption is strictly context-dependent. **ChaCha20** is recommended for highly constrained IoT edge devices running pure software, while **AES (with AES-NI)** is the definitive choice for high-throughput IoT back-end systems, servers, and gateways.

## 👨‍💻 Author
**Wamashudu Shabane** 
