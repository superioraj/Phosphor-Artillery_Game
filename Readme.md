# PHOSPHOR ARTILLERY

> 1980년대 DOS 녹색 CRT 화면 스타일의 턴제 포격 게임  
> 브라우저에서 바로 실행되며, micro:bit 블루투스 제어와 온라인 1:1 대전을 지원합니다.

**플레이:** https://<사용자이름>.github.io/<저장소이름>/

**버전:** v3.4

---

## 소개

PHOSPHOR ARTILLERY는 각도와 위력을 조절해 상대 탱크를 맞히는 아틸러리(포격) 장르 게임입니다.
바람, 지형 파괴, 보급 헬기, 다양한 포탄을 활용해 마지막까지 살아남으면 승리합니다.

- 설치나 빌드 과정이 없는 **HTML 파일 하나**로 동작합니다.
- 게임 계산은 모두 **브라우저 안에서** 처리됩니다.
- 이름의 *Phosphor(인광체)* 는 옛 CRT 모니터의 초록 빛을, *Artillery(포격)* 는 게임 장르를 뜻합니다.

---

## 주요 기능

| 구분 | 내용 |
|---|---|
| 게임 방식 | 1인 + AI 대전 / 같은 기기에서 교대(2~4대) / 온라인 1:1 |
| AI | 난이도 1~10단계, AI도 이동·보급 획득·함정 회피 |
| 전장 | 무작위 지형, 둥근 폭발 구덩이, 지형 붕괴와 추락 피해, 매 차례 변하는 바람 |
| 포탄 | 기본탄, 중포탄, 분열탄, 지진탄 |
| 보급 | 바람에 흔들리는 헬기가 낙하산 상자 투하, 아이템 10종 |
| 규칙 | 3선승제, 30발 이후 서든데스(피해 2배), 60발 무승부 |
| 연출 | 바퀴가 굴러가는 탱크, 화면 흔들림, 섬광, 파편, 연기, 바람 줄기 |
| 외부 제어 | micro:bit 기울기·버튼으로 조종(Web Bluetooth) |

---

## 조작 방법

### 키보드 / 마우스

| 키 | 동작 |
|---|---|
| `A` / `D` | 누르는 동안 왼쪽 / 오른쪽 이동 (연료 소모) |
| `←` / `→` | 각도 ±1° (SHIFT: ±5°) |
| `↑` / `↓` | 위력 ±10 (SHIFT: ±50) |
| `1` ~ `4` | 포탄 선택 |
| `SPACE` | 발사 |
| `ENTER` | 전투 시작 / 다음 라운드 |
| `F1` / `F2` | 도움말 / 메뉴 |

터치 화면에서는 이동 버튼을 길게 누르면 계속 이동합니다.

### micro:bit

| micro:bit 동작 | 게임 동작 |
|---|---|
| 위/아래로 기울이기 | 각도 조절 (많이 기울일수록 빠름) |
| 좌/우로 기울이기 | 탱크 이동 |
| A 버튼 | 발사 |
| B 버튼 | 포탄 변경 |
| A+B 버튼 | 전투 시작 |
| 로고 터치 | 다음 라운드 / 새 경기 |

---

## 게임 규칙

### 한 차례의 흐름

1. **이동** - 연료(매 차례 48)를 써서 위치 조정
2. **조준** - 각도와 위력 조절
3. **포탄 선택**
4. **발사** - 발사하면 차례 종료

### 포탄

| 포탄 | 특징 | 지급 |
|---|---|---|
| 기본탄 | 반경 26 / 피해 55 | 무제한 |
| 중포탄 | 반경 45 / 피해 80 | 라운드마다 1발 (최대 4) |
| 분열탄 | 최고점에서 3갈래 / 각 피해 36 | 라운드마다 1발 (최대 4) |
| 지진탄 | 반경 67 큰 구덩이 / 피해 24 / 추락 유도 | 보급으로만 획득 (최대 3) |

### 보급 상자 10종

라운드 시작과 3발마다 헬기가 상자를 투하합니다(최대 2개). 전차로 지나가거나 포탄으로 맞히면 획득합니다.

| 표시 | 아이템 | 효과 | 확률 |
|---|---|---|---|
| H | 중포탄 | 중포탄 +1 | 12% |
| S | 분열탄 | 분열탄 +1 | 11% |
| Q | 지진탄 | 지진탄 +1 | 8% |
| + | 수리 | 체력 +25 | 12% |
| O | 방어막 | 방어막 +35 | 10% |
| F | 연료 2배 | 다음 차례 연료 96 | 11% |
| C | 무풍탄 | 다음 1발 바람 무시 | 9% |
| L | 정밀 조준경 | 다음 발사까지 탄도 전체 표시 | 10% |
| P | 강화탄 | 다음 1발 피해 1.5배 | 8% |
| ! | 함정 상자 | 밟으면 피해 15 / 포탄으로 맞히면 폭발 | 9% |

### AI 난이도

| 단계 | 특징 |
|---|---|
| 1~2 | 조준 오차가 크고 바람을 거의 무시 |
| 3~4 | 바람 일부 계산, 보급 상자를 노려 이동 |
| 5~7 | 고지대 이동, 함정 회피, 약한 전차 우선 공격 |
| 8~10 | 정확한 바람 계산, 특수탄 적극 사용 |

---

## 온라인 1:1 대전

방 코드 5자리로 연결합니다.

1. 두 사람 모두 메뉴에서 **온라인 1:1** 선택
2. **호스트:** `[방 만들기]` → 화면의 5자리 코드를 상대에게 알려주기
3. **게스트:** `[방 참가]` → 코드 입력 → `[접속]`
4. **호스트:** 접속 요청이 오면 `[허용]` → 자동으로 전투 시작

