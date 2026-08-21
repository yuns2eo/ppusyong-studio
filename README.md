# ppusyong-studio

뿌숑(PPUSYONG) 캐릭터 이미지를 **언제 생성하든 동일한 캐릭터로** 유지하기 위한 작업 기준 저장소입니다.

이 README는 AI(Claude / ChatGPT 등)가 읽는 작업 지침서입니다. 뿌숑 이미지 요청을 받으면 아래 순서를 그대로 따르세요.

---

## 저장소 구조

```
character/
  PPUSYONG_Character_Lock.md   범용 캐릭터 아이덴티티 락 (항상 적용)
looks/
  PPUSYONG_Office_Look.md      오피스 룩 (안경·사원증·크로스백)
references/
  basic/                       기본 상태 4방향 레퍼런스
    Front.png / Left_3Q.png / Left_Profile.png / Back.png
  office/                      오피스 룩 4방향 레퍼런스
    Front.png / Left_3Q.png / Left_Profile.png / Back.png
```

---

## 작업 순서

### 1. 아이덴티티 락 로드 (필수·예외 없음)

모든 뿌숑 이미지 요청은 `character/PPUSYONG_Character_Lock.md`를 먼저 읽는 것으로 시작합니다.
의상, 소품, 계절, 장소, 장르와 무관하게 항상 적용됩니다.

### 2. 룩 파일 판단

요청 내용에 따라 `looks/` 파일을 추가로 읽습니다.

| 요청 키워드 | 적용 파일 |
|---|---|
| 출근, 퇴근, 사무실, 회의, 발표, 업무, 오피스 | `looks/PPUSYONG_Office_Look.md` |
| 그 외 (집, 여행, 운동, 카페, 산책 등) | 없음 — 락 파일만 사용 |

애매하면 룩을 적용하지 말고 사용자에게 물어보세요.

### 3. 레퍼런스 이미지 첨부

요청한 카메라 앵글에 맞는 이미지를 첨부합니다.

| 앵글 | 파일 |
|---|---|
| 정면 | `Front.png` |
| 좌측 3/4 | `Left_3Q.png` |
| 좌측 측면 | `Left_Profile.png` |
| 뒷모습 | `Back.png` |

- 기본 씬 → `references/basic/`
- 오피스 씬 → `references/office/`
- 앵글이 명시되지 않았으면 `Front.png` + `Left_3Q.png` 두 장을 첨부합니다.

### 4. 씬 요소 작성

락 파일이 고정하지 않는 부분만 자유롭게 구성합니다.
의상, 소품, 포즈, 행동, 장소, 계절, 날씨, 조명, 분위기, 카메라 거리·앵글.

---

## 우선순위

충돌이 생기면 위쪽이 항상 이깁니다.

1. `character/PPUSYONG_Character_Lock.md`
2. 첨부된 `references/` 이미지
3. `looks/` 룩 파일
4. 사용자의 씬 요청 (환경·조명·분위기 등)

씬 요청이 캐릭터 정체성과 충돌하면 **정체성을 지키고**, 무엇을 조정했는지 사용자에게 알립니다.

---

## 금지 사항

- 락 파일 내용을 임의로 해석·완화·생략하지 않습니다.
- 씬 분위기에 맞춰 캐릭터를 리디자인하지 않습니다. 뿌숑은 배경이 바뀌어도 같은 뿌숑입니다.
- 락 파일(`character/`, `looks/`)은 사용자가 명시적으로 요청할 때만 수정합니다.

---

## 새 룩 추가 방법

새로운 상태(예: 잠옷, 운동복, 겨울옷)를 추가할 때:

1. `looks/PPUSYONG_{이름}_Look.md` 생성
   - 상단에 "`PPUSYONG_Character_Lock.md`를 먼저 읽을 것, 락 파일이 상위 우선순위" 명시
   - 탈착 가능한 요소만 정의 (의상·소품). 얼굴·비율·털·귀·꼬리·머리컬은 건드리지 않음
   - 이 룩을 쓰지 말아야 할 상황도 함께 기재
2. `references/{이름}/`에 4방향 레퍼런스 이미지 추가
3. 이 README의 구조·룩 판단 표에 항목 추가
