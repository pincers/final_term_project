# final_term_project
---
This repo contains machine learning algoritms:
---
Classification with Scikit Learn Library

model 소개:
---
SkLearn 에 있는 Linear SVC 라는 모델이다.
Linear Support Vector Classifier의 약자로 주어진 데이터셋을 분류하는 선(또는 평면이나 초평면)이 여럿 존재할텐데 그 중 가장 적절한 경계를 나누는 알고리즘이라고 한다. 
각 데이터와 거리가 멀수록 기준을 잘 잡은 것이기 때문에, 서포트 벡터 머신은 이 거리(margin)을 최대로 만드는 알고리즘이라고 한다. 

이 모델을 선택한 이유: 
---
SKlearn에 있는 모델들에 대하여 구글링을 하던 도중, olivetti_faces의 모델별 정확도를 비교하는 글을 찾게 되었다. https://towardsdatascience.com/face-recognition-using-deep-learning-b9be73689a23
거기에는 logistic regression, knn , svm 등 여러 가지 알고리즘에 대한 소개가 나와있었다. 
이 중에서 여러 가지를 선별해서 default값으로 테스트를 해봤다. (decision tree classifier 등등..)
그 중에서 디폴트 값의 accuracy가 가장 높은 알고리즘이 Linear SVC라는 모델이었고, 이 모델을 선택하게 되었다. 

하이퍼 매개변수 선택
---
변수 선택이 시행착오가 가장 많은 부분이었다. 사실 모델에 대해 깊게 공부하지 않아서 다룰 줄 아는 변수가 없었다. 
이 중에서 수치적으로 바꿀 수 있는 변수를 우선적으로 골랐다. 
C, max_iter 을 골랐고, class_weight도 골라봤다. 
우선 C는, 정규화 변수라고 한다. 정규화의 정도(strength)가 C에 반비례한다고 한다. 적당히 0.83을 선택해 보았다.
다음으로, max_iter는 실행할 최대 반복 횟수로, 숫자가 어느 정도 커지면 결국 큰 수의 법칙에 의해 오차가 줄어들 것이기 때문에 일부러 100이라는 작은 수를 선택하였다.
class_weight 는 class간 데이터에 따라 학습의 분량을 조절하는 변수라고 한다. "balanced" 모드는 입력 데이터의 클래스 빈도에 반비례하여 가중치를 자동조정한다.

코드 설명
---
코드에서는 크게 설명할 것이 없다. 수업시간을 착실히 따라갔으면 문제 없이 채워 넣을 수 있다. 
다만, additional rackage에 sklearn.svm을 하나 추가하였다. 
추가하지 않아도 작동이 되긴 하였지만, linear SVC의 경우 sklearn.svm.LinearSVC의 형식이기 때문에 혹시나 해서 import하여 추가했다.
