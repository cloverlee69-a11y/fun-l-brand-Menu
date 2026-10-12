# 브랜드별 메뉴 추이 대시보드 (모바일 앱 / PWA)

FUN&I · OKPOS 상품별 매출 대시보드를 **휴대폰에 설치해서 쓰는 앱(PWA)** 형태로 만든 프로젝트입니다.

## 구성
- `index.html` — 대시보드 본체 (모바일 UI 보강 포함)
- `manifest.webmanifest`, `icons/` — 앱 이름·아이콘·전체화면 설정
- `sw.js` — 서비스워커 (한 번 열어두면 오프라인에서도 실행)
- `.github/workflows/pages.yml` — GitHub Pages 자동 배포

## 휴대폰에서 쓰는 방법
1. 저장소 **Settings → Pages → Source: GitHub Actions** 로 설정 (최초 1회)
2. 배포 후 주소 `https://<계정>.github.io/<저장소>/` 를 휴대폰 브라우저로 접속 (HTTPS 필수)
3. 설치
   - **Android(Chrome)**: 상단 `앱 설치` 버튼 또는 메뉴 → *홈 화면에 추가*
   - **iPhone(Safari)**: 공유 버튼 → *홈 화면에 추가*

## 모바일용 수정 사항
- 900px 이하: 슬라이드 사이드바 + 어두운 배경(탭하면 닫힘), 44px 터치 영역
- 노치/홈바 safe-area 대응, 입력창 16px(iOS 자동 확대 방지)
- KPI·TOP5·요일별 카드 등 1~2열 재배치, 표는 가로 스크롤
- 외부 라이브러리(Chart.js, SheetJS)·폰트는 첫 접속 때 캐시되어 이후 오프라인 사용 가능

> 업로드한 엑셀 데이터와 원가표는 각 기기 브라우저(localStorage)에 저장됩니다. 기기 간 자동 동기화는 되지 않습니다.
