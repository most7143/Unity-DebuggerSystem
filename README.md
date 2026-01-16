# 라벨 단위로 Debug.Log / Warning / Error를 런타임에서 제어할 수 있는 디버깅 툴

에디터에서 체크박스를 통해

“이 기능 로그만 끄고 싶다”,
“에러만 보고 싶다”

같은 상황을 빠르게 제어하는 것을 목표로 한다.

## 주요 기능

- Debug 로그를 Label 단위로 관리
- Log / Warning / Error 각각 개별 ON/OFF
- ScriptableObject 기반 설정 (런타임 공유)
- Enum 자동 생성으로 및 EditorWindow 제공해 쉽게 추가 삭제가 되도록 구현

## 사용법
### 임포트 해서 프로젝트에 가져오기


