---
title: CSS의 모든 것 1부 - CSS란? 간단한 사용법과 선택자
date: 2024-01-06 19:54:40 +0900
categories: [Web, CSS]
tags: [web, html, frontend]     # TAG names should always be lowercase
published: true
---

> CSS는 HTML에 멋진 스타일을 할당하기 위한 필수적인 요소 입니다. 
> HTML을 배우고 나서 바로 배우면 아주 좋습니다. 
> 본 포스팅 시리즈에서는 CSS와 관련해 공부하고 정리한 내용을 적어두려고 합니다. 

## 1. Web문서에 스타일을 부여하는 방법과 CSS
Cascading Style Sheet(CSS)는 Web 문서에 스타일을 부여하는 언어 입니다. 
이러한 CSS정보를 web 문서에 부여하는 방법에는 **inline**, **internal**, **external**로 3가지 방법이 있습니다. 

### 1.1 Inline 방법
먼저 inline은 html에서 사용하는 tag에 style이라는 attribute를 선언하여, 적절한 property를 할당하는 방법 이다. 
아래는 inline 방식의 예시 이다. 
```html
    <!DOCTYPE html>
    <html>
        <head>
            <title>My CSS website</title>
        </head>
        <body>
            <h1>Welcome!</h1>
            <p style="color:red">Hi, Thank you so much for visiting my website.</p>
        </body>
    </html>
```
위 예시를 보면, ```<p style="color:red">```부분이 있는데, 이 부분이 inline 방식으로 style을 부여한 것 입니다. 

### 1.2 Internal 방법
Inline 방법은 tag마다 스타일을 정해줘야 하는데, 이는 손이 너무 많이 가는 방법입니다. 
그래서, 사전에 tag에 어떠한 style을 사용할지 정해줄 수 있는데, 이러한 방법이 internal 방법 이다. 

```html
    <!DOCTYPE html>
    <html>
        <head>
            <title>My CSS website</title>
            <style>
                p {color:red;}
            </style>
        </head>
        <body>
            <h1>Welcome!</h1>
            <p>Hi, Thank you so much for visiting my website.</p>
        </body>
    </html>
```

위와 같이 ```<head></head>```부분에, ```<style></style>```을 선언하고, 적절한 style을 정해두면, ```<p></p>```에 해당하는 부분은 모두 스타일이 적용된다. 

### 1.3 External 방법
만약, 여러 web 문서에 공통적으로 적용될 style을 적용하고 싶으면, 따로 style sheet를 작성하여, html에서 이를 불러와서 사용하게 하면 된다. 
Style sheet는 ```.css``` 확장자로 저장을 하고, 해당 파일에 style과 관련된 정보를 저장해둔다. 
Html 파일에서 ```css```파일을 불러오는 방법은 ```<link>```tag를 이용하는 방법이다. 
이러한 접근 방식을 external방식이라 합니다. 
아래는 간단한 예제 코드 입니다. 

```css
    p{
        color: red;
    }
```

```html
    <!DOCTYPE html>
    <html>
        <head>
            <title>My CSS website</title>
            <style>
                p {color:red;}
            </style>
            <link rel="stylesheet" href="somewhere/style.css">
        </head>
        <body>
            <h1>Welcome!</h1>
            <p>Hi, Thank you so much for visiting my website.</p>
        </body>
    </html>
```

위의 세가지 방식을 하나의 html 파일에 동시에 적용할 수도 있습니다. 하지만 우선순위가 정해져 있습니다. 
먼저 세가지 방법 중 **우선순위가 가장 높은 것은 ```inline```방식** 이다. 
그 후에 internal 방식 또는 external 방식 둘 중 하나가 적용이 되는데, 둘중에서 나중에 선언되는 것으로 적용이 됩니다. 
가령 위의 예시에서, ```<p></p>```tag는 external 방식으로 style이 적용될 것 입니다. 
우선순위가 잘 기억이 나지 않는다면, **일반법보다 특수법이 우선된다.**라는 것을 생각하면 되겠습니다. 


## 2. CSS 선택자 (Selector) 개요

HTML에 특정 부분에 style을 할당하기 위해서는 **선택자(selector)**라는 것이 필요합니다. 
선택자는 html에 정의된 tag이름이나, 속성이름, 속성값, 내용, 사건(event)이 될 수 있습니다. 
Tag이름이나, 속성이름, 속성값 등은 HTML에서 공부했던 내용들인데, 이를 다시한번 remaind 해보면 다음과 같습니다. 
예를 들어```<a href="https://...........>hello there</a>"```는 ```<태그이름 속성이름=속성값>hello there<\a> ```로 나눌 수 있습니다. 

