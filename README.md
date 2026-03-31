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

<p align="center"><b>Table 1:</b> Quantitative complexity and performance comparison. All methods are evaluated on $256 \times 256$ patches under identical hardware settings. ULSIR achieves the highest PSNR (23.80 dB) while maintaining an optimal balance between parameter count, FLOPs, and inference latency compared to SOTAs.</p>

</div>

---

<div align="center">
  <img width="2370" height="1770" alt="data" src="https://github.com/user-attachments/assets/d723ecb8-81e2-4346-8dec-7ba8bf2e5b1a" />
  <p align="center"><b>Figure 1:</b> Comparison of probability densities between a real ultra-low-light satellite acquisition (Jilin-1) and a synthetic LLSD image. As explicitly detailed in the text, the synthetic distribution strictly matches actual hardware outputs, ensuring the radiometric realism of our dataset.</p>

  
</div>

---
<div align="center">
  
| Methods | Architecture Type | Params (M) | FLOPs (G) | Time (ms) | PSNR (dB) |
| :--- | :--- | :---: | :---: | :---: | :---: |
| LEDNet | Pure CNN | 7.405 | 38.572 | 8.40 | 23.23 |
| LLFormer | Transformer | 24.518 | 22.035 | 90.80 | 22.95 |
| RetinexFormer | Transformer | 4.817 | 51.055 | 59.67 | 22.57 |
| DFFN | Pure CNN | 2.577 | 15.965 | 10.68 | 16.43 |
| SCI++ | Pure CNN | 0.023 | 2.960 | 1.89 | 12.89 |
| DarkIR | Pure CNN | 3.309 | 7.117 | 71.19 | 23.24 |
| URWKV | Transformer-Var | 2.248 | 18.335 | 479.02 | 23.25 |
| **ULSIR (Ours)** | **Freq-CNN (Dual)** | **14.141** | **29.114** | **64.30** | **23.80** |

<p align="center"><b>Table 2:</b> Table 2. Quantitative efficiency and performance comparison. All metrics are measured on $256 \times 256$ patches using a single GPU. ULSIR establishes an optimal trade-off, outperforming heavy Transformer-based SOTAs (e.g., URWKV, LLFormer) in speed and surpassing lightweight CNNs (e.g., SCI++, DFFN) by over 7.37 dB in PSNR.</p>


</div>

---
<div align="center">
  
  <img width="4396" height="2588" alt="aligen8M" src="https://github.com/user-attachments/assets/637c6810-5162-43f5-9375-2f8f2dfb13b0" />
  <p align="center"><b>Figure 2:</b> Visualization of adaptive wavelet soft-thresholding ($t_k$). By visualizing intermediate LH/HL sub-bands, we demonstrate that $t_k$ acts as an effective separator: background noise is effectively zeroed out while structural boundaries remain entirely intact. This dynamic self-calibration prevents over-smoothing, ensuring that fine textures are preserved during the denoising process.</p>


</div>

---





















