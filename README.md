# Today's Webtoon (Flutter App)

- A mobile application for viewing webtoons uploaded today on 'Naver Webtoon' (built with Flutter)
- You can download and install 'today's-webtoon-installer.apk'

<br>

![todays-webtoon-flutter-app](https://github.com/yeohj0710/todays-webtoon-flutter-app/assets/93759367/115c9d9e-5bb1-4a1c-bdfa-c6b30bf50f2f)

<br>
<br>

## Projects practiced to enhance Flutter development skills

### Wallet App using StatelessWidget (commit 2404012120)

<br>

![flutter-1](https://github.com/yeohj0710/todays-webtoon-flutter-app/assets/93759367/e1a291a9-e96e-4abf-ba9d-4861710eee76)

<br>

### Pomodoro App using StatefulWidget (commit 2404030018)

<br>

![flutter-2](https://github.com/yeohj0710/todays-webtoon-flutter-app/assets/93759367/6d0026b8-971f-4716-9127-4cc8f628d739)

<br>
<br>

## Study Notes Summarization

### Wallet app

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

### Pomodoro app

- stateful widget: 상태에 따라 데이터를 변경되면, 변화를 UI에 실시간으로 반영할 수 있는 widget

<br>

- 변경된 데이터를 UI에 업데이트하기 위해서는 setState() 함수를 사용해야 한다.
- setState() 함수를 호출하면 build() 메서드가 다시 실행된다.
```dart
void onClicked() { setState(() { counter++; }); }
```
- 또는 다음과 같이 작성해도 UI가 업데이트 된다.
```dart
void onClicked() { counter++; setState(() {}); }
```

<br>

- of() 메서드: Theme.of(context)는 BuildContext인 context에서 조상 중 가장 가까운 Theme widget을 찾아 데이터에 접근한다.

<br>

- initState() 메서드: widget이 최초로 생성되었을 때 한 번만 호출되는 메서드
- 잘 안 쓰이지만, super.initState()와 같이 부모 클래스까지 같이 초기화를 해 줄 수 있다.

<br>

- dispose() 메서드: widget이 스크린에서 제거될 때 호출되는 메서드

<br>

### Today's webtoon app

- Flutter나 Dart의 공식 패키지 저장소는 pub.dev이다.
- 패키지는 flutter pub add "패키지명" 명령어를 사용하여 설치한다.

<br>

- Future: flutter에서 비동기 작업을 수행하고 결과를 반환하는 객체
- Future 객체를 반환받으려면 await을 사용해 주어야 한다.

<br>

- Future 객체를 이용해 data를 fetch 할 때는 setState()를 사용할 필요가 없다.
- FutureBuilder라는 widget을 이용하면, StatelessWidget으로도 반환된 Future 객체의 데이터를 전달해줄 수 있다.
- (future: Future 객체 이름, builder: (context, snapshot) { 함수 })

<br>

- ListView: 여러 개의 항목들을 나열해서 볼 수 있는 widget
- ListView.builder: infiniteScroll 등의 기능을 구현할 수 있는 최적화된 ListView
- ListView.separator: ListView.builder에 separatorBuilder라는 추가로 인자를 가진다.

<br>

- Container widget에서, clipBehavior 속성을 통해 자식의 부모 영역 침범을 제어할 수 있다. (ex: clipBehavior: Clip.hardEdge) 

<br>

- Flutter에서 Screen을 이동하는 법: Navigator
- Navigator는 context와 route를 필요로 한다. (Navigator.push(context, route))
- route는 widget을 스크린처럼 보이도록 한다. 
- route 자리에는 MaterialPageRoute와 같은 클래스들이 들어간다.
- fullscreenDialog: card → full screen (옆으로 넘겨서 닫는 것이 아닌, 밑에서 화면이 팝업됨)

<br>

- Hero widget: 두 개의 widget 화면을 애니메이션으로 전환하게 해주는 widget
- hero widget을 두 widget에 사용하고, 같은 tag 값을 주면 된다.

<br>

- Future 객체는 constructor로 초기화할 수는 없으므로, 이를 초기화할 때는 late modifier가 유용하다.

<br>

- Flutter에서 앱 내에서 브라우저를 열도록 하는 방법: url_launcher 패키지를 설치하여 이용하면 된다.

<br>

- 앱 내에서 모바일 기기에 데이터를 저장하는 방법: shared_preference 패키지를 사용하면 된다.

<br>

- app 완성 이후, 빌드하기 전 인터넷 권한 문제 해결을 해야 한다.
- Project 뷰 > android > app > src > main > AndroidManifest.xml에서,
- <application> 태그 바로 윗 줄에 다음의 코드를 입력하여 권한을 추가한다.
```xml
<uses-permission android:name="android.permission.INTERNET" />
```

<br>

- app 아이콘 변경하는 법: App Icon Generator를 이용해 폴더를 생성하고, android 또는 ios의 아이콘 폴더 자리에 위치시키면 된다.
- android icon 폴더 위치: android/src/main/res
- ios icon 폴더 위치: ios/Runner/Assets.xcassets

<br>

- android apk 빌드 명령어: flutter build apk --release --target-platform=android-arm64
- 빌드 경로: [Project Forder]/build/app/outputs/apk/release/app-release.apk

<br>
<br>

