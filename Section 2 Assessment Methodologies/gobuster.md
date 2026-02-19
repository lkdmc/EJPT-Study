
### `gobuster`
- **디렉토리/파일을 무차별 대입으로 찾아주는 도구**
- 사전에 있는 단어들을 URL에 하나씩 붙여서 존재하는지 확인해요

---

### `dir`
- **디렉토리 탐색 모드**
- gobuster에는 여러 모드가 있어요
```
dir  → 디렉토리/파일 탐색
dns  → 서브도메인 탐색
vhost → 가상호스트 탐색
```

---

### `-u http://target.ine.local`
- **u = URL** (타겟 주소)
- 어떤 사이트를 탐색할지 지정

---

### `-w /usr/share/wordlists/dirb/common.txt`
- **w = wordlist** (단어 목록 파일)
- 이 파일 안에 있는 단어들을 URL 뒤에 붙여서 시도해요
```
http://target.ine.local/admin
http://target.ine.local/login
http://target.ine.local/uploads
http://target.ine.local/backup
... (수천개)
```

---