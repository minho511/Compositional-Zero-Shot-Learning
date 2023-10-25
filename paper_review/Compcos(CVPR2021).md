# Open World Compositional Zero-Shot Learning
- Review Date: 2023.10.25

## Intro
Open World setting을 처음으로 제안하는 논문이다.  
본문의 Abstract에서 

> In this work, instead of assuming **prior** knowledge about unseen compositions ~

이렇게 이전의 설정들을 묘사하였는데 기존의 czsl에서는 zero-shot 세팅임에도 불구하고 우리가 **이미 알고있는(하지만 학습때는 모델이 본적없는) compoisition embedding들로만 구성된 벡터 공간**에서 가장 유사한 벡터를 찾아 매칭하는 것이었다면, Open World setting에서는 학습에 사용된 object, state의 모든 (실존하지 않을지라도)가능한 조합들이 벡터 공간을 이루게 되고 이로써 우리는 모델이 모든 가능한 경우의 composition들 중에서도 사진과 매칭되는 composition의 벡터와 가장 유사한 벡터를 출력하도록 학습시켜야한다.

따라서 Open World의 설정이 더욱 어려운 task라고 할 수 있다.

## Method
본 논문의 핵심은 다음과 같다.
1. OW를 위한 visual feature과 composition embedding 사이의 cosine similarity
2. 실존가능성을 고려한 feasibility score를 활용하여 output space 와 similarity loss를 규제.

모델은 Image와 compositional representation 을 모두 공유된 embedding space에 임베딩하고 cosine similarity로 점수를 계산하는 방식이다.

-  **feasibility score**
    사전학습된 단어임베딩 (primitives) 간의 유사도를 사용하여 feasibility score를 구하고, 이를 cross-entropy loss의 margin값으로 사용함으로써, 실존 가능성이 적은 (unfeasible) 조합을 제거(가중을 낮춤)하며 학습을 진행한다.
    > 매우 단순한 이 방법이 이전의 방식들을 모두 능가하였다.(CW, OW)  



## Experiments
1. Dataset 
    - MIT-states (CW/OW)
    - UT Zappos (CW/OW)


## info
- 확실히, CW(이전 테스크)의 모델들이 OW 세팅에서 성능이 저하된다.
- 본 논문에서는 실존 가능성이 적은 state-object 조합을 `distractor`라 부른다.