### 2-1. Tag이름을 이용한 선택법
Tag이름으로 선택하는 방법은 아래와 같습니다. 
```css
h1{
    color: red;
}
```

```html
    <!DOCTYPE html>
    <html>
        <head>
            <title>My CSS website</title>
            <link rel="stylesheet" href="somewhere/style.css">
        </head>
        <body>
            <h1>Welcome!</h1>
            <p>Hi, Thank you so much for visiting my website.</p>

            <h2>Stay Here</h2>
            <p> Please stay with me.</p>

            <input type="time", name="time">
            <input type="date", name="date">
        </body>
    </html>
```
단순하게, ```tag 이름```을 적고, ```{}```을 적은후, style과 관련된 정보를 적어둡니다. 

### 2-2. 속성이름을 이용한 선택법
특정 속성이름을 가진 tag만을 선택할 수도 있습니다. 
선택법은 ```[속성이름]```의 형식을 따릅니다. 
Style을 작성하는 방법은 tag이름을 이용하는 방법과 동일합니다. 
```css
    h1{
        color: red;
    }

    [type] {
        color: green;
    }
```

```html
    <!DOCTYPE html>
    <html>
        <head>
            <title>My CSS website</title>
            <link rel="stylesheet" href="somewhere/style.css">
        </head>
        <body>
            <h1>Welcome!</h1>
            <p>Hi, Thank you so much for visiting my website.</p>

            <h2>Stay Here</h2>
            <p> Please stay with me.</p>

            <input type="time", name="time">
            <input type="date", name="date">
        </body>
    </html>
```

### 2-3. 특정 속성값을 이용한 선택법
특정 속성값을 가진 tag만을 선택할 수도 있습니다.  
작성법은 ```[type=value]```와 같이, 속성이름을 적고, 속성값을 적은 후, style을 할당해 주면 됩니다. 

```css
    h1{
        color: red;
    }

    [type] {
        color: green;
    }

    [type="date"]{
        color: blue;
    }
```

```html
    <!DOCTYPE html>
    <html>
        <head>
            <title>My CSS website</title>
            <link rel="stylesheet" href="somewhere/style.css">
        </head>
        <body>
            <h1>Welcome!</h1>
            <p>Hi, Thank you so much for visiting my website.</p>

            <h2>Stay Here</h2>
            <p> Please stay with me.</p>

            <input type="time", name="time">
            <input type="date", name="date">
        </body>
    </html>
```

또한 tag의 특정 내용 부분에만 style을 적용시킬 수도 있습니다. 
가령, ```p tag```에서 첫번째 텍스트에만 스타일을 적용하고 싶다면, ```::first-letter```이라는 pseudo-element라는 것을 추가로 선언해 주면 됩니다. 
아래는 예시 입니다. 
```css
    h1{
        color: red;
    }

    [type] {
        color: green;
    }

    [type="date"]{
        color: blue;
    }

    p::first-letter{ # pseudo-element
        color: red;
    }
```

```html
    <!DOCTYPE html>
    <html>
        <head>
            <title>My CSS website</title>
            <link rel="stylesheet" href="somewhere/style.css">
        </head>
        <body>
            <h1>Welcome!</h1>
            <p>Hi, Thank you so much for visiting my website.</p>

            <h2>Stay Here</h2>
            <p> Please stay with me.</p>

            <input type="time", name="time">
            <input type="date", name="date">
        </body>
    </html>
```

### 2.4 특정 event을 이용한 선택법

특정 event가 발생했을때, style을 적용시키는 방법 입니다. 
가령, checkbox에 check가 되었다던지, 아니면, 특정 tag를 가진 내용에 마우스커서가 올라갔다던지 등 다양한 event에 style을 적용시킬 수 있다. 
아래는 예시로, ```:hover```라고 하는 pseudo class를 선언함으로써 이용할 수 있다. 
이는 마우스커서가 올라가면 발생하는 event 입니다. 

```css
    h1{
        color: red;
    }

    [type] {
        color: green;
    }

    [type="date"]{
        color: blue;
    }

    p::first-letter{ # pseudo-element
        color: red;
    }

    h2:hover { # pseudo-class
        color: yellow;
    }
```

```html
    <!DOCTYPE html>
    <html>
        <head>
            <title>My CSS website</title>
            <link rel="stylesheet" href="somewhere/style.css">
        </head>
        <body>
            <h1>Welcome!</h1>
            <p>Hi, Thank you so much for visiting my website.</p>

            <h2>Stay Here</h2>
            <p> Please stay with me.</p>

            <input type="time", name="time">
            <input type="date", name="date">
        </body>
    </html>
```
