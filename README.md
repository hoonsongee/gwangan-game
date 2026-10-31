# 광안 3D — 인터넷 공개 배포 버전

이 프로젝트는 기존 광안 모바일 웹게임을 유지하면서 Render에 올려 **서로 다른 Wi-Fi / LTE / 5G**에서 하나의 링크로 접속하도록 준비한 버전입니다.

## 공개 링크 만들기 (Render + GitHub)

1. https://github.com 에 로그인하고 새 **Public 또는 Private repository**를 만듭니다.
2. 이 ZIP의 압축을 푼 뒤, **gwangan-public-link-ready 폴더 안에 있는 파일 전체** (`server.js`, `package.json`, `public/`, `render.yaml` 등)를 GitHub 저장소 최상위에 업로드하고 Commit합니다. ZIP 파일 자체만 올리면 배포되지 않습니다.
3. https://dashboard.render.com 에 로그인한 뒤 **New → Blueprint**를 선택하고 방금 만든 GitHub 저장소를 연결합니다.
4. `render.yaml` 설정을 확인하고 **Deploy Blueprint**를 누릅니다. 무료 플랜이 제공되지 않거나 조건이 바뀌었으면 표시되는 요금과 정책을 확인한 뒤 진행하세요.
5. 배포가 완료되면 Render가 보여주는 `https://...onrender.com` 주소를 복사해 공유합니다. 그 주소가 실제 공개 게임 링크입니다. 배포 전에는 공개 링크가 없습니다.
6. 맥북 Wi-Fi와 다른 휴대폰의 모바일 데이터로 각각 열어 멀티플레이를 확인합니다.

## 참고

- Render 무료 인스턴스는 일정 시간 접속이 없으면 절전 상태가 되어 첫 접속에 시간이 걸릴 수 있습니다. 플랜/정책은 Render 안내를 확인하세요.
- 멀티플레이 접속 정보, 종이배 1일 제한, 날씨는 현재 서버 메모리에 보관됩니다. 서버 재시작 시 초기화되며, 여러 서버 인스턴스로 확장할 경우 Redis/DB 및 Socket.IO 어댑터가 필요합니다.
- 테스트 종이배는 기존대로 무제한 미리보기 가능합니다. 서버의 실제 종이배는 공연 시간 제한이 적용됩니다.
- 배포된 사이트는 누구나 접속할 수 있으므로 개인 정보나 비밀키를 코드에 넣지 마세요.
- 배포에 사용할 Node.js 버전은 20 이상을 권장합니다.

## 맥북 로컬 실행

```bash
npm install
npm start
```

로컬 접속: http://localhost:3000

상태 확인: http://localhost:3000/health
