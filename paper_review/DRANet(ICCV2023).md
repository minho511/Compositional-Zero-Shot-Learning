# DRANet(ICCV2023) 
- Paper : Distilled Reverse Attention Network for Open-world Compositional Zero-Shot Learning(ICCV2023)
- Review Date: 2023.10.23
___
## Intro

전형적인 CZSL 방식은 composition들의 joint representation을 학습하는 것.

다른 방향의 연구로는 attribute와 object를 분리하는 방식으로 모델링하여 compositional learning을 attribute, object learning 문제로 다룬다.

그중에서도 몇몇 연구는 이러한 방식(고립된 모델링)이 속성-객체 간 상호작용을 무시한다는 것을 발견하였고,  
따라서 **dientangle attributes and object** 방식으로 CW-CZSL을 해결하고자 하였다.  
(ex. affinity estimation, contrastive learning, cutting the confounding links)


- 이 논문은 새로운 disentangling 전략을 제안한다. (특히 Open-World에 적합한 방식임을 강조한다)

- OW-CZSL을 위해 disentangling 을 시도한 첫번째 방식이다.

