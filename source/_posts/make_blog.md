---
title: "깃 블로그와 연동하기"
author: "Young Jae Kim"
date: '2022-03-16'
categories: 
- Development
- gitBlog
tags:
- Development
- gitBlog
---



# 깃허브 블로그 만들기

## 1.깃과 로컬 연동시켜주기

- 1.마우스 우클릭으로 git bash 를 열어주고, hexo 파일을 만들어준다

```bash
hexo init youngjae 

```

이 이후에  깃허브에 들어가서 youngjae 와 이름이 같은 레퍼지토리를 만들어 줍니다. 

- 2.이제 로컬의 youngjae와 git의 youngjae 를 연동시켜 주어야 합니다. 로컬에 있는 my blog를 파이참으로 실행 시켜 줍니다.

![Untitled](/images/make_blog/Untitled.png)

- 파이참으로 실행시킨뒤 필요한 패키지를 깔아줍니다

        $ npm install

   $ npm install hexo-server --save

   $ npm install hexo-deployer-git --save

- 이제 명령창에 이 명령어들을 복사,붙여넣기를 해줍니다.

![Untitled](/images/make_blog/Untitled%201.png)

- 그러면 창이 이렇게 변하게 됩니다!!

![Untitled](/images/make_blog/Untitled%202.png)

이제 그러면 로컬에 있는 youngjae 폴더의 모든 파일들을 깃허브에 연동하여 업로드 해 보겠습니다

 

```bash
git add .   # 모든 파일을 업로드 한다
git commit -m "upload" 
git push    #이제 다 준비 되었으니 다 올려라 !! 
```

![Untitled](/images/make_blog/Untitled%203.png)

 그러면 이렇게 깃허브와 연동되어 로컬에 있는 모든 파일이 올라가게 됩니다 !! 

## 2.hexo 로 웹페이지 만들기

- cosfig.yml 로 들어가서 tilte 도 조정을 해주고, url도 조정을 해줍니다.

![Untitled](/images/make_blog/Untitled%204.png)

![Untitled](/images/make_blog/Untitled%205.png)

- 한번 홈페이지를 로컬에서 열어주어 볼까요? hexo generate  와 hexo server 명령어를 쳐줍니다. 웹을 생성해주고 서버로 url 로 넘어갈수 있는 명령어에요!!

![Untitled](/images/make_blog/Untitled%206.png)

![Untitled](/images/make_blog/Untitled%207.png)

이렇게 웹사이트가 생성 되었네요 !! 이제는 이것을 git으로 연동해 배포해주겠습니다.  

맨 아래 Deployment 부분에 이렇게 바꾸어줍니다

![Untitled](/images/make_blog/Untitled%208.png)

- 여기서 !! 깃허브 레퍼지토리에 `[kimyoungjae777.github.io](http://kimyoungjae777.github.io)` 이름으로 된 레퍼지토리를 새로 만들어줍니다. 여기에 연동을 시켜줄 거니까요!!

- hexo generate 로 웹을 생성시켜주고 hexo deploy 로 배포를 해줍니다.

![Untitled](/images/make_blog/Untitled%209.png)

![Untitled](/images/make_blog/Untitled%2010.png)

- 이렇게 되면, 웹페이지가 배포 되면서 커뮤니케이션을 할 수 있게 됩니다.

![Untitled](/images/make_blog/Untitled%2011.png)

![Untitled](/images/make_blog/Untitled%2012.png)

## 3.웹의 테마 설정하기 (이카루스)

- 이카루스 테마를 설정하기 위해 이카루스 깔기

![Untitled](/images/make_blog/Untitled%2013.png)

- 테마 바꿔 주기.

![Untitled](/images/make_blog/Untitled%2014.png)

![Untitled](/images/make_blog/Untitled%2015.png)

하지만 에러가 발생하였다..

에러 해결!!

![Untitled](/images/make_blog/Untitled%2016.png)

- 이렇게 테마가 바뀐것을 볼 수가 있다. !!

![Untitled](/images/make_blog/Untitled%2017.png)