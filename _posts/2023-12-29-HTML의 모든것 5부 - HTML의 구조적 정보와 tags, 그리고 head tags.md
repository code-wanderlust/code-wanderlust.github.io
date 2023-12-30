---
title: HTML의 모든것 5부 - HTML의 구조적 정보와 tags, 그리고 head tags
date: 2023-12-30 20:24:30 +0900
categories: [Web, HTML]
tags: [web, html, frontend]     # TAG names should always be lowercase
published: true
---

> HTML관련 마지막 포스팅으로, HTML의 구조와 관련된 tag들과 layout, 그리고 기타 여러가지 tag들에 대해 다루어 보려고 한다. 


## 1. HTML 영역분할
### 1-1. \<div\>와 \<span\> tag
영역분할에는 ```<div></div>```와 ```<span></span>```tag가 있습니다. 
```<div></div>```는 division의 약자로 여러 element들을 다른 element들과 구분시켜주는 태그 입니다. 
해당 태그를 적용하면, 시각적으로는 큰 변화가 없지만, 추후 ```css```등을 통해 html에 스타일을 할당시킬때 ```<div></div>```에 따라 다르게 부여해 줄 수 있다. 
즉, web page의 구조를 디자인할때 필요로 하는 tag이다. 
```<span></span>```는 특정 text를 구분할때 사용하는 tag이다. 
역시 해당 tag를 부여하여도, 특별한 변화는 없지만, 스타일을 부여할때 사용된다. 
아래는 예시 html 입니다. 

```html
<!DOCTYPE html>
<html>
    <head>
        <title>My website</title>
    </head>
    <body>
        <div>
        <ol>
            <li>Coffee</li>
            <li>Tea</li>
            <li>Milk</li>
        </ol>
        <ul>
            <li>Apple</li>
            <li>Banana</li>
            <li>Melon</li>
        </ul>
        </div>

        <h1>1. h1 제목</h1>
        <p>안녕하세요? <span>저의</span> 홈페이지에 와주셔서 감사합니다. </p>
        <p>오늘도 좋은 하루 보내셔요.</p>
    </body>
</html>
```

### 1-2. Block과 Inline 형식.
여기서, ```block```과 ```inline```이라는 형식을 알아야 합니다. 
이는 앞서 소개해 드렸던 다양한 tag들은 ```block```또는 ```inline```형식을 통해 web page에서 특정 영역을 어떻게 차지하게 될지 결정이 됩니다. 
```block```형식은 위에서 아래로 차근차근 영역을 차지하면서 배치가 됩니다. 즉, 자동으로 줄바꿈이 되며, web page의 전체폭을 사용합니다. 
```block```형식을 사용하는 tag들에는 ```<h>```, ```<p>```, ```<div>```등이 있습니다. 
반면, ```inline```형식은 가로방향으로 배치되는 형태를 따릅니다. 일렬로 배치되며, 폭이 지정되어 있습니다. 
```inline```형식을 따르는 tag로는 ```<img>```, ```<input>```, ```<span>```등이 있습니다. 

### 1-3. Web Page의 layout
처음 소개하였듯이, web page는 layout이 어느정도 정해져 있는데, 보통 각 영역을 ```<div></div>```tag를 이용합니다. 

```html
<!DOCTYPE html>
<html>
    <head>
        <title>My website</title>
    </head>
    <body>
        <div>Header Area</div>
        <div>Navigation Area</div>
        <div>Sidebar Area</div>
        <div>Main Area</div>
        <div>Footer Area</div>
    </body>
</html>
```

물론, 각 영역을 구분하기 위해서는 ```id```와 같은 attribute를 이용하여 구분을 해줘야 합니다. 
그런데, 이러한 구성을 너무 많이 사용하다보니, HTML5에서는 위의 역할을 하는 tag들을 아애 따로 만들어 버렸습니다. 
그 내용은 아래와 같습니다. 

```html
<!DOCTYPE html>
<html>
    <head>
        <title>My website</title>
    </head>
    <body>
        <header>Header Area</header>
        <nav>Navigation Area</nav>
        <aside>Sidebar Area</aside>
        <main>Main Area</main>
        <footer>Footer Area</footer>
    </body>
</html>
```

```<header></header>```, ```<nav></nav>```, ```<aside></aside>```, ```<main></main>```, ```<footer></footer>``` tag을 통해 구분을 할 수 있습니다. 
실질적인 역할은 ```<div></div>``` tag와 동일하지만, 의미를 부여했다는 점에서, 특별히 **semantic tag**라고 부릅니다. 



## 2. HTML \<head>에 들어갈 tag들

HTML의 ```<head></head>```부분에는 ```<title></title>```, ```<style></style>```, ```<link>```, ```<script></script>```, ```<meta>```, ```<base>```와 같은 tag들을 사용할 수 있습니다. 
이들 tag들은 web browser상에 뭔가 보여주기 위해 사용하는 tag는 아니고, web page자체의 정보를 표시하기 위해 사용하는 tag들 입니다. 


1. ```<title></title>``` : Web browser의 tab에 띄울 제목을 작성할 수 있습니다. 
2. ```<style></style>``` : Web page의 style과 관련된 tag로 ```css```와 밀접한 관계가 있습니다. 해당 tag를 이용하면, 아래와 같이 스타일을 직접 적어줄 수도 있습니다. 아래의 내용은 ```<head></head>```태그안에 넣어두면 된다. 
```
<style>
    h1 {color: blue;}
    p {color: red;}
</style>
```

