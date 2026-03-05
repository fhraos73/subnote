#SW공학 #디자인패턴 #아키텍처

## 정의
데이터 바인딩 기반 UI 패턴, MVVM
- Model-View-ViewModel로 구성되며, 데이터 바인딩을 통해 View와 로직을 완전히 분리하는 패턴
- MVC의 발전형으로, ViewModel이 View의 상태와 동작을 추상화하여 테스트 용이성과 재사용성 향상
## 키워드
- Model, View, ViewModel, Data Binding
## 암기법
- **MVVM**: 모뷰뷰모 (Model-View-ViewModel)
- **바인딩**: 양방향 자동 동기화
## 목적
- 데이터 바인딩을 통한 View와 로직의 완전한 분리
- UI 로직의 테스트 용이성 및 유지보수성 향상
## 구성요소
| 구성요소 | 역할 |
|---------|------|
| Model | 데이터, 비즈니스 로직 |
| View | 화면 표시 (XAML, XML) |
| ViewModel | View 상태, Command, 바인딩 |
## 연관 토픽
- [[MVC 패턴]] - [[MVI 패턴]] - [[디자인패턴]]
## 특징
- 양방향 바인딩: View와 ViewModel 자동 동기화
- 테스트 용이: ViewModel 단독 테스트 가능
- 완전 분리: View와 로직의 명확한 분리
- 재사용성: ViewModel 여러 View에서 재사용
## 동작 흐름
```
View ←(Data Binding)→ ViewModel ←→ Model
```
## 적용 프레임워크
- WPF, Xamarin, Angular, Vue.js, SwiftUI
