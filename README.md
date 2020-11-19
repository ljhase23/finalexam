# Keras  
----  
<img src = logo.png  height = 200 width = 600>

----  
> * 파이썬으로 작성된 오픈 소스 신경망 라이브러리  
> * 딥러닝 라이브러리  
>> Tensorflow와 Theano를 backend 로 사용  

* 장점  
> * 쉽고 빠른 구현(레이어,활성화 함수, 비용 함수, 최적화 등 모듈화)  
> * CNN, RNN 지원  
> * CPU / GPU 지원  
> * 확장성(새 모듈을 매우 간단하게 추가 가능)  
> * 파이썬 코드로 모델 생성  

* 특징  
> * 사용자 친근성(User Friendliness)
>>> Keras는 기계가 아닌 인간을 위해 설계된 API  
>>> 일관성 있고 간단한 API를 제공하고, 일반적으로 필요한 사용자 작업의 수를 최소화하며, 사용자 오류 시 명확하고 실용적인 피드백을 제공  

> * 모듈성(Modularity)  
>>> 모델은 가능한 최소한으로의 제한하여 독립적으로 생성가능  
>>> 신경층, 비용함수, 최적화기, 초기화 스킴, 활성 함수, 정규화 스킴은 모두 새로운 모델을 생성하기 위해 결합할 수있는 독립 실행형 모듈 

> * 쉬운 확장성(Easy Extensibility)  
>>> 새로운 모듈은 (새로운 클래스와 함수로서) 추가하기 쉬움.  
>>> 새로운 모듈을 쉽게 만들 수 있기 때문에 Keras가 고급 연구에 적합.  

> * Python 작업(Work with Python)  
>>> 모델은 작고, 디버그하기 쉽고, 확장성이 용이한 Python을 기반  

-----------

## 딥러닝 모델 생성 과정  
> * 데이터셋 생성하기
>>> 원본 데이터를 불러오거나 시뮬레이션을 통해 데이터를 생성하고 데이터로부터 훈련셋, 검증셋, 시험셋을 생성.  
>>> 이때 딥러닝 모델의 학습 및 평가를 할 수 있도록 포맷 변환.  

> * 모델 구성하기  
>>> 시퀀스 모델을 생성한 뒤 필요한 레이어를 추가하여 구성.  
>>> 좀 더 복잡한 모델이 필요할 때는 케라스 함수 API를 사용.  

> * 모델 학습과정 설정하기  
>>> 학습하기 전에 학습에 대한 설정을 수행하고, 손실 함수 및 최적화 방법을 정의.  
>>> 케라스에서는 compile() 함수를 사용.  

> * 모델 학습시키기  
>>> 련셋을 이용하여 구성한 모델로 학습시키며 fit() 함수를 사용  

> * 학습과정 살펴보기  
>>> 모델 학습 시 훈련셋, 검증셋의 손실 및 정확도를 측정.  
>>> 반복횟수에 따른 손실 및 정확도 추이를 보면서 학습 상황을 판단.  

> * 모델 평가하기  
>>> 준비된 시험셋으로 학습한 모델을 평가하고 evaluate() 함수를 사용.  

> * 모델 사용하기  
>>> 임의의 입력으로 모델의 출력을 얻고 predict() 함수를 사용.  

-------
## keras 설치방법  
### How to Install??  
<img src = install.png height = 200 width = 500>  


> * Python 3.6 설치  
> * Anaconda 설치  
>>> 패키지 관리와 디플로이를 단순케 할 목적으로 과학 계산을 위해 파이썬과 R 프로그래밍 언어의 자유-오픈 스 배포판.  
>>> [Anaconda Download][anaconda]  

> * Anaconda를 이용한 keras 설치  
>>> * Anaconda prompt 실행  
>>> * conda create-n keras python=3.8  
>>> * conda activate keras  
>>> * pip install tensorflow  
>>> * conda install scipy  
>>> * pip install keras  
>>> * pip intstall h5py  


------  

## keras 기초 사용법 
> * jupyter notebook 사용.  
>>> 도큐먼트를 생성하고 공유할 수 있게 해주는 오픈소스 웹 어플리케이션.  
>>> PYTHON 을 사용.  
> * Keras에서 레이어들을 구성하는 방법으로 사용되는 핵심적인 자료구조형은 모델.  
> * 그 중에서도 가장 간단한 형태의 모델은 레이어들을 선형으로 쌓는 Sequential Model.  
>> * example  
>>> from keras.models import Sequential  
>>> model = Sequential()  

> * 레이어는 .add()를 통해 추가할 수 있음.  
>> * example  
>>> from keras.layers import Dense  
>>> model.add(Dense(units=64, activation='relu', input_dim=100))  
>>> model.add(Dense(units=10, activation='softmax'))  

> * 모델이 어느정도 모양을 갖추면, .compile()을 통해 학습 방법을 설정할 수 있음.  
>> * example  
>>> model.compile(loss='categorical_crossentropy', optimizer='sgd',metrics=['accuracy'])  

> * 모델 설정이 완료되면, .fit()을 통해 모델에 직접 학습데이터를 넣어 학습 시킬 수 있음.  
>> * example  
>>> model.fit(X_train_std, Y_train, epochs=10, batch_size=105)  

> * 배치를 수동으로 모델에 학습하도록 줄 수 있음.  
>> * example 
>>> model.train_on_batch(X_batch_std, y_batch)  

> * 모델이 학습이 완료되면, 단 한줄로 평가가 가능.  
>> * example 
>>> loss_and_metrics = model.evaluate(X_test_std, Y_test, batch_size=128)  

> * 에측도 가능.
>> * example 
>>> classes = model.predict(X_test_std, batch_size=105)  


------


[anaconda]:https://www.anaconda.com/sidtribution/  


