# 라벨 단위로 런타임에서 제어할 수 있는 디버깅 툴
![Image](https://github.com/user-attachments/assets/64819151-43da-400d-95cd-dc64c4f7708d)

Unity 프로젝트에서 Debug.Log가 많아질수록
특정 기능의 로그만 보고 싶거나, 불필요한 로그를 잠시 끄고 싶은 상황이 잦아진다.

이 디버깅 툴은
에디터의 체크박스를 통해

“이 기능 로그만 끄고 싶다”,
“에러만 보고 싶다”

같은 상황을 런타임에서도 빠르게 제어할 수 있도록 만든 시스템이다.

## 주요 기능
- Debug 로그를 Label 단위로 관리
- Log / Warning / Error 각각 개별 ON / OFF
- ScriptableObject 기반 설정으로 런타임과 에디터 설정 공유
- Enum 자동 생성 + EditorWindow 제공으로 라벨 추가 / 삭제를 안전하게 처리
  
## 사용 시 장점
- 특정 기능의 로그만 끄고 테스트할 수 있다.
- QA / 디버깅 과정에서 로그 범위를 빠르게 조절할 수 있다.
- 프로젝트 규모가 커져 로그가 많아져도 관리가 용이하다.

## 설계 포인트
**Label 기반**
- 시스템 / 기능 / 도메인 단위 로그 분리
- 로그의 의도와 출처를 즉시 파악 가능
  
**ScriptableObject 사용 이유**
- 런타임 & 에디터에서 동일한 설정 공유
- 빌드 후에도 로그 필터 유지
  
**자동 Enum 생성** 
- 문자열 로그의 가장 큰 문제 → 오타
- 컴파일 타임에 안전하게 관리


## 사용 순서
### 임포트 해서 프로젝트에 가져오기
<img width="682" height="1030" alt="Image" src="https://github.com/user-attachments/assets/cd2c5d6f-ef87-45ee-8595-941b752151d0" />

### Window 메뉴에서 Debbuger 열기
![Image](https://github.com/user-attachments/assets/12bd12d2-c0a1-4626-a933-b58087549aae)

라벨을 추가 / 삭제하면 DebugLabel enum이 자동으로 갱신된다.

### 필요한 곳에서 로그를 코드를 작성
<img width="1454" height="340" alt="Image" src="https://github.com/user-attachments/assets/4208b616-a4e1-4359-ac6d-6f93983430ef" />

Enum 기반 라벨을 사용하기 때문에 별도로 라벨 목록을 보지 않아도 어떤 로그인지 파악 가능하다.




