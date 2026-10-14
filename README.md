# imagefarm-releases

ImageFarm(판매용 데스크톱 이미지 생성 앱) **배포 전용** 공개 저장소입니다. 소스 코드는 없습니다(소스 저장소는 비공개).

여기에 있는 것:

| 위치 | 내용 |
|---|---|
| [Releases](../../releases) | 설치 파일(Windows `ImageFarm-Setup-<버전>.exe`·`.blockmap`), 자동 업데이트 정보 `latest.yml` |
| `remote-config.json` | 앱이 30분마다 받는 원격 설정(점검 중 생성 일시 중지·최소 버전). ed25519 로 서명돼 있어 앱에 든 공개키로 확인합니다 |

- 앱은 `https://raw.githubusercontent.com/japing81/imagefarm-releases/main/remote-config.json` 을 읽습니다. 서명이 맞지 않거나 예전 것이면 무시합니다.
- 설치 파일은 아직 코드 서명이 없습니다. Windows 에서 "Windows의 PC 보호" 창이 뜨면 **추가 정보 → 실행**을 누르세요.
- `remote-config.source.json` 은 서명 전 원본(지금 값)입니다. 바꾸려면 Actions 의 **sign-remote-config** 를 [Run workflow] 로 돌리고 고친 JSON 을 넣습니다 — 서명 키는 저장소 비밀에만 있어 서명은 여기서만 됩니다. 두 파일을 손으로 고치지 마세요(서명이 깨지면 앱이 무시합니다).
- 설치 파일은 운영자가 직접 올립니다.
