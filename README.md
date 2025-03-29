# Flowers dataset classification with pre-trained CNN models

### 연구의 목적
- 사전 학습 모델을 활용한 전이 학습 시 파인 튜닝 방식 및 정규화 여부에 따른 모델의 성능 차이
- 사전 학습 모델과 일반 CNN 모델의 성능 차이

---
### 데이터셋 설명
- 이미지 수 : 2746개
- 클래스 수 : 5개
    - Daisy(데이지)
    - Dandelion(민들레)
    - Rose(장미)
    - Sunflower(해바라기)
    - Tulip(튤립)
- 클래스별 이미지 수
![Image](https://github.com/user-attachments/assets/beec9731-5a8b-4225-aa69-bfaba711d0fd)
- 데이터 사이트 : https://www.kaggle.com/datasets/imsparsh/flowers-dataset/data

---
### 실험 방법
**사전 훈련 학습 모델은 ResNet18 사용**
- 모델1와 모델2는 각각 전체 파인 튜닝과 특징 추출기를 사용하는 부분 파인 튜닝에 해당한다. 이 두 모델을 통해 파인 튜닝 방식의 차이에 따른 모델 성능을 비교해보고자 한다.
- 모델2와 모델3는 모델의 구조는 같지만, 데이터 증강, 드롭 아웃, 기울기 감쇠 여부에 따라 나뉜다. 즉, 정규화 기법을 사용하지 않은 모델2와 정규화 기법을 사용한 모델3의 성능을 비교해보고자 한다. 
- 모델3와 모델4는 모두 데이터 증강, 드롭 아웃, 기울기 감쇠 기법을 사용하지만, 모델3은 사전 훈련된 모델인 데 반해 모델4는 사전 훈련되지 않은 CNN 모델이다. 이 두 모델을 통해 사전 훈련된 모델이 그렇지 않은 모델과의 성능 차이를 비교해보고자 한다.
---
### 모델 설명
<img width="452" alt="Image" src="https://github.com/user-attachments/assets/fceec677-3ce9-4d0c-8e4b-b531cc188a1d" />

---

### 결과 분석

###### 모델1 vs 모델2
- 모델1과 모델2의 결과에 유의미한 차이는 없고 모두 과적합되었다.

- 모델1
![Image](https://github.com/user-attachments/assets/b90c4364-1e7f-43fc-97ec-79149e70c9dc)

- 모델2
![Image](https://github.com/user-attachments/assets/b8be38ce-f392-49ab-821b-610b426e2000)

###### 모델2 vs 모델3
- 모델2은 과적합된 반면, 모델3은 정규화 기법으로 인하여 과적합이 완화되었다.

- 모델2
![Image](https://github.com/user-attachments/assets/b8be38ce-f392-49ab-821b-610b426e2000)

- 모델3
![Image](https://github.com/user-attachments/assets/2777eb04-e894-445e-9d87-fb1343a63625)

###### 모델3 vs 모델 4
- 모델4도 모델3과 동일하게 과접합이 일어나진 않았지만 성능이 크게 하락한 것을 볼 수 있다.

- 모델3
![Image](https://github.com/user-attachments/assets/2777eb04-e894-445e-9d87-fb1343a63625)

- 모델4
![Image](https://github.com/user-attachments/assets/ec04d7c1-bc47-4c25-8fc2-2ae0355b701e)

---
### 결론
1.	전체 파인 튜닝과 특징 추출기를 사용하는 부분 파인 튜닝은 모델의 정확도 및 과적합 여부에서 큰 차이를 보이지 않는다.
2.	데이터 증강, 드롭 아웃, 기울기 감쇠 같은 정규화 기법은 과적합을 방지하는 데에 유의미한 영향을 끼친다.
3.	사전 훈련 모델과 일반 CNN 모델 간에는 모델의 정확도 측면에서 유의미한 차이를 보인다.

