# 이번 달까지만 버텨주세요

**Please Let Us Survive This Month**

한국 중소 제조업 생존을 소재로 한 브라우저 경영 시뮬레이션 프로토타입입니다.

플레이어는 자금난에 시달리는 중소 제조업 회사를 운영합니다. 생산은 돌아가지만 돈은 부족하고, 은행은 압박하고, 거래처는 납기를 재촉합니다. 현장, 조립실, 사무실, 설계실을 오가며 생산 관리, 현금 흐름 관리, 설계 개선, 납기 대응을 수행해야 합니다.

목표는 단순합니다.

> 이번 달도 살아남는 것.

## 실행 방법

로컬에서 `index.html`을 브라우저로 열면 됩니다.

GitHub Pages에 올릴 경우 이 ZIP을 풀고, 폴더 안의 파일을 저장소 루트에 업로드하세요. 그 다음 GitHub 저장소의 **Settings → Pages → Deploy from a branch → main / root**를 선택하면 됩니다.

## 현재 구조

```text
.
├── index.html
├── assets/
├── docs/
├── prompts/
├── AI_HANDOFF.md
├── CHANGELOG.md
├── DECISIONS.md
├── BUGS.md
├── README.md
├── VERSION.txt
├── .nojekyll
├── .gitattributes
└── .gitignore
```

## 현재 구현

- HTML/CSS/JavaScript 단일 파일 게임
- 별도 빌드 도구 없음
- GitHub Pages 배포 가능
- 저장은 브라우저 localStorage 사용
- 모바일 모달/이벤트창 스크롤 보정 적용

## 주의

이 ZIP 파일 자체를 저장소에 올리지 말고, 압축을 풀어서 나온 파일과 폴더를 업로드하세요.
