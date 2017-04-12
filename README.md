# MVC
- M : Model
  - 속성 및 상태를 가진다.
- V : View
  - Model의 속성 및 상태를 참조해서 화면을 그린다.
- C : Controller
  - 이벤트를 처리(Model의 속성 및 상태 변경 요청)하고 View에 갱신을 요청한다.
  
![MVC Flow](https://github.com/bsscco/mvctest/blob/master/mvc-flow.png?raw=true)
User input -> Controller에서 Model에게 속성 및 상태 변경 요청 -> Model의 속성 및 상태 변경 -> Controller에서 View에게 UI 갱신 요청 -> **View는 Model을 참조**하여 UI 갱신

### 오늘의집(Android)은 전반적으로 MLVC 패턴으로 제작하였습니다. MLV(LightView)C는 지어낸 용어입니다.
- M : Model(Data Response Object)
  - 네트워크 데이터 응답 객체
  - 속성 및 상태를 포함한다.
  - Controller에 의해 속성 및 상태가 바뀐다.
- LV : LightView(RecyclerView, ItemViews)
  - UI 드로잉
  - 표시값의 가공 로직을 포함
  - Controller에 의해 UI 갱신을 요청받는다. 갱신에 필요한 값은 Controller로부터 제공받습니다. 이로써 Model-View 간 의존성을 제거해서 View재활용성을 높였습니다.
- C : Adapter
  - 네트워크 데이터 요청
  - 네트워크 데이터 응답을 파싱(M:네트워크 데이터 응답 객체)해서 가지고 있는다.
  - 클릭 이벤트 등 유저인풋을 처리한다.


User input -> Controller에서 Model에게 속성 및 상태 변경 요청 -> Model의 속성 및 상태 변경 -> Controller에서 View에게 UI 갱신 요청 -> **View는 Controller로부터 받은 값을 참조**하여 UI 갱신
![MLVC Flow](https://github.com/bsscco/mvctest/blob/master/mlvc-flow.png?raw=true)
