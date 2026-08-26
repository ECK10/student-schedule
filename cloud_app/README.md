# 온라인 학생 일정 관리

컴퓨터가 꺼져 있어도 휴대폰과 PC에서 같은 일정을 사용하기 위한 버전입니다.

## 구성

- Supabase Auth: 이메일/비밀번호 회원가입과 로그인
- Supabase Database: 사용자별 일정 저장
- Row Level Security: 로그인한 사용자 본인의 일정만 조회/수정/삭제
- 정적 웹앱: `cloud_app/index.html`

## 설정

1. Supabase에서 새 프로젝트를 만듭니다.
2. Supabase SQL Editor에서 프로젝트 루트의 `supabase_schema.sql` 내용을 실행합니다.
3. Supabase Project Settings > API에서 Project URL과 anon public key를 복사합니다.
4. `cloud_app/index.html`의 다음 두 값을 교체합니다.

```javascript
const SUPABASE_URL = "프로젝트 URL";
const SUPABASE_ANON_KEY = "anon public key";
```

5. `cloud_app` 폴더를 Cloudflare Pages, Netlify 또는 GitHub Pages에 배포합니다.

비밀번호는 앱이나 데이터베이스에 직접 저장하지 않습니다. Supabase Auth가 암호화된 인증 정보로 관리합니다.