3. ```<link>``` : 필요한 파일들을 연결시켜주는 tag로, ```css```파일을 불러올때나, 아이콘등을 볼러올 수 있습니다. 불러올 파일을 어떠한 용도로 사용할지는 relation의 약자로 ```rel```이라는 attribute를 이용하여 정해줘야 합니다. 
```html
<head>
    <link rel="stylesheet", href="somewhere/css_path/style.css">
    <link rel="icon", href="somewhere/icon_path/icon.jpg">
</head>
```

4. ```<script></script>``` : 해당 tag에서 ```Javascript```code를 작성할 수 있습니다. 만약, 따로 ```Javascript```코드가 ```.js``` 파일로 저장되어 있다면, ```<script src="somewhere/javascript_code.code.js"></script>```을 이용하여 해당 파일을 불러와서 사용할 수 있다. 
```html
<head>
    <script>
        function Myfunction(){
            // Something Here.
        }
    </script>
</head>
```

5. ```<meta>``` : Web page에 대한 여러가지 설명을 적어둘 수 있습니다. 가령 ```name``` attribute를 선언하고, 해당하는 값으로 ```"description"```, ```"keywords"```, ```"author"```등을 지정할 수 있습니다. 이러한 정보는 사용자가 이용하는 것은 아니고, web browser나, 여러 검색엔진들이 참고하여 활용할 수 있는 요소들 입니다. 
```html
<head>
    <meta name="description" content="테스트 페이지 입니다.">
    <meta name="keywords" content="테스트, 연습, html">
    <meta name="author" content="Someone">
</head>
```

6. ```<base>``` : 경로에 대한 기준을 정해두는 tag입니다. 만약 기준 경로를 ```assests/```로 정하였다면, ```<body></body>```안에 있는 모든 경로들은 ```assets/```아래에 있는 경로들을 기준으로 하여 결정되게 됩니다. 또한 ```target``` attribute도 설정 가능하기 때문에, ```<body></body>```안에 있는 모든 곳에 적용시킬 수 있습니다. Tag는 ```<base href="images/" target="_blank"> ``` 과 같이 작성하면 된다. 


## 3. HTML관련 기타사항

1. 주석을 넣는 방법: html 문서 내에서 ```<!-- 이곳에 필요한 주석을 넣어주세요 -->``` 를 통해 주석을 넣어줄 수 있습니다. 
2. empty tag들도 사실은 end tag를 넣어줄 수 있습니다. 또한, 특별히 끝에 ```/```을 넣어주는 방식으로 end tag를 표시해 줄 수도 있습니다. 가령, ```<br />```과 같이 사용할 수 있습니다. 
3. Web page에 가로줄을 넣어줄 수도 있는데, horizontal rule의 약자인 ```<hr />``` tag를 사용합니다. 
4. 다양한 text관련 tag들이 있습니다. 
    - ```<b></b>``` <b>bold를 의미합니다.</b>
    - ```<strong></strong>``` <strong>도 bold를 의미합니다. </strong>
    - ```<i></i>``` <i>이텔릭체로 표시해줍니다. </i>
    - ```<em></em>``` <em>텍스트를 강조해 줍니다.</em>
    - ```<mark></mark>``` <mark>텍스트에 highlighting을 해줍니다. </mark>
    - ```<small></small>``` <small>텍스트를 작게해줍니다. </small>
    - ```<del></del>``` <del>텍스트에 취소선을 그어줍니다. </del>
    - ```<ins></ins>``` <ins>텍스트에 밑줄을 그어줍니다. </ins>
    - ```<sub></sub>``` 아래첨자 <sub>텍스트를 입력할</sub> 수 있게 해줍니다. 
    - ```<sup></sup>``` 윗첨자 <sup>텍스트를 입력할</sup> 수 있게 해줍니다. 
    - ```<code></code>``` <code>Code관련 글씨체로</code> 바꿔줍니다. 
    - ```<kbd></kbd>``` <kbd>키보드 글씨체로</kbd> 바꿔줍니다. 
5. ```<p>```tag에서 character entity를 사용해야 <kbd>enter</kbd>, <kbd>space</kbd>가 먹혔었는데, preformatted의 약자인 ```<pre></pre>```테그를 사용하면, 문제를 해결할 수 있습니다. 



> HTML 시리즈
> 1. [HTML의 모든것 1부 - HTML이란 무엇인가](https://code-wanderlust.github.io/posts/HTML의-모든것-1부-HTML이란-무엇인가/)
> 2. [HTML의 모든것 2부 - HTML의 제목, 본문 단락, 목록, 표 태그들](https://code-wanderlust.github.io/posts/HTML의-모든것-2부-HTML-내용-tags/)
> 3. [HTML의 모든것 3부 - HTML의 Media (이미지, 오디오, 비디오) tags](https://code-wanderlust.github.io/posts/HTML의-모든것-3부-HTML의-Media-(이미지,-오디오,-비디오)-tags/)
> 4. [HTML의 모든것 4부 - HTML의 하이퍼링크, 입력 tags](https://code-wanderlust.github.io/posts/HTML의-모든것-4부-HTML의-하이퍼링크,-입력-tags/)
> 5. [HTML의 모든것 5부 - HTML의 구조적 정보와 tags, 그리고 head tags](https://code-wanderlust.github.io/posts/HTML의-모든것-5부-HTML의-구조적-정보와-tags,-그리고-head-tags/)