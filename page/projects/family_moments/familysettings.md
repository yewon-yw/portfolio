# ⚙️ 가족 설정

### 목차

- [가족 정보 수정](#가족-정보-수정)
- [알림 주기 변경](#알림-주기-변경)
- [권한 넘기기, 가족 강퇴](#권한-넘기기-가족-강퇴)
- [가족 탈퇴, 삭제](#가족-탈퇴-삭제)

<br>

## <a name="가족-정보-수정"></a>⭐️ 가족 정보 수정

<img src="https://github.com/user-attachments/assets/325ba510-d760-49ee-b46e-68d00cf10d29" alt="가족정보수정" width="30%">

**[문제 해결]**
- 이미지 선택 메뉴 디자인이 iOS의 액션 시트 형식으로 변경됨
  - 안드로이드의 다이얼로그로 구현
    - `fillMaxWidth()`가 적용되지 않는 문제를 `DialogProperties`를 사용해 해결
    - 하단에 정렬해야 할 다이얼로그가 중앙에 정렬되는 문제를 다이얼로그 상단 `Box`에 `weight`를 적용해 해결
- 파일 명이 동일한 경우 컴포저블이 변경을 감지하지 못하는 문제
  - 컴포저블은 파일 경로를 통해 파일의 변화를 감지하므로, 사진이 변경될 때마다 파일명을 변경해서 해결
- 가족 정보 변경 시 앱 바에 해당 정보가 반영되지 않는 문제
  - 앱 바의 데이터가 다른 뷰모델에 존재하지만, 뷰모델 간 의존성을 제거하기 위해 이벤트 객체를 생성해 해결

<br>

## <a name="알림-주기-변경"></a>⭐️ 알림 주기 변경

<img src="https://github.com/user-attachments/assets/c5227015-1f9d-411a-9564-e53d72d38185" alt="알림주기변경" width="30%">


**[문제 해결]**
- 드롭다운 메뉴에 `fillMaxWidth()` 적용되지 않는 문제
  - 사용중인 material3 버전에서 발생하는 버그임을 확인
  - material3의 버전을 업그레이드하여 해결
- 드롭다운 메뉴의 기본 패딩이 제거되지 않는 문제
  - Modifier 확장 함수를 구현해 제거

<br>

## <a name="권한-넘기기-가족-강퇴"></a>⭐️ 권한 넘기기, 가족 강퇴
|권한 넘기기| 가족 강퇴|강퇴된 유저|
|:-:|:-:|:-:|
|<img src="https://github.com/user-attachments/assets/7dd9de54-d2ab-4e55-a1dc-ae982c209c5d" alt="권한 넘기기" width="70%" align = "center">|<img src="https://github.com/user-attachments/assets/e5e2a1b1-3208-4ecf-af31-2314fe4ae327" alt="가족 강퇴" width="70%" align = "center">|<img src="https://github.com/user-attachments/assets/c33dce3e-8768-40c4-82b4-f8e82ef67678" alt="강퇴된 유저" width="70%" align = "center">|

**[문제 해결]**
- arguments로 전달받은 리스트의 파싱 문제
  - 정규식을 활용해서 대괄호를 직접 제거해 해결
- 강퇴된 사용자가 해당 가족에서 강퇴된 것을 확인하기 어려운 문제
  - 스플래시 화면에서 해당 내용을 확인할 수 있는 API를 실행해 적절한 화면 전환을 구현


**[배운 점]**
- `buildAnnotatedString` 사용법을 익힘
  - 다른 텍스트 스타일을 가지는 텍스트를 연결하기 위해 사용
- 단일 체크 및 다중 체크 방식 구현 방법을 배움

<br>

## <a name="가족-탈퇴-삭제"></a>⭐️ 가족 탈퇴, 삭제
|가족 탈퇴|가족 삭제|
|:-:|:-:|
|<img src="https://github.com/user-attachments/assets/c633ed43-4540-4a6f-a602-384f23a781ff" alt="가족 탈퇴" width="70%" align = "center">|<img src="https://github.com/user-attachments/assets/e01ea063-d098-442f-959f-6f5585a0f006" alt="가족 삭제" width="70%" align = "center">|

**[문제 해결]**
- API 중복 요청이 가능한 문제
  - 가족 탈퇴나, 삭제의 경우엔 중복 요청이 발생하면 안 되는 API
  - 이전 화면으로 돌아가서 중복 요청하지 못하도록 뒤로가기와 시스템 백버튼을 막아서 해결

