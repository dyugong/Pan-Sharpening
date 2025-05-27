# Pan-Sharpening
The summary of the pan-sharpening methods


---
## Traditional_Pan-Sharpening
Resulted by ChatGPT


| **기법 이름**             | **분류**                                        | **설명 (간단 요약)**                                               |
| --------------------- | --------------------------------------------- | ------------------------------------------------------------ |
| **Brovey**            | Traditional                                   | 비율 기반의 색 보정 방법. PAN을 MS에 비례적으로 분배하여 공간 해상도 강화.               |
| **PCA**               | Traditional                                   | 주성분 분석을 이용하여 MS를 낮은 차원으로 투사하고 PAN으로 일부 성분을대체.               |
| **IHS**               | Traditional                                   | 색상 모델 변환(IHS) 기반. Intensity 성분을 PAN으로 대체하여 공간 정보 강화.         |
| **SFIM**              | Traditional                                   | 고주파 세부정보를 추출하고 MS에 삽입.                                       |
| **GS (Gram-Schmidt)** | Traditional                                   | MS 밴드를 직교화한 후 PAN을 삽입하여 재구성.                                 |
| **Wavelet**           | Traditional                                   | Wavelet 변환을 이용해 PAN의 고주파 정보를 MS에 융합.                         |
| **MTF-GLP**           | Traditional                                   | MTF 기반 저역 통과 필터와 Laplacian pyramid를 결합한 방식.                  |
| **MTF-GLP-HPM**       | Traditional                                   | 위 방식에 HPM(High-Pass Modulation)을 더하여 고주파 정보 조절.              |
| **GSA**               | Traditional                                   | GS 기반 기법에서 PAN-MS 스펙트럴 관계를 보존하도록 개선.                         |
| **CNMF**              | Traditional (정확히는 Matrix Factorization 기반 기법) | Coupled Non-negative Matrix Factorization. 스펙트럼 및 공간적 결합 모델. |
| **GFPCA**             | Traditional (통계 기반)                           | Guided Filter PCA. 공간적 구조 보존을 위해 guided filtering 결합.        |



---
## DL_Pan-Sharpening
Resulted by ChatGPT


| **기법 이름**             | **분류**                                        | **설명 (간단 요약)**                                               |
| --------------------- | --------------------------------------------- | ------------------------------------------------------------ |
| **PNN**               | Deep Learning                                 | Pansharpening Neural Network. 입력 이미지를 CNN으로 고해상도 MS로 예측.     |
| **PanNet**            | Deep Learning                                 | Residual learning 기반 CNN. PAN과 MS의 차이를 학습하여 복원.              |

---
## Full-Resolution vs Reduced-Resolution
Resulted by ChatGPT


|           |  **Full-Resolution(FR)**  |  **Reduced-Resolution(RR)**  |
|-----------|---------------------------|------------------------------|
| 입력 데이터 | 실제 PAN + MS          | 다운샘플된 PAN + MS          |
| GT 유무  | ❌ 없음                 | ✅ 있음                    |
| 평가 방식  | No-reference         | Reference-based         |
| 대표 지표  | QNR, Dλ, Ds          | RMSE, PSNR, SSIM, SAM   |
| 목적     | 실제 적용 시 품질 측정        | 정량 평가 (논문 비교 등)         |