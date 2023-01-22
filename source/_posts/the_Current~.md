---
title: "The current branch master has no upstream branch"
author: "Young Jae Kim"
date: '2023-01-23'
output:
  html_document:
    keep_md: true
categories:
- Development
- git_error
tags:
- Machinelearning
- git_error


---

# The current branch master has no upstream branch.

![Untitled](images/the_Current~/0.png)

- 오류의 원인은 처음 만들고 원격 저장소에 대한 기본 브랜치를 설정을 안 해주었기 때문에 생기는 오류 .

<span style="background-color:yellow">$ git push —set-upstream origin main </span>

- 이 코드를 통해 기본 브랜치를 main 으로 설정해준 뒤 push 를 하면 오류가 생겨난다.