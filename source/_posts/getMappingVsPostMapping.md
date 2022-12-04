---
title: "PostMapping_vs_GetMapping"
author: "Young Jae Kim"
date: '2022-12-04'
output:
  html_document:
    keep_md: true
categories: 
- Development
- 기본개념
tags:
- Development
- 기본개념

---

# GetMapping,PostMapping

### GET 방식: 어떠한 정보를 가져와서 조회하기 위해 사용되는 방식

- **URL에 변수를 포함시켜 요청**한다.
- 데이터를 header를 포함하여 전송한다.
- url에 데이터가 노출되어 **보안에 취약하다.**
- 캐싱이 가능하다. (캐싱:한번 접근후, 똑같은 요청을 할 시 빠르게 접근하기 위해 레지스터에 데이터를 저장시키는것)

### post 방식: 데이터를 서버로 제출하여 추가 또는 수정하기 위해서 데이터를 전송하는 방식

- URL에 변수에 변수를 노출하지 않고 요청을 한다.
- 데이터를 body에 포함시킨다.
- url에 데이터가 노출되지 않아서 기본 보안이 설정되어 있다.
- 전송하는데 길이 제한이 없다
- 캐싱이 불가능하다