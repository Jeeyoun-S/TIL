- **Repository**
    
    특정 디렉토리를 버전 관리하는 저장소 (폴더를 기준으로 버전 관리)
    
    - `git init` 명령어로 로컬 저장소 생성
    - .git 디렉토리에 버전 관리에 필요한 모든 것이 들어있다.
- **Commit(커밋)**
    
    특정 버전으로 남긴다 = “커밋(Commit)한다”
    
    커밋(Commit)은 3가지 영역을 바탕으로 동작!
    
    - Working Directory *untracked(아직 버전 관리X, 최소의 상태)*
        
        내가 작업하고 있는 실제 디렉토리
        
    - Staging Area *staged, tracked*
        
        `git add`로 변경 사항을 Working → Staging으로
        
        커밋으로 남기고 싶은, 특정 버전으로 관리하고 싶은 파일이 있는 곳
        
        - **중간에 Staging Area를 거쳐야 하는 이유?**
            
            특정 변경사항만 저장하고 싶어서, 모든 변경사항 저장X
            
    - Repository *tracked, committed*
        
        `git commit`으로 커밋을 만든다. Staging → Repository
        
        커밋들이 저장되는 곳 (.git 디렉토리를 가리킨다)
        
        수정할 때 *modified, tracked* 상태로 Repository → Working로
        
- **Commit 문법**
    - `git status` 현재 git으로 관리되고 있는 파일들의 상태
    - `git config --global user.email "you@example.com"`
    - `git config --global user.name "Your Name"`
    - `git log` **git의 commit 히스토리
        
        ![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/eaad7004-7a2b-40fc-8abb-bc0b629d745e/Untitled.png)
        
    - `git diff **ID_A ID_B` commit 비교→ 순서에 따라 기준이 달라진다. A가 기준.
        
        ![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/37a353cf-bbae-4ac3-84dd-f6d2dde4cace/Untitled.png)
        
- **Commit 생성하기**
    1. *readme.md* 파일 `git add .` 후 `git commit` **하기
        
        ![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/5f743094-64c8-4efe-a906-bb7f1853c84b/Untitled.png)
        
    2. `git commit`과 `git commit -m “(file_name)”`
        
        ![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/c1b1e359-a560-4f8b-9649-375a8ace5286/Untitled.png)
        
        ![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/f055660b-b3a6-4b81-a458-f50c66dd4dfb/Untitled.png)
        
    3. *readme.md*에 한 줄 더한 뒤 커밋 재생성
        
        ![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/8a5de800-2713-48e9-91f9-10cab2c1a2f8/Untitled.png)
        
    4. `git commit -m “update”`
    
- **Git Commit 실습**
    1. 바탕화면에 *edu_git_commit* 폴더를 만들고 git 저장소 생성
    2. *a.txt* 파일 만들고, `add a.txt`라는 커밋메세지로 커밋 만들기
    3. *b.txt* 파일 만들고, `add b.txt`라는 커밋메세지로 커밋 만들기
        
        ![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/ab1aefe0-4063-45f2-b274-f6d91767eaba/Untitled.png)
        
    4. a.txt 파일 수정하고, `update a.txt`라는 커밋메세지로 커밋 만들기
        
        ![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/139a55b2-f92e-49b5-8861-75303451bc92/Untitled.png)
        
- **Local → Remote Repository 연결**
    
    지금까지 Local Repository에서만 작업, GitHub와 연동X
    
    - `git remote add origin remote_repo`
        
        ![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/b611ccd0-6345-43ef-adab-5b75072dea9b/Untitled.png)
        
    - `git push -u origin master`
    - `git push A(어디로) B(branch)`
        
        ![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/b2fb64f9-6971-430c-a70e-1248d9184a45/Untitled.png)
        
    - `git push -u origin master`
        - 실행 후 `git push`만 해도 `git push origin master`로
    - *readme.md* 파일 수정 후 다시 push하기
        
        ![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/b6d96ca1-bbcb-4dd9-b0dc-ba1e757453bb/Untitled.png)
        
- **Remote → Local Repository 연결**
    - `git clone remote_repo` Remote repo를 local로 복사
    - ↔ `git push origin master` Local repo의 최신 커밋을 Remote repo로 push합니다.
    - *past.py* 파일 만든 뒤, Commit 및 Push하기
        ![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/8f438b3a-5cfe-43e1-9dcf-6670b1fb2d6c/Untitled.png)