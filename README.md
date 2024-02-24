# Github101

### 강의 순서 및 내용

#### 1. 소개 (5분)
- What is GitHub?
  - **Git:**
    - 분산 버전 관리 시스템(DVCS)으로, 코드 변경 사항 추적 및 여러 버전 관리 가능.
    - 로컬 컴퓨터에서 작동, 네트워크 연결 없이도 사용 가능.
    - 모든 사용자가 코드베이스 전체의 복사본을 보유, 시스템 문제 발생 시 다른 사용자의 복사본으로 복구 가능.

  - **GitHub:**
    - Git 기반의 온라인 코드 호스팅 서비스.
    - 웹 인터페이스를 통해 코드 저장 및 공유, 협업 도구(코드 리뷰, 이슈 트래킹, 프로젝트 관리 등) 제공.
    - 개발자들이 전 세계 어디서든 협업할 수 있는 플랫폼.

- GitHub의 중요성과 사용 사유
  - **코드 공유 및 협업:**
    - 개발자들이 코드를 쉽게 공유하고, 문제 해결 및 지식 공유를 통해 프로젝트 효율성 향상.
    
  - **기타 사유:**
    - 오픈 소스 프로젝트 기여, 개발자 포트폴리오 구축, 글로벌 커뮤니티
    
#### 2. GitHub 기본 개념 (10분)
- Repository 설명: 저장소의 개념과 용도.
- Branches: 주요 브랜치(master/main)와 기능 브랜치의 개념.
- Commits: 변경 사항을 저장하는 방법과 커밋 메시지의 중요성.
- Pull Requests: 기능 개발이 완료되었을 때 메인 브랜치로의 병합 요청.
- Merge: Pull request의 병합 과정 설명.

#### 3. GitHub 시작하기 (10분)
- GitHub 계정 SSH keys
  - `ssh-keygen`
- 새로운 repository 생성 및 설정(예: .gitignore 파일).
  - `git config --global user.name "your_username"`
  - `git config --global user.email "your_email@example.com"`
- Git 설치 및 GitHub에 연결하기: Git 설치, Git과 GitHub 계정 연동하기.
  - https://git-scm.com/

#### 4. Git 기본 명령어 (15분)
- `git clone`: GitHub 저장소 복제하기.
- `git branch`: 브랜치 생성 및 전환하기.
- `git status`: 현재 상태 확인하기.
- `git add`: 변경 사항 스테이징하기.
- `git commit`: 변경 사항 커밋하기.
- `git push`: GitHub에 변경 사항 푸시하기.
- `git pull`: GitHub에서 최신 변경 사항 가져오기.
- 예제 코드
```base
# GitHub 저장소 복제하기
git clone https://github.com/username/repository-name.git

# 브랜치 생성하기 (new-branch-name을 원하는 브랜치 이름으로 대체)
git branch new-branch-name

# 다른 브랜치로 전환하기 (branch-name을 원하는 브랜치 이름으로 대체)
git checkout branch-name

# 새로운 브랜치를 생성하고 해당 브랜치로 전환하기 (한 번의 명령어로)
git checkout -b new-branch-name

# 현재 상태 확인하기
git status

# 변경 사항 스테이징하기 (특정 파일)
git add filename.txt

# 모든 변경 사항 스테이징하기
git add .

# 변경 사항 커밋하기 (commit-message를 실제 커밋 메시지로 대체)
git commit -m "commit message"

# GitHub에 변경 사항 푸시하기 (branch-name을 현재 작업 중인 브랜치 이름으로 대체)
git push origin branch-name

# GitHub에서 최신 변경 사항 가져오기 (현재 브랜치에 대해)
git pull origin branch-name
```

#### 5. 협업을 위한 GitHub 사용 (10분)
- Fork: 다른 사용자의 저장소 복제하기.
- Pull Request 생성 및 관리: 기여 과정 설명.
- 이슈(Issues) 사용하기: 프로젝트의 문제나 토론을 위한 이슈 사용 방법.

#### 6. 좋은 커밋 메시지 작성하기 (5분)
  - **Be Clear and Concise:**
    - Summarize the change accurately without unnecessary details.
  
  - **Separate Subject from Body:**
    - Use a blank line to separate the subject (title) from the body (description).
    - Limit the subject to 50 characters.
    - Wrap the body at 72 characters.
  
  - **Use Imperative Mood in Subject:**
    - Start the subject line with an imperative verb like "Fix", "Add", "Change".
  
  - **Explain Why and What in the Body:**
    - Describe why the change was made and what it entails.
    - Mention any side effects or implications.
  
  - **Maintain Consistency:**
    - Stick to a consistent commit message format within the project.
  
  - **Include Issue Tracker IDs:**
    - Reference related issue tracker IDs for additional context.

#### 7. Q&A ?


## 고급 주제

### GitHub의 고급 기능
GitHub Actions, GitHub Pages, Projects 등

### Git Rebase (5-10분)

#### Git Rebase란?
- `git rebase`의 기본 개념 설명: 브랜치의 기준(base)을 다른 커밋으로 옮기는 것으로, 커밋 히스토리를 깔끔하게 정리할 수 있습니다.
- **Merge**와의 차이점 강조: `merge`는 두 브랜치의 변경 사항을 합치지만, `rebase`는 한 브랜치의 커밋을 다른 브랜치 위에 "재배치"합니다. 이는 히스토리를 선형적으로 만들어 가독성을 높이는 장점이 있습니다.

#### Rebase 사용 시기
- 기능 개발을 진행하는 동안 메인 브랜치(main/master)에서 발생한 새로운 변경 사항을 현재 작업 중인 브랜치에 적용하고 싶을 때.
- Pull Request를 보내기 전에 커밋 히스토리를 정리하고 싶을 때.

#### Rebase 실습
- 기본적인 `git rebase` 명령어 사용법: `git rebase <base-branch>`
- 충돌(conflict) 해결 방법: rebase 과정에서 충돌이 발생할 수 있으며, 이를 수동으로 해결하는 방법 설명.
- 안전하게 rebase하기: `git rebase --abort`를 사용해 rebase를 중단하고 원래 상태로 돌아가는 방법.

#### 주의사항
- 이미 공개된(public) 브랜치에서는 `rebase`를 사용하지 않는 것이 좋습니다. 이는 다른 사람이 해당 브랜치의 이력을 기반으로 작업을 하고 있을 수 있기 때문에 혼란을 야기할 수 있습니다.

`git rebase`에 대한 강의를 추가함으로써, 참가자들은 Git의 보다 고급 기능을 이해하고, 실제 프로젝트에서 보다 효율적으로 협업할 수 있는 능력을 개발할 수 있습니다. 다만, 이 주제는 시간 관계상 간략하게 다루되, 실습과 예제를 통해 참가자들이 충분히 이해할 수 있도록 하는 것이 중요합니다.
