
---
title: "깃허브 자료올리기"
author: "Young Jae Kim"
date: '2022-03-19'
categories: 
- Development
- gitBlog
tags:
- Development
- gitBlog

---

# github 블로그에 공부 자료 올려보기

- [ ]  저번 시간에는 hexo를 통해 github 블로그를 만드는 법을 알아 보았는데요, 이번에는 블로그에 자료를 직접 올려보겠습니다.

- Notion 으로 작성한 공부일지를 올려보자 !!
    
    .
    
    # step 1) notion을 마크다운 형식으로 export 하기.
    
source/images/github_update_blog
![Untitled](/images/github_update_blog/Untitled.png)

- 그렇게 되면 아래의 그림과 같이 마크다운 파일과 image 파일이 나오게 됩니다

 

![Untitled](/images/github_update_blog/Untitled%201.png)

# step 2) export 한 파일들을 myblog(깃허브와 연동시켜준 로컬 파일) 로 옮겨 줍니다.

- 포스트 파일에 마크다운 파일을 넣어줍니다

![Untitled](/images/github_update_blog/Untitled%202.png)

- 이제 포스팅 해야하는 이미지 파일들은 images 파일을 만들어주어서 여기다 넣어줍니다.

 (hexo 개발자가 그렇게 하래요~) 

![Untitled](/images/github_update_blog/Untitled%203.png)

- images 파일에 notion의 이미지 파일을 넣어 줍니다.

![Untitled](/images/github_update_blog/Untitled%204.png)

- 파이참으로 들어간 이후로, 이미지의 경로를 설정하여줍니다.

      처음, 이미지 파일들이 저렇게 똑같은 글자로 되어있을 것 입니다. 

      이 글자들을 모두 images/make_blog/이미지 파일이름 

이렇게 지정해두어야 합니다 .  그렇다면 이렇게 하나하나 모두 바꿔주기 힘드니. 

같은 글자를 드래그 및 복사 해준다음에 

ctrl+f  

![Untitled](/images/github_update_blog/Untitled%205.png)

- replace all 로 경로를 모두 바꾸어줍니다.

![Untitled](/images/github_update_blog/Untitled%206.png)

# step3) 저번 포스팅과 같이 hexo server 로 확인해줍니다 .

  

- 그러면 저의 깃허브 블로그 사이트에 저번 노션 기록이 올라간 것을 확인 하실수 있습니다.

![Untitled](/images/github_update_blog/Untitled%207.png)

## step4)배포해주기

```bash
git add . 
git commit -m "update"
git push 

hexo generate --deploy
```

지금까지 한 파일들을 git으로 올려주고 배포를 시켜준다 . !!