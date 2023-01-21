---

layout: post

---

4.4절에서 다루는 스레드 생성 전략( [[비동기 스레딩]] , [[동기 스레딩]] ) 은 종종 fork-join 모델로 알려져 있다.

이 메소드를 사용하면 메인 부모 스레드가 하나 이상의 자식 스레드를 생성(fork)한 다음 자식의 종료를 기다린 후 join하고 그 시점부터 자식의 결과를 확인하고 결합할 수 있다.

이 동기식 모델은 종종 명시적 스레드 생성이라고 특정지어지지만 암시적 스레딩에도 사용될 수 있다.

후자희 상황에서, fork 단계에서는 스레드가 직접 구출되지 않고 대신 병렬 작업이 식별된다.

![image](https://user-images.githubusercontent.com/116250393/213496876-d4ed548f-85ad-4db0-ae4d-a54a3d98e969.png)

라이브러리는 생성되는 스레드 수를 관리하며 스레드에 작업 배정을 책임진다.

어떤 식으로든 이 fork-join 모델은 라이브러리가 생성할 실제 스레드 수를 결정하는 동기 버전의 스레드 풀이다([[스레드 풀]]에서 설명된 [[휴리스틱]]을 사용하여).