- 연결을 시작할 때 무료 공개 중계 서버 [PeerJS](https://peerjs.com/)를 사용합니다.
- 게임 계산은 호스트 브라우저에서 처리하고, 결과를 게스트 화면에 똑같이 보여줍니다.
- 두 사람 모두 **같은 버전(v3.4)** 을 사용해야 합니다.

---

## micro:bit 연결

### 1. MakeCode 프로그램 만들기

1. [MakeCode for micro:bit](https://makecode.microbit.org/)에서 새 프로젝트를 만듭니다.
2. **확장**에서 `bluetooth`를 추가합니다. radio 확장이 제거된다는 안내가 나오면 확인을 누릅니다.
3. **톱니바퀴 → 프로젝트 설정**에서 `No Pairing Required`를 켭니다.
4. **JavaScript** 탭에 아래 코드를 붙여넣고 micro:bit에 다운로드합니다.

```typescript
let connected = false
bluetooth.startUartService()
basic.showIcon(IconNames.Diamond)

bluetooth.onBluetoothConnected(function () {
    connected = true
    basic.showIcon(IconNames.Yes)
})
bluetooth.onBluetoothDisconnected(function () {
    connected = false
    basic.showIcon(IconNames.No)
})
input.onButtonPressed(Button.A, function () {
    if (connected) bluetooth.uartWriteLine("A")
})
input.onButtonPressed(Button.B, function () {
    if (connected) bluetooth.uartWriteLine("B")
})
input.onButtonPressed(Button.AB, function () {
    if (connected) bluetooth.uartWriteLine("AB")
})
input.onLogoEvent(TouchButtonEvent.Pressed, function () {
    if (connected) bluetooth.uartWriteLine("L")
})
basic.forever(function () {
    if (connected) {
        bluetooth.uartWriteLine("T," + input.rotation(Rotation.Pitch) + "," + input.rotation(Rotation.Roll))
    }
    basic.pause(100)
})
```

> **micro:bit V1 사용 시:** 로고 터치가 없으므로 `input.onLogoEvent(...)` 부분을 아래 코드로 바꾸세요. GND를 잡은 채 P0 핀을 만지면 다음 라운드로 넘어갑니다.
>
> ```typescript
> input.onPinPressed(TouchPin.P0, function () {
>     if (connected) bluetooth.uartWriteLine("L")
> })
> ```

### 2. 게임과 연결하기

1. micro:bit 화면에 ◇ 모양이 뜨면 연결 대기 상태입니다.
2. **https 주소(GitHub Pages)** 로 게임을 엽니다.
3. `[ micro:bit 연결 ]` 버튼 → 목록에서 `BBC micro:bit [...]` 선택
4. micro:bit에 ✓ 표시가 뜨고, 화면 위쪽 PITCH / ROLL 값이 움직이면 연결 완료입니다.
5. 기울인 방향과 반대로 움직이면 `위/아래 반전`, `좌/우 반전`을 켜세요.

### micro:bit가 보내는 신호

| 신호 | 의미 |
|---|---|
| `T,피치,롤` | 기울기 (0.1초마다) |
| `A` / `B` / `AB` | 버튼 입력 |
| `L` | 로고 터치 |

---

## 설치 및 배포

### 로컬에서 실행

`index.html`을 브라우저로 열면 바로 실행됩니다.
단, micro:bit 연결은 https 환경에서만 동작하므로 GitHub Pages로 배포해 사용하세요.

### GitHub Pages 배포

1. 이 저장소 최상위에 `index.html`, `README.md`를 올립니다.
2. **Settings → Pages** 에서 **Deploy from a branch** 선택
3. 브랜치 `main`, 폴더 `/(root)` 선택 후 저장
4. 잠시 뒤 표시되는 주소로 접속합니다.

### 파일 구조

```
/
├── index.html   # 게임 전체 (HTML + CSS + JavaScript)
└── README.md    # 이 문서
```

---

## 지원 환경

| 기능 | Chrome / Edge (PC, 안드로이드) | Safari (iPhone, iPad) |
|---|---|---|
| AI / 로컬 대전 | 지원 | 지원 |
| 온라인 1:1 | 지원 | 지원 |
| micro:bit 연결 | 지원 | 미지원 (Web Bluetooth 없음) |

---

## 개인정보 및 네트워크

- 쿠키, 분석 도구, 로컬 저장소를 사용하지 않습니다. 새로고침하면 진행 기록이 사라집니다.
- AI·로컬 대전은 외부로 데이터를 보내지 않습니다.
- **온라인 대전 시**에만 PeerJS 라이브러리와 중계 서버를 사용하며, 연결 과정에서 IP 주소가 중계 서버에 전달됩니다. 게임 데이터는 보통 두 브라우저 사이에서 직접 오가지만, 직접 연결이 막힌 네트워크에서는 중계 서버를 거칠 수 있습니다.
- micro:bit는 브라우저와 블루투스로 직접 연결됩니다.

---

## 알려진 제한사항

- 온라인 대전은 무료 공개 서버를 사용하므로 서버 상태나 학교·회사 방화벽에 따라 연결되지 않을 수 있습니다.
- 온라인 연결이 끊기면 이어서 할 수 없으며 다시 연결해야 합니다.
- 저장/불러오기, 사운드 기능은 없습니다.
- 전장은 Canvas로 그려지므로 스크린리더만으로 조준하기에는 한계가 있습니다.
- 운영체제의 '동작 줄이기' 설정을 켜면 흔들림·파편 등 연출이 자동으로 줄어듭니다.

---

## 고지

이 게임은 고전 아틸러리 게임 *Scorched Earth*(1991)에서 영감을 받은 **독립 구현작**입니다.
원작의 코드, 그래픽, 음원을 사용하지 않았으며 원작자와 관련이 없습니다.
