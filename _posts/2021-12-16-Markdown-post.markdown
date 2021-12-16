---
layout: post
title:  "Markdown 알아보기"
description: Markdown을 쓰는 이유와 Markdown의 문법 알아보기
date:   2021-12-15 21:52:59 +0530
categories: Markdown
comments: true
---
마크업 언어(Markup language)는 태그 등을 이용해서 문서나 데이터 구조를 명기하는 언어의 한 가지입니다. Markdown은 일반 텍스트 기반의 마크업 언어이며 서식이 있는 문서를 작성하기 위해 사용합니다. 


일반 사람들에게 가장 익숙한 마크업 언어는 HTML일 것입니다. 간혹 인터넷을 쓰다보다보면 *.html* 로 끝나는 주소를 보신적이 있으실 것입니다. 인터넷 브라우저가 웹페이지의 구조를 알 수 있도록 태그를 통해서 웹페이지의 구조를 기술한 것이 HTML 문서입니다. HTML의 구조가 궁금하다면 웹브라우저의 어느곳에서나 'F12' 키를 눌러 확인해보실 수 있습니다.

![html_example](/html_example.png)


Markdown은 일반적인 마크업 언어보다 작성이 쉽다는 장점이 있습니다. 위의 HTML이 태그를 이용해서 구조를 명시한다면 Markdown은 특수기호만으로 서식을 넣을 수 있습니다.


예를들어 **강조체(bold)**는 `**bold**` 로 작성합니다. 

기울임체는 *기울임체(italic)*는 `*italic*` 로 작성합니다.

제목은 #으로 나타내며 #의 갯수를 최대 6개까지 하면서 크기를 조정할 수 있습니다.
# 제목
## 제목
### 제목
#### 제목
##### 제목
###### 제목

이 외에도 다양한 마크다운 문법이 존재합니다. `![html_example](/html_example.png)` 는 이미지를 삽입하기 위한 마크다운 문법입니다. 이런 식으로 코드를 표현할 때는 \`(코드)\`을 사용합니다.  \`\`\`(코드 블록)\`\`\` 으로 아래와 같이 코드 블록(code block)도 삽입할 수도 있습니다.

```javascript
const express = require('express')
const app = express()
 
app.get('/', function (req, res) {
  res.send('Hello World')
})
 
app.listen(3000)
```