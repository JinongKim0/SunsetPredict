# Sunset HDRI Scorecard — GitHub Pages 배포 가이드

이 폴더(레포)를 그대로 GitHub Pages로 배포하면, 아이폰 사파리에서 열고 **홈 화면에 추가**하여 앱처럼 사용할 수 있습니다.

## 빠른 사용법 (브라우저만으로 업로드)
1. GitHub 로그인 → 우측 상단 **+** → **New repository**.
2. 레포 이름: 아무거나 (예: `sunset-scorecard`). **Public** 권장.
3. 레포가 만들어지면 **Add file → Upload files** 버튼 클릭.
4. 이 폴더의 파일(`index.html`, `README.md`)을 업로드하고 **Commit changes**.
5. 레포 상단의 **Settings → Pages** 이동.
   - **Source**: `Deploy from a branch`
   - **Branch**: `main` / **Folder**: `/root` 선택 → **Save**
6. 상단에 표시되는 배포 URL을 클릭해 접속합니다. (예: `https://<username>.github.io/sunset-scorecard/`)

## Git 로컬에서 올리기 (선호 시)
```bash
git init
git remote add origin https://github.com/<username>/sunset-scorecard.git
git add .
git commit -m "deploy scorecard"
git branch -M main
git push -u origin main
```
그 다음 **Settings → Pages**에서 위와 동일하게 설정하면 됩니다.

## 아이폰 홈 화면에 추가
1. 아이폰 **사파리**에서 배포된 URL 접속
2. 하단 **공유(□↑)** → **홈 화면에 추가**
3. 이름 입력(예: `노을 예보`) → **추가**

## 자주 묻는 질문
- **API Key가 필요한가요?**  
  아니요. Open‑Meteo와 CAMS 공개 API를 사용합니다(키 불필요).
- **시간대/위치 바꾸려면?**  
  `index.html` 상단 `LOCATIONS` 배열에서 좌표/이름 수정.
- **강수확률이 이상해요**  
  본 버전은 **시간 버킷 겹침(overlap)** 로직으로 골든/레드 최대값을 집계합니다.
- **아이콘/앱 이름 바꾸기**  
  `<title>` 수정, `apple-mobile-web-app-*` 메타 태그 참고.
