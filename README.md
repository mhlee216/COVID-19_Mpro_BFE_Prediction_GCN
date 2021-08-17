# Prediction of SARS-CoV-2 Main Protease Binding Free Energy Using Graph Convolutional Networks

#### Motivation
Drug–Target Binding Affinity (DTA)는 신약 개발 과정에서 표적 단백질에 선택적으로 강하게 결합하는 약물을 설계하기 위해 측정된다. DTA가 충분히 크지 않으면 해당 약물은 유용하지 않을 수 있다. DTA는 일반적으로 해리 상수 (Dissociation Constant, Kd), 억제 상수 (Inhibition Constant, Ki) 또는 50% 최대 억제 농도 (The Half Maximal Inhibitory Concentration, IC50)로 표현된다. 이런 일반적이고 생물학적인 단위와는 다르게, Docking Simulation은 결합 전위를 kcal/mol 단위로 반환한다. 하지만 분자 생성모델에서 분자의 목적이 특정 표적 단백질에 결합하는 약물로서 역할 하는 경우라면, 생성된 분자의 DTA를 검증하기 위해 AutoDock Vina를 이용해 Binding Free Energy (BFE, kcal/mol)를 측정하는 것은 종종 이용되는 방법이다.

따라서, SARS-CoV-2의 Target 중 하나인 Mpro와 여러 Drug 사이의 BFE를 Regression하고자 한다.



#### Dataset
https://github.com/omarwagih/covid19-docking

Dataset는 AutoDock Vina를 이용해 계산된 BFE(0 미만)와 SMILES에 대해 중복을 제거하여 정리하였다.



#### GCN Model Architecture

<img src="https://github.com/mhlee216/COVID-19_Mpro_BFE_Prediction_GCN/blob/main/Model.jpg">

- R2 : 0.87 (±0.02)

- RMSE : 0.44 (±0.03) (kcal/mol)

- MAE : 0.32 (±0.01) (kcal/mol) 


#### Abstact
약물과 표적 간의 상호 작용에 대한 계산적 예측은 SARS-CoV-2 (COVID-19)의 신약 개발 과정에 있어 중요한 단계이며, 컴퓨터를 이용하면 이 과정을 가속화하고 자원을 줄일 수 있다. 이를 위한 Drug–Target Binding Affinity (DTA) 예측에 딥 러닝을 도입하고 정확도를 향상시키는 것이 최근 연구의 초점이 되고 있다. 본 논문에서는 분자의 구조 정보를 활용하여 분자 Graph를 생성하고, SARS-CoV-2의 표적 단백질인 Mpro (PDB entry: 6LU7)와 약물 사이의 Binding Free Energy (BFE, kcal/mol) 예측을 위한 Graph Convolutional Networks (GCN)를 제안한다. 분자 Graph는 원소의 화학적 특성을 구조적 특성에 따라 Convolution하여 BFE를 예측할 수 있으며, 모델 개발을 위한 추가적인 복잡한 계산/실험 과정은 필요하지 않다. BFE Dataset는 AutoDock Vina를 이용해 생성된 4,717개 분자의 SMILES를 이용하였다. 결과적으로, 본 논문에서 제안하는 GCN 모델은 BFE 예측을 위한 효과적인 접근 방식이며, 약물 개발 과정에서 매우 유용할 수 있음을 보여준다.

- Paper : https://drive.google.com/file/d/194W1ph8O7wqBKZ6NNY0ggN0bkoHzvwLR/view?usp=sharing
