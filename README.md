<div align="center">

| Methods | Params (M) | FLOPs (G) | Time (ms) | PSNR (dB) |
| :--- | :---: | :---: | :---: | :---: |
| LEDNet | 7.405 | 38.572 | 8.40 | 23.23 |
| RetinexFormer | 4.817 | 51.055 | 59.67 | 22.95 |
| LLFormer | 24.518 | 22.035 | 90.80 | 22.57 |
| DFFN | 2.577 | 15.965 | 10.68 | 16.43 |
| SCI++ | 0.023 | 2.960 | 1.89 | 12.89 |
| DarkIR | 3.309 | 7.117 | 71.19 | 23.24 |
| URWKV | 2.248 | 18.335 | 479.02 | 23.25 |
| **ULSIR (Ours)** | **14.141** | **29.114** | **64.30** | **23.80** |

<p align="left"><b>Table 1:</b> Quantitative complexity and performance comparison. All methods are evaluated on $256 \times 256$ patches under identical hardware settings. ULSIR achieves the highest PSNR (23.80 dB) while maintaining an optimal balance between parameter count, FLOPs, and inference latency compared to SOTAs.</p>

</div>

---

<div align="center">
  ![Figure 1](https://github.com/user-attachments/assets/e5cfec50-52d1-4118-be54-f76728306b7b)
  <p align="left"><b>Figure 1:</b> Radiometric realism validation of LLSD. (a) Intensity and (b) SNR distributions of LLSD strictly align with real Jilin-1 acquisitions. Crucially, the noise variance profiles (c) exhibit nearly identical linear slopes between synthetic and real data, confirming that our pipeline faithfully replicates the intrinsic physical behavior and hardware gain of the actual sensors.</p>
</div>

---
<div align="center">
  
| Methods | Architecture Type | Params (M) | FLOPs (G) | Time (ms) | PSNR (dB) |
| :--- | :--- | :---: | :---: | :---: | :---: |
| LEDNet | Pure CNN | 7.405 | 38.572 | 8.40 | 23.23 |
| LLFormer | Transformer | 4.817 | 51.055 | 59.67 | 22.57 |
| RetinexFormer | Transformer | 24.518 | 22.035 | 90.80 | 22.95 |
| DFFN | Pure CNN | 2.577 | 15.965 | 10.68 | 16.43 |
| SCI++ | Pure CNN | 0.023 | 2.960 | 1.89 | 12.89 |
| DarkIR | Pure CNN | 3.309 | 7.117 | 71.19 | 23.24 |
| URWKV | Transformer-Var | 2.248 | 18.335 | 479.02 | 23.25 |
| **ULSIR (Ours)** | **Freq-CNN (Dual)** | **14.141** | **29.114** | **64.30** | **23.80** |

<p align="left"><b>Table 2:</b> Quantitative efficiency and performance comparison. All metrics are measured on $256 \times 256$ patches using a single GPU. ULSIR establishes an optimal trade-off, outperforming heavy Transformer-based SOTAs (e.g., URWKV, LLFormer) in speed and surpassing lightweight CNNs (e.g., SCI++, DFFN) by over 7.37 dB in PSNR.</p>


</div>

---
<div align="center">
  
  <img width="4396" height="2588" alt="aligen8M" src="https://github.com/user-attachments/assets/637c6810-5162-43f5-9375-2f8f2dfb13b0" />
  <p align="left"><b>Figure 2:</b> Visualization of adaptive wavelet soft-thresholding ($t_k$). By visualizing intermediate LH/HL sub-bands, we demonstrate that $t_k$ acts as an effective separator: background noise is effectively zeroed out while structural boundaries remain entirely intact. This dynamic self-calibration prevents over-smoothing, ensuring that fine textures are preserved during the denoising process.</p>


</div>

---

<div align="center">

| $\lambda_{Lap}$ | 1 | 10 | 30 | **50 (Paper)** | 70 | 100 |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: |
| PSNR (dB) | 22.91 | 23.35 | 23.61 | **23.80** | 23.69 | 23.42 |

  <p align="left"><b>Table 3:</b> Sensitivity analysis of the Laplacian loss weight ($\lambda_{Lap}$). We evaluate $\lambda_{Lap} \in [1, 100]$ to balance gradient magnitudes and second-order structural supervision. The inverted-U curve validates that $\lambda_{Lap}=50$ optimally aligns high-frequency gradients without over-amplifying sensor noise, achieving the peak PSNR of 23.80 dB.</p>

</div>

---
<div align="center">

| Methods | Architecture Type | Params (M) | FLOPs (G) | Time (ms) | PSNR (dB) |
| :--- | :--- | :---: | :---: | :---: | :---: |
| LEDNet | Pure CNN | 7.405 | 38.572 | 8.40 | 23.23 |
| RetinexFormer | Transformer | 4.817 | 51.055 | 59.67 | 22.95 |
| LLFormer | Transformer | 24.518 | 22.035 | 90.80 | 22.57 |
| DFFN | Pure CNN | 2.577 | 15.965 | 10.68 | 16.43 |
| SCI++ | Pure CNN | 0.023 | 2.960 | 1.89 | 12.89 |
| DarkIR | Pure CNN | 3.309 | 7.117 | 71.19 | 23.24 |
| URWKV | Transformer-Var | 2.248 | 18.335 | 479.02 | 23.25 |
| Diff-Retinex++ (2025 TPAMI) | Diffusion | 62.755 | 308.660 | 76.01 | 22.56 |
| ReDDiT (2025 CVPR) | Diffusion | 17.434 | 232.460 | 70.80 | 14.73 |
| **ULSIR (Ours)** | **Freq-CNN (Dual)** | **14.141** | **29.114** | **64.30** | **23.80** |

  <p align="left"><b>Table 4:</b> Quantitative comparison between ULSIR and SOTA Transformer/Diffusion baselines. Results are measured on $256 \times 256$ patches. ULSIR outperformers heavy Transformers in both PSNR (+1.23 dB over LLFormer) and inference latency. Notably, compared to Diffusion models (e.g., Diff-Retinex++), ULSIR achieves superior fidelity with only $\sim1/10$ of the FLOPs (29.1G vs. 308.7G), effectively avoiding generative hallucinations and ensuring strict geographical fidelity.</p>


</div>

---
<div align="center">

  <img width="1421" height="404" alt="diffusion" src="https://github.com/user-attachments/assets/ecb6c758-65d7-40ce-be57-3627cee7ef0a" />
  <p align="left"><b>Figure 3:</b> Visual comparison of ultra-low-light satellite restoration. Compared to state-of-the-art baselines, ULSIR achieves the highest PSNR (23.80 dB) and restores sharp structural details (e.g., vehicles and road textures) without distortions. Notably, diffusion-based methods (Diff-Retinex++, ReDDiT) introduce severe texture inconsistencies under extreme noise, while lightweight CNNs (DFFN, SCI++) fail to recover recognizable structures. ULSIR mathematically ensures strict geographical fidelity through its single-feed-forward dual-frequency design.</p>


</div>

---

| Methods | Architecture Type | Params (M) | FLOPs (G) | Time (ms) | PSNR (dB) | Train GPU Memory (MB) | Test GPU Memory (MB) |
| :--- | :--- | :---: | :---: | :---: | :---: | :---: | :---: |
| LEDNet | Pure CNN | 7.405 | 38.572 | 8.40 | 23.23 | 3790.43 | 415.06 |
| RetinexFormer | Transformer | 4.817 | 51.055 | 59.67 | 22.95 | 17537.60 | 185.56 |
| LLFormer | Transformer | 24.518 | 22.035 | 90.80 | 22.57 | 35137.23 | 331.05 |
| DFFN | Pure CNN | 2.577 | 15.965 | 10.68 | 16.43 | 3130.90 | 230.79 |
| SCI++ | Pure CNN | 0.023 | 2.960 | 1.89 | 12.89 | 624.85 | 32.11 |
| DarkIR | Pure CNN | 3.309 | 7.117 | 71.19 | 23.24 | 3585.94 | 116.57 |
| URWKV | Transformer-Var | 2.248 | 18.335 | 479.02 | 23.25 | >40 G | 261.22 |
| **ULSIR (Ours)** | **Freq-CNN (Dual)** | **14.141** | **29.114** | **64.30** | **23.80** | **2823.41** | **103.41** |


  <p align="left"><b>Table 5:</b> Computational complexity and resource analysis. Evaluated on 256x256 patches, ULSIR successfully bypasses the memory explosions of Transformer-based methods (LLFormer/URWKV $>35$ GB), requiring only 2.8 GB for training. Furthermore, ULSIR achieves the highest PSNR (23.80 dB) with significantly lower inference memory (103.41 MB) and latency (64.30 ms), offering an optimal trade-off for satellite ground-station deployment.</p>



  





















