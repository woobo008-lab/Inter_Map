# Inter_Map

React, Vite, Leaflet으로 만든 지도 메모 앱입니다. 지도를 클릭해 카테고리가 있는 메모 핀을 만들고, 핀은 브라우저 로컬 저장소에 자동 저장됩니다.

## 실행

```bash
npm install
npm run dev
```

개발 서버를 실행해야 JSON 파일 저장 기능도 사용할 수 있습니다. JSON 내보내기는 프로젝트의 `json` 폴더에 날짜가 포함된 파일로 저장하며, JSON 가져오기는 같은 폴더에 있는 파일 목록에서 선택합니다. 가져온 핀은 기존 핀에 추가됩니다.

## 배포

저장소의 `master` 브랜치에 푸시하면 GitHub Actions가 사이트를 빌드하고 `dist`를 GitHub Pages에 배포합니다. GitHub 저장소의 **Settings → Pages → Build and deployment → Source**를 **GitHub Actions**로 설정해야 합니다. 수동 배포는 Actions 탭에서 **Deploy to GitHub Pages** 워크플로의 **Run workflow**를 실행하세요.

로컬에서 빌드할 수도 있습니다.

```bash
npm run build
```

빌드 결과는 `dist`에 생성됩니다. `dist/index.html`은 배포 진입점이며, 앱 자산 경로는 저장소 하위 경로에서도 동작하도록 상대 경로로 생성됩니다.

핀은 브라우저별 로컬 저장소에 저장되므로 다른 브라우저나 기기와 자동으로 동기화되지 않습니다. JSON 가져오기/내보내기 기능은 Vite 개발·미리보기 서버 전용이며, 정적 호스팅에서는 사용할 수 없습니다.

## 기술 정보

- 일반 지도: OpenStreetMap
- 위성 이미지: Esri World Imagery
- 지도 표시 및 상호작용: Leaflet, React-Leaflet
- 개발 서버 JSON API: Vite 서버 미들웨어
