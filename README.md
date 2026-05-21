# claim-page

구매자가 주문번호 + 이메일을 입력해 라이센스키를 발급받는 단일 페이지.

## 배포 (GitHub Pages, 무료, 신용카드 X)

1. GitHub에 신규 public 또는 private repo 생성 (예: `nano-claim`)
2. `claim-page/` 안의 모든 파일을 repo 루트에 푸시
3. `config.js`의 `LICENSE_API_BASE`를 본인의 Deno Deploy URL로 교체
4. GitHub repo Settings > Pages > Source: `Deploy from a branch` → `main` / `/(root)` 선택
5. 1~2분 뒤 `https://<username>.github.io/nano-claim/` 가 발급됨
6. 크몽 자동 응답 메시지에 이 URL을 박아둠

## 로컬 미리보기

```bash
# 어떤 정적 서버든 OK
npx http-server claim-page -p 8000
# 또는 Python
python -m http.server 8000 --directory claim-page
```

## CORS 주의

Deno Deploy 서버는 `Access-Control-Allow-Origin: *`를 반환하므로
GitHub Pages 도메인에서도 정상 동작.
