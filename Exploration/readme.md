# AIFFEL Campus Online Code Peer Review Templete
- 코더 : 신지만
- 리뷰어 : 이윤상


# PRT(Peer Review Template)
- [X]  **1. 주어진 문제를 해결하는 완성된 코드가 제출되었나요?**
    - 문제에서 요구하는 최종 결과물이 첨부되었는지 확인
    - 문제를 해결하는 완성된 코드란 프로젝트 루브릭 3개 중 2개, 
    퀘스트 문제 요구조건 등을 지칭
        - VGG16 모델을 활용하고, transfer learning을 이용하여 문제를 해결하였습니다.
        - 학습과정 및 결과에 대한 설명이 시각화를 포함하여 체계적으로 진행되었습니다.
        - test accuracy가 93.75%로 85% 이상 도달하였습니다.
         ![image](https://github.com/lys678/AIFFEL_Online_Quest/assets/137245511/f297a9d1-3597-449b-996f-6c04ebc2a729)
    
- [X]  **2. 전체 코드에서 가장 핵심적이거나 가장 복잡하고 이해하기 어려운 부분에 작성된 
주석 또는 doc string을 보고 해당 코드가 잘 이해되었나요?**
    - 해당 코드 블럭에 doc string/annotation이 달려 있는지 확인
    - 해당 코드가 무슨 기능을 하는지, 왜 그렇게 짜여진건지, 작동 메커니즘이 뭔지 기술.
    - 주석을 보고 코드 이해가 잘 되었는지 확인
        - 잘 작성되었다고 생각되는 부분을 캡쳐해 근거로 첨부합니다.
           ![image](https://github.com/lys678/AIFFEL_Online_Quest/assets/137245511/700fd34d-8d37-464d-95e5-e061fd7fb609)
          - global average pooling에 대해 사용하는 이유, 계층을 만들 때 코드의 구현 등이 잘 설명되어 있습니다.

        
- [X]  **3. 에러가 난 부분을 디버깅하여 문제를 “해결한 기록을 남겼거나” 
”새로운 시도 또는 추가 실험을 수행”해봤나요?**
    - 문제 원인 및 해결 과정을 잘 기록하였는지 확인
    - 문제에서 요구하는 조건에 더해 추가적으로 수행한 나만의 시도, 
    실험이 기록되어 있는지 확인
        - 잘 작성되었다고 생각되는 부분을 캡쳐해 근거로 첨부합니다.
          - 학습률에 대해 여러 시도를 해보고 최적의 학습률을 찾는 과정이 나타나 있습니다.
          ![image](https://github.com/lys678/AIFFEL_Online_Quest/assets/137245511/09c98b4c-bc91-4a0b-adfd-d7e413801a7c)

        
- [X]  **4. 회고를 잘 작성했나요?**
    - 주어진 문제를 해결하는 완성된 코드 내지 프로젝트 결과물에 대해
    배운점과 아쉬운점, 느낀점 등이 기록되어 있는지 확인
    - 전체 코드 실행 플로우를 그래프로 그려서 이해를 돕고 있는지 확인
        - 잘 작성되었다고 생각되는 부분을 캡쳐해 근거로 첨부합니다.
        - 회고
             강아지 고양이 전이 모델처럼 쉽게 학습해 정학도 높은 높은 모델을 만들 수 있을 거라 생각했으나
             데이터세트가 작아서 인지 VGG16, VGG19, RssNet50에 파인 튜닝을 해도 생각만큼 정확도를 얻을 수 없다.
             특히 파인 튜닝으로 배치 사이즈, 학습률, 옵티마이, 정규화, 드롭아웃 등 많은 하이퍼파라미터를 변경했으나 결론적으로 큰 읨미는 없었으며
             결국에 Dense laser의 units 수를 1024 -> 526 -> 256으로 수정하면서 손실율이 감소하는 쪽으로 수렴하는 것을 확인했다.
             잠정적으로 데이터 세트가 작은 경우 Dense laser의 units이 크면 손실이나 정확도가 수렴하지 않고 발산할 수 있다.
        - 회고를 잘 작성하였습니다.
- [X]  **5. 코드가 간결하고 효율적인가요?**
    - 파이썬 스타일 가이드 (PEP8) 를 준수하였는지 확인
    - 하드코딩을 하지않고 함수화, 모듈화가 가능한 부분은 함수를 만들거나 클래스로 짰는지
    - 코드 중복을 최소화하고 범용적으로 사용할 수 있도록 함수화했는지
        - 잘 작성되었다고 생각되는 부분을 캡쳐해 근거로 첨부합니다.
          ![image](https://github.com/lys678/AIFFEL_Online_Quest/assets/137245511/695a1979-f05a-414c-aae5-ee98df1255e9)
          - 모델을 테스트하기 위한 부분을 함수로 구현하여 모델을 확인하고 평가하기 편리하도록 작성했습니다.



# 참고 링크 및 코드 개선
```
https://huggingface.co/google/vit-base-patch32-384)https://huggingface.co/google/vit-base-patch32-384
https://keras.io/examples/vision/vit_small_ds/?fbclid=IwAR3iuuzbXFmBhGY1HNieMcRSSsUKbXkWoNrULmox--ZiIDZV4L51WoKMO5o
성능 개선에 관하여 이야기를 하던 도중 vit32라는 모델과 관련된 이야기가 나와서 이를 참고하여 전이학습을 통해 모델의 성능을 개선 시킬 수 있다고 생각합니다.
```