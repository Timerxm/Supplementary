
#### 1. Quantitative Comparison

Our proposed **ULSIR** method achieves competitive results with higher PSNR while maintaining lower Params and FLOPs than many leading methods.

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

</div>

---

#### 2. Statistical Distribution

We visualize the effectiveness of our alignment technique. The plot shows the statistical alignment of intensity distributions.

<div align="center">
  <img width="2370" height="1770" alt="data" src="https://github.com/user-attachments/assets/d723ecb8-81e2-4346-8dec-7ba8bf2e5b1a" />
  <p align="center"><b>Figure 1:</b> Statistical alignment of intensity distributions for real and synthetic data.</p>
</div>

