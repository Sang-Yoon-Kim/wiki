# Wiki Setup Guide

## Vault 정보

- 경로: `~/git/wiki`
- Git remote: `git@github.com:Sang-Yoon-Kim/wiki.git`
- 동기화: obsidian-git (백업) + Self-hosted LiveSync (실시간 싱크)

---

## 새 기기에서 시작하기

### 1. 레포 클론

```bash
git clone git@github.com:Sang-Yoon-Kim/wiki.git ~/git/wiki
```

### 2. 플러그인 수동 설치

Obsidian Community plugin store를 거치지 않고 직접 설치한다.

```bash
# obsidian-git
mkdir -p ~/git/wiki/.obsidian/plugins/obsidian-git
cd ~/git/wiki/.obsidian/plugins/obsidian-git
curl -sL "https://github.com/Vinzent03/obsidian-git/releases/latest/download/main.js" -o main.js
curl -sL "https://github.com/Vinzent03/obsidian-git/releases/latest/download/manifest.json" -o manifest.json
curl -sL "https://github.com/Vinzent03/obsidian-git/releases/latest/download/styles.css" -o styles.css

# Self-hosted LiveSync
mkdir -p ~/git/wiki/.obsidian/plugins/obsidian-livesync
cd ~/git/wiki/.obsidian/plugins/obsidian-livesync
curl -sL "https://github.com/vrtmrz/obsidian-livesync/releases/latest/download/main.js" -o main.js
curl -sL "https://github.com/vrtmrz/obsidian-livesync/releases/latest/download/manifest.json" -o manifest.json
curl -sL "https://github.com/vrtmrz/obsidian-livesync/releases/latest/download/styles.css" -o styles.css
```

### 3. Obsidian에서 Vault 열기

Obsidian 좌하단 vault 아이콘 → **Open folder as vault** → `~/git/wiki` 선택

### 4. Community Plugins 활성화

설정(⚙️) → Community plugins → **Restricted mode 해제** → Git, Self-hosted LiveSync Enable

---

## 플러그인 설정

### obsidian-git

| 항목 | 값 |
|------|-----|
| Auto backup | ON |
| Auto push | OFF |
| Auto pull | OFF |
| Commit message | `auto: {{date}}` |

수동 push: Command Palette → `Git: Push`

### Self-hosted LiveSync

→ [[LiveSync-Setup]] 참고 (Cloudflare D1 백엔드 설정 포함)

---

## 폴더 구조 (PARA)

```
wiki/
├── Projects/     # 현재 진행 중인 작업
├── Areas/        # 지속 관리 영역 (AI, Robotics, Software, Hardware)
├── Resources/    # 주제별 참고 자료
├── Archive/      # 완료/보관
└── Setup.md      # 이 파일
```
