# Prediction of SARS-CoV-2 Main Protease Binding Free Energy Using Graph Convolutional Network

SARS-CoV-2 Mpro와 Drug 사이의 Binding Free Energy (BFE, kcal/mol) Regression

#### Dataset
https://github.com/omarwagih/covid19-docking
Dataset는 AutoDock Vina를 이용해 계산된 BFE(0 미만)와 SMILES에 대해 중복을 제거하여 정리하였다.

#### GCN Model Architecture
<img src="https://github.com/mhlee216/COVID-19_Mpro_BFE_Prediction_GCN/blob/main/Model_architecture.jpg">

