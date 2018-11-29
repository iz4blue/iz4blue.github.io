# Apple Watch App 처음 당황한 부분
- 처음 Apple Watch App 을 개발할 때는 Xcode 10 에 미리 만들어져 있는 하드웨어 세트를 선택하자
- iPhone XS 와 40mm 가 이미 연결되어 있음
- iPhone XS MAX 와 44mm 가 이미 연결되어 있음
- 위 내용을 기초로 처음에 불필요한 삽질의 시간을 줄이자

## Xcode 10 에 기본 설치된 Watch 시뮬레이터 확인
![iPhone XS](/posts/img/2018-11-29/image-001.png)
![iPhone XS MAX](/posts/img/2018-11-29/image-002.png)

## Hello World 해보자

### iPhone XS 를 선택하고 Run 실행
![iPhone XS로 변경해서 Run](/posts/img/2018-11-29/image-003.png)

### iPhone XS 와 38mm Pairing
- iPhone XS 가 완전히 실행 될 때 까지 기다림
- 앱이 설치 될 때 까지 기다림
- 시뮬레이터에서 iOS와 연결된 Watch 시뮬레이터를 구동시켜 줌
  - 반드시 watchOS 5.1, Series 4 - 40mm 를 선택한다.
![페어링되어 있는 Watch 선택](/posts/img/2018-11-29/image-005.png)
- watchOS 가 완전히 구동될 때 까지 기다린다.
  - 마이크 허용 권한을 물어보는 경우 허용해준다.
- iOS 에서 watch 앱을 실행해준다.
![Watch 앱 실행](/posts/img/2018-11-29/image-006.png)
- 구동된 Watch 시뮬레이터와 싱크가 성공할 때 까지 기다린다.
  - 아주 조금씩 진행 바가 올라가는 것을 끝까지 기다린다.
![1/4조금 넘게 진행됨](/posts/img/2018-11-29/image-007.png)
![1/2조금 넘게 진행됨](/posts/img/2018-11-29/image-008.png)
- 이제 페어링 성공!
![페어링 성공](/posts/img/2018-11-29/image-009.png)

### iOS 를 통해 Watch App 이 설정가능하게 됨을 확인
- watch app 을 통해서 watch 에 앱을 설치할 수 있게 되는 것을 확인
![페어링 성공](/posts/img/2018-11-29/image-010.png)
- watch 에 app 이 설치 됨을 확인
![완료](/posts/img/2018-11-29/image-011.png)
