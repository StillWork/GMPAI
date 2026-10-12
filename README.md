# 실습으로 배우는 GMP AI (GMPAI)

서울대학교 / 제약바이오 **GMP·의약품 제조 AI** 2일(12시간) 과정 실습 예제입니다.
모든 예제는 **Google Colab** 에서 바로 실행되며, **AI 배경지식 없이** 따라갈 수 있도록 구성했습니다.

> 강사: 김화종 (K-MELLODDY 사업단장) · hjkim3@gmail.com

## 이 과정의 특징 — 실제 제조 데이터
가상의 난수 데이터가 아니라 **실제 제약공장 생산 기록**과 **국제 표준 벤치마크**를 사용합니다.
그래서 **모델이 실패하는 경우도 그대로** 다룹니다. 현장에서 실제로 겪는 일이고, **왜 실패했는지 진단하는 능력**이 성능 숫자보다 중요하기 때문입니다.

## 실행 방법
각 노트북 상단의 [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com) 배지를 클릭하면 Colab 에서 바로 열립니다.
위에서부터 `Shift + Enter` 로 실행하세요.

## 예제 구성

| # | 노트북 | 강의 목차 연계 | 핵심 내용 | 데이터 | 환경 |
|:--:|---|---|---|---|---|
| 01 | [Colab·LLM 코딩과 제조 데이터](01_Colab_LLM_GMP_Data.ipynb) | ①②③ | QbD 용어(QTPP·CQA·CPP·CMA), EDA, OOS/OOT, 데이터 무결성 점검 | 정제 1,005 배치 | CPU 15분 |
| 02 | [머신러닝 기초 — 회귀·분류와 성능 평가](02_ML_Basics_Regression_Classification.ipynb) | ④ | 성능지표, **시간 순 검증**, **데이터 누수 탐지**, 모델 비교, 과대적합 | 정제 1,005 배치 | CPU 15분 |
| 03 | [SPC 관리도·공정능력·다변량 SPC](03_SPC_Control_Charts_Capability.ipynb) | 기본기 | 관리한계 vs 규격, I-MR, **Nelson 규칙**, Cp·Cpk, CUSUM·EWMA, **Hotelling T²·Q 통계** | 정제 1,005 배치 | CPU 10분 |
| 04 | [공정 시계열 데이터와 회귀 예측](04_Process_TimeSeries_Features.ipynb) | ⑤ | 기동/정상/정지 구간 분할, 시계열 특성공학, 진행률 리샘플링 | **타정기 10초 간격 센서 로그** | CPU 10분 |
| 05 | [품질 분류 예측과 OOS 조기경보](05_Quality_Classification_OOS_Alert.ipynb) | ⑥ | 불균형 분류, **비용+경보율 기반 임계값**, 확률 보정, **SHAP**, 경보 운영 설계 | 정제 1,005 배치 | CPU 10분 |
| 06 | [공정 이상 탐지와 Deviation 분류](06_Anomaly_Detection_Deviation.ipynb) | ⑧ | PCA **SPE·T²** vs Isolation Forest vs 오토인코더, 탐지 지연, 기여도 분석, 일탈 텍스트 분류 | **Tennessee Eastman** | CPU 10분 |
| 07 | [딥러닝 이해와 비전 검사](07_Deep_Learning_Vision_Inspection.ipynb) | ⑦ | CNN 원리, **정상품만 학습하는 외관 검사**, 패치 기반 **결함 위치 히트맵**, 검사 임계값 | **MVTec AD 캡슐** | GPU 권장 10분 |
| 08 | [바이오 프로세스 탐색과 생산량 예측](08_Bioprocess_Data_Yield_Prediction.ipynb) | ⑨ | 배치 궤적, 제어 전략 비교, 배치 지문·골든 배치, 수율 예측, 고장 배치 분류 | **IndPenSim 페니실린 100 배치** | CPU 10분 |
| 09 | [소프트센서와 PAT·RTRT](09_Soft_Sensor_PAT_RTRT.ipynb) | ⑩ | 소프트센서 구현, **배치 단위 검증의 중요성**, 예측 구간, **RTRT 적용 시점 결정** | IndPenSim | CPU 10분 |
| 10 | [설비 예지보수와 장애 예측](10_Predictive_Maintenance_RUL.ipynb) | ⑪ | 보전 전략, **RUL 레이블 설계**, 추세 특성, 비대칭 오차, **비용 기반 정비 시점** | **NASA C-MAPSS** | CPU 10분 |
| 11 | [AI 모델 검증과 규제 대응](11_AI_Validation_Regulatory.ipynb) | ⑫ | GAMP 5·CSA, **모델 카드**, **해시 체인 감사추적**, ALCOA+ 점검, **드리프트(PSI)**, GAIP 체크리스트 | 정제 1,005 배치 | CPU 10분 |

