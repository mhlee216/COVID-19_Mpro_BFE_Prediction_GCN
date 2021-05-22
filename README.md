# Prediction of SARS-CoV-2 Main Protease Binding Free Energy Using Graph Convolutional Network

#### Motivation
Drug–Target Binding Affinity (DTA)는 신약 개발 과정에서 표적 단백질에 선택적으로 강하게 결합하는 약물을 설계하기 위해 측정된다. DTA가 충분히 크지 않으면 해당 약물은 유용하지 않을 수 있다. DTA는 일반적으로 해리 상수 (Dissociation Constant, Kd), 억제 상수 (Inhibition Constant, Ki) 또는 50% 최대 억제 농도 (The Half Maximal Inhibitory Concentration, IC50)로 표현된다. 이런 일반적이고 생물학적인 단위와는 다르게, Docking Simulation은 결합 전위를 kcal/mol 단위로 반환한다. 하지만 분자 생성모델에서 분자의 목적이 특정 표적 단백질에 결합하는 약물로서 역할 하는 경우라면, 생성된 분자의 DTA를 검증하기 위해 AutoDock Vina를 이용해 Binding Free Energy (BFE, kcal/mol)를 측정하는 것은 종종 이용되는 방법이다.
따라서, SARS-CoV-2의 Target 중 하나인 Mpro와 여러 Drug 사이의 BFE를 Regression하고자 한다.

#### Dataset
- https://github.com/omarwagih/covid19-docking
Dataset는 AutoDock Vina를 이용해 계산된 BFE(0 미만)와 SMILES에 대해 중복을 제거하여 정리하였다.

#### GCN Model Architecture
<img src="https://github.com/mhlee216/COVID-19_Mpro_BFE_Prediction_GCN/blob/main/Model_architecture.jpg">
- R2 : 0.87 (±0.02)
- RMSE : 0.44 (±0.03) (kcal/mol)
- MAE : 0.32 (±0.01) (kcal/mol) 
