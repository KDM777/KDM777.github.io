---
title: "다른 컴퓨터로 레포지토리 내용 변경"
excerpt: " "

categories:
  - Categories5
tags:
  - [git]

permalink: /git/change-repository-content/

toc: true
toc_sticky: true

date: 2025-01-20
last_modified_at: 2025-01-20
---

## 🦥 본문

로컬과 깃허브를 연동하여 commit할 내용이 있다면 commit 후 push를 하는 것을 알았으나 만약 다른 컴퓨터에서 작업을 하고 commit -> push를 할려면 어떻게 해야하는가를 알게 되었다. 

먼저 그 컴퓨터가 내 깃허브 계정으로 로그인이 되어 있지 않았다. 확인할 수 있는 명령어는 다음과 같다.

> 
git config user.name
git config user.email


이것을 변경하는 코드는
> git config --global user.name 이름
git config --global user.email 로그인할 이메일

모두 git bash에서 하였다.
![git_img](assets/images/posts_img/git-change-repository-content/git_img.png)

그러면 
![git_img2](assets/images/posts_img/git-change-repository-content/git_img2.png)
이렇게 바뀌는 것을 확인할 수 있다.

계정을 바꾼 후 원래 목적인 다른 컴퓨터에서 작업을 했을 때 내 레포지토리에 저장하는 방법이다
1. git clone 깃허브 주소
![git_clone](assets/images/posts_img/git-change-repository-content/git_clone.png)
2. 폴더 이동 후 상태 확인
![git_status](assets/images/posts_img/git-change-repository-content/git_status.png)
보시다시피 에러가 발생했다. 
> On branch main
Your branch is up to date with 'origin/main'.
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        hw4/
nothing added to commit but untracked files present (use "git add" to track)
  
 이런 에러 인데 
  ![git_error](assets/images/posts_img/git-change-repository-content/git_error.png)
요 방식으로 해결하고 push를 성공적으로 마쳤다.
  ![git_status](assets/images/posts_img/git-change-repository-content/git_status.png)
추가가 되었다