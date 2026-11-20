# TC AI 배포

Total Commander 옆에 붙는 AI 채팅 패널 **TC AI**의 설치 파일을 배포하는 저장소입니다. 소스는 별도 저장소에서 관리합니다.

## 설치

1. [Releases](https://github.com/wind1018/totalcommand-ai-release/releases/latest) 에서 `TcAi-Setup-<버전>.exe` 를 받아 실행합니다.
2. 관리자 권한 없이 `%LOCALAPPDATA%\Programs\TcAi` 에 설치됩니다. Node.js 와 Python 이 함께 들어 있어 따로 설치할 것이 없습니다.
3. "Total Commander 버튼바에 TC AI 버튼 추가" 를 켜 두면 버튼이 등록됩니다. Total Commander 를 다시 시작하면 보입니다.
4. 버튼을 눌러 패널을 열고 **설정 → 연결** 에서 LLM 서버 주소와 API 키를 넣습니다.

요구 사항: Windows 10/11 64비트, Total Commander. PC 전체 검색을 쓰려면 [Everything](https://www.voidtools.com/) 을 실행해 둡니다(선택).

## 업데이트

새 버전 설치 파일을 그대로 실행하면 덮어씁니다. 실행 중인 TC AI 는 설치기가 끝냅니다. 설정, 키, 비밀 금고, 대화 기록, 스킬은 그대로 남습니다.

## 제거

Windows 설정 → 앱 에서 "TC AI" 를 제거합니다. 버튼바의 TC AI 버튼도 함께 지웁니다. 사용자 데이터는 남기므로, 완전히 지우려면 아래 폴더를 직접 지웁니다.

| 위치 | 내용 |
|---|---|
| `%APPDATA%\tc-ai` | 패널 설정, 암호화된 API 키, 비밀 금고, 패널 로그 |
| `%LOCALAPPDATA%\Programs\TcAi\agent` | 대화 기록(sessions), 고른 모델, 스킬 |

## 자동 업데이트 매니페스트

[`latest.json`](latest.json) 은 최신 버전 정보이며 앞으로 패널의 자동 업데이트가 읽습니다.

| 필드 | 뜻 |
|---|---|
| `version` | 최신 버전 (`x.y.z`) |
| `url` | 설치 파일 다운로드 주소 |
| `sha256` | 설치 파일 해시. 받은 뒤 반드시 확인 |
| `size` | 바이트 크기 |
| `silentArgs` | 조용한 설치 인수. `/RELAUNCH=1` 이면 설치 뒤 패널을 다시 띄움 |

변경 내역은 [CHANGELOG.md](CHANGELOG.md) 에 있습니다.