## 데이터 출처 (모두 공개 데이터)
| 데이터 | 출처 | 내용 |
|---|---|---|
| **정제 생산 배치** | Žagar & Mihelič, *Scientific Data* 9:55 (2022), Lek Pharmaceuticals — CC BY 4.0 | 실제 제약공장 1,005 배치, 원료시험+타정공정+품질시험 |
| **타정 공정 시계열** | 위 데이터셋의 10초 간격 로그 (1분 평균으로 요약 제공) | 제품코드 17, 207 배치 |
| **Tennessee Eastman** | Downs & Vogel (1993), Braatz 그룹 공개 데이터 | 화학공정 52센서, 21가지 고장 시나리오 |
| **MVTec AD (capsule)** | Bergmann et al., CVPR 2019 — **CC BY-NC-SA 4.0 (비영리)** | 캡슐 정상 219장 + 결함 5종 |
| **IndPenSim** | Goldrick et al., 산업용 페니실린 발효 시뮬레이터 | 100 배치 × 113,935 측정점 × 37 변수 |
| **NASA C-MAPSS** | NASA Prognostics Data Repository | 터보팬 100대 전 생애 센서 기록 |

`data/` 폴더에 전처리된 스냅샷이 있으며, 노트북이 자동으로 내려받습니다.

## 학습 흐름
```
01 데이터 이해 ─> 02 성능 평가·검증 설계 ─> 03 SPC(기본기)
                          │
     ┌────────────────────┼──────────────────────┐
     ↓                    ↓                      ↓
04 시계열 특성      05 품질 분류·경보       06 이상탐지·일탈분류
     │                    │                      │
     └──> 07 비전검사   08 바이오프로세스 ─> 09 소프트센서·RTRT
                              └──> 10 예지보수
                                        ↓
                          11 검증·감사추적·드리프트 (운영)
```

## 이 과정이 강조하는 5가지 원칙
1. **검증 설계가 성능보다 중요** — 시간 순·배치 단위 분할. 무작위 CV 는 성능을 부풀립니다 (예제 02·09)
2. **데이터 누수를 항상 의심** — 너무 좋은 성능은 대개 누수입니다 (예제 02)
3. **실패도 결과** — "예측 불가"는 PAT 도입·추가 계측의 근거가 됩니다 (예제 02·04)
4. **AI 는 지원, 판정은 사람** — GMP 에서 품질 판정 책임은 사람에게 있습니다 (예제 05·07·11)
5. **모델은 낡는다** — 드리프트 감시와 재학습 절차를 처음부터 설계합니다 (예제 11)

## 환경
- Google Colab (권장) — 설치 불필요
- GPU(T4) 권장: 07
- 로컬 실행 시: Python 3.10+ / `pip install scikit-learn pandas matplotlib scipy shap torch torchvision`

## 라이선스
교육용으로 자유롭게 사용하실 수 있습니다. 각 데이터셋은 원 출처의 라이선스를 따릅니다
(특히 MVTec AD 는 **비영리** 라이선스입니다).
