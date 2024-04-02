# flutter-webtoon-explorer

- A webtoon exploration app developed using Flutter (App 1 and App 2 are apps for practicing Flutter, and App 3 is the Webtoon Explorer App)
- StatelessWidget: Static UI / StatefulWidget: Dynamic UI (UI that changes its state)

<br>

### App 1. Wallet App using StatelessWidget (commit 2404012120)

<br>

![flutter-1](https://github.com/yeohj0710/flutter-webtoon-explorer/assets/93759367/ccff9a0b-b99a-4ede-8102-5781600571ca)

<br>

### App 2. Pomodoro App using StatefulWidget (commit 2404030007)

<br>

![flutter-2](https://github.com/yeohj0710/flutter-webtoon-explorer/assets/93759367/5cb4e565-3556-48d8-aa02-0668f29ff775)

<br>

### App 3. Webtoon Explorer App using StatefulWidget

<br>

## summarization

### Wallet App

- widget: UI를 구성하는 블록 (ex: Center는 child를 가운데로 오게 하는 widget)
- widget을 만들기 위해서는 flutter에 있는 3개의 core widget 중 하나를 extend 받아서 사용할 수 있다.
- StatelessWidget: 정적 UI / StatefulWidget: 동적 UI (상태가 변경되는 UI)

<br>

- 모든 widget은 build 메서드를 포함해야 한다.
- build 메서드: widget의 상태가 변경될 때마다 호출되어 UI를 렌더링

<br>

- root widget에는 2개의 옵션이 있다.
- material 앱(from google) > cupertino 앱(from apple)

<br>

- scaffold: 화면의 구성하는 구조
- 모든 화면은 scaffold를 가져야 한다.

<br>

### Pomodoro App

- stateful widget: 상태에 따라 데이터를 변경되면, 변화를 UI에 실시간으로 반영할 수 있는 widget

<br>

- 변경된 데이터를 UI에 업데이트하기 위해서는 setState() 함수를 사용해야 한다.
- setState() 함수를 호출하면 build() 메서드를 다시 실행된다.
  - ex) void onClicked() { setState(() { counter++; }); }
- 또는 다음과 같이 작성해도 UI가 업데이트 된다.
  - ex) void onClicked() { counter++; setState(() {}); }

<br>

- of() 메서드: Theme.of(context)는 BuildContext인 context에서 조상 중 가장 가까운 Theme widget을 찾아 데이터에 접근한다.

<br>

- initState() 메서드: widget이 최초로 생성되었을 때 한 번만 호출되는 메서드
- 잘 안 쓰이지만, super.initState()와 같이 부모 클래스까지 같이 초기화를 해 줄 수 있다.

<br>

- dispose() 메서드: widget이 스크린에서 제거될 때 호출되는 메서드

<br>
<br>
