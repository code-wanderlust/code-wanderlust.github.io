---
title: HTML의 모든것 4부 - HTML의 하이퍼링크, 입력 tags
date: 2023-12-30 17:12:30 +0900
categories: [Web, HTML]
tags: [web, html, frontend]     # TAG names should always be lowercase
published: true
---

> 본 포스팅에서는 하이퍼링크를 넣는 방법과, 입력 양식에 대해 알아보려고 한다. 


## 1. HTML 하이퍼링크 태그
하이퍼링크 태그는 ```<a></a>```를 이용하며, 해당 태그를 쓰면, 링크에 따라 다른 web page로 이동이 가능해집니다. 
링크는 ```href``` attribute를 이용합니다. 
아래는 예시 코드 입니다. 

```html
<!DOCTYPE html>
<html>
    <head>
        <title>My website</title>
    </head>
    <body>
        <a href="somewhere_link">어디론가 이동하기</a>
    </body>
</html>
```

심지어는 특정 web page내에서 특정 위치로도 이동이 가능한데, 이동하고 싶은 위치의 ```id```를 주소에 입력해주면 됩니다. 
여기서 ```id```는 모든 html tag의 attribute로 선언이 가능하며, 특정 tag에 고유한 이름을 부여할 수 있게 해줍니다. 
아래는 특정 id로 이동하는 것을 나타내는 예시 입니다. 

```html
<!DOCTYPE html>
<html>
    <head>
        <title>My website</title>
    </head>
    <body>
        <a href="someehre.html#id">어디론가 이동하기</a>
    </body>
</html>
```

여기서 위에 서 처럼 ```*.html#{id_name}```의 형식으로 작성해 줍니다. 
추가적으로, 단순히 ```#```만 입력하면 지금 있는 page의 최상단으로 이동합니다. 
Web page에서 새로운 창을 띄워서 링크로 가고 싶으면, ```target``` 속성을 이용하고, 속성값으로 ```"_blank"```를 씁니다. 
새로운 링크를 그냥 현재 page에서 넘어가게 하고 싶으면, 아무것도 안쓰면 됩니다. 
하지만, 이를 명시적으로 표시해주고 싶으면, ```target```속성을 정의하고, 그 값으로 ```"_self"```를 씁니다. 
아래는 그 예시 입니다. 

```html
<!DOCTYPE html>
<html>
    <head>
        <title>My website</title>
    </head>
    <body>
        <a href="someehre.html#id" target="_blank">어디론가 이동하기</a>
    </body>
</html>
```

## 2.HTML 입력양식 태그 (Form tag)
입력양식 (Form tag)는 web page에서 다양한 정보를 입력해야할때 사용하는 tag 입니다. 
주요 tag로는 ```<input>```, ```<select></select>```, ```<textarea></textarea>```, ```<fieldset></fieldset>```, ```<legend></legend>```가 있습니다. 

```<input>```태그는 ```type```속성을 이용하여, 어떤 type의 입력인지 지정해 주어야 합니다. 
주요 입력 type으로는 ```"text"```, ```"radio"```, ```"checkbox"```, ```"submit"```, ```"reset"```등등의 다양한 type이 있습니다. 
또한, ```<input>```태그는 ```name```이라는 속성에 고유한 이름을 만들어줘야 합니다. 
그래야 어디서 받아온 데이터인지 구분할 수 있습니다. 

```<select></select>```태그를 지정하면, 콤보박스를 만들어서 ```<option></option>```태그로 지정된 요소들을 선택할 수 있게 해줍니다. 
```<textarea></textarea>```태그를 사용하면, multi-line text box를 만들 수 있게되며, 문자열을 입력으로 받을 수 있게 해줍니다. 
```<fieldset></fieldset>```이나 ```<legend></legend>```를 이용하면, 여러 element들을 보기 좋게 묶어줄 수 있습니다. 
아래는 위의 태그들을 이용하여 작성한 예시 입니다. 

```html
<!DOCTYPE html>
<html>
    <head>
        <title>My website</title>
    </head>

    <body>
        <form>
            <fieldset>
            <legend>Information</legend>
                <input type="text" name="input1">
                <input type="text" name="input2">
                <select name="Drinks">
                    <option>option1</option>
                    <option>option2</option>
                    <option>option3</option>
                    <option>option4</option>
                </select>
                <br>
                <textarea name="memo">메모를 남겨주세요</textarea>
                <br>
                <br>
                <input type="submit">
                <input type="reset">
            </fieldset>
        </form>
    </body>
</html>
```

위의 html을 이용하여 입력을 받으면, 어디론가 전달이 되어 처리가 진행이 될텐데, 그 부분을 우리는 *backend*이라 부릅니다. 
보통 backend는 ```php```, ```ASP```, ```Java```, ```Python```, ```Ruby```, ```Node.js```등과 같은 server측에서 사용하는 programing language를 이용하여 만들어 집니다. 
만약, 입력을 backend의 어딘가로 보내기 위해서는 ```<form></form>``` 태그에 ```action``` attribute를 이용하여 소스코드의 위치를 알려줍니다. 
또한 정보를 보내는 방식도 알려줘야 하는데, ```"get"```방식과 ```"post"```로 나누어 지는데, 이를 ```method```라는 attribute를 통해 지정해 줄 수 있습니다. 
만약 지정해주지 않으면, default로 ```"get"```방식을 이용해 줍니다. 
두 방식의 특징은 다음과 같습니다. 

* ```"get"```: 데이터가 노출, 용량제한
* ```"post"```: 데이터를 은닉, 큰용량

두 방식에 따라 데이터를 전달할때 url이름이 바뀌게 되는데, ```"get"```방식을 이용하면, url에 ```name``` attribute의 값과 그에 해당하는 입력값이 그대로 노출이 됩니다. 
하지만, ```"post"```방식은 암호화되어 url에 정보들이 나타지 않게 됩니다. 

```html
<!DOCTYPE html>
<html>
    <head>
        <title>My website</title>
    </head>

    <body>
        <form action="process.py">
            <fieldset>
            <legend>Information</legend>
                <input type="text" name="input1">
                <input type="text" name="input2">
                <select name="Drinks">
                    <option>option1</option>
                    <option>option2</option>
                    <option>option3</option>
                    <option>option4</option>
                </select>
                <br>
                <textarea name="memo">메모를 남겨주세요</textarea>
                <br>
                <br>
                <input type="submit">
                <input type="reset">
            </fieldset>
        </form>
    </body>
</html>
```

## 3.HTML Input tag의 type들
앞서 소개 하였듯이, ```<input>``` tag에는 다양한 ```type``` attribute를 지정해 줄 수 있습니다. 
우선 대략적으로 소개해 드리자면, ```"text"```, ```"password"```, ```"submit"```, ```"reset"```, ```"radio"```, ```"checkbox"```, ```"file"```, ```"email"```, ```"url"```, ```"color"```, ```"date"```, ```"time"```, ```"month"```, ```"number"```, ```"button"```이 있습니다. 

1. ```"text"```: 일반적인 문자나 숫자를 입력으로 받을 수 있게 해줍니다. 
2. ```"password"```: 입력하는 string이 노출되지 않도록 별표 표시를 해줍니다. 
3. ```"submit"```: 
4. ```"reset"```: 
5. ```"radio"```: 여러 종류 중 하나를 선택할 수 있게 해줍니다. 특히, 동일한 구성이면, ```name```을 같게 만들어 줘야 합니다.
6. ```"checkbox"```: ```radio```와 비슷하지만, ```name```을 같게 만들어줄 필요는 없습니다. 
7. ```"file"```: 파일을 업로드 할수 있게 해줍니다. ```"submit"``` 속성을 통해 파일을 전송시킬때, 반드시 ```"post"```방식으로 전송시켜야 합니다. 
7. ```"email"```: email을 입력받을 수 있게 해줍니다. 특히, email의 형식에 맞지 않는다면, 에러를 표시해 줍니다. 
8. ```"url"```: url형식에 맞지 않는 string이 들어오면, 에러를 나타냅니다. 
9. ```"color"```: 색상 정보를 입력해 줄 수 있게 해줍니다. 
10. ```"date"```: 날짜 정보를 입력해 줄 수 있게 해줍니다. 
11. ```"time"```: 시간 정보를 입력해 줄 수 있게 해줍니다. 
12. ```"month"```: 월 정보를 입력해 줄 수 있게 해줍니다. 
13. ```"number"```: 숫자만 입력받을 수 있는 곳 입니다. 최대/최소값을 정해줄 수 있고, 유효성에 맞지 않는다면, 에러를 표시해 줍니다. 
14. ```"button"```: 단순클릭을 했을때 발생하는 event를 발생시키는데, 이것은 ```javascript```를 통해 코드를 작성해야 합니다. 

아래는 예시 코드 입니다. 

```html
<!DOCTYPE html>
<html>
    <head>
        <title>My website</title>
    </head>

    <body>
        <form action="process.py">
            <input type="text" name="input1"><br>
            <input type="password" name="password"><br>
            <input type="radio" name="gender", value="male", checked>남<br>
            <input type="radio" name="gender", value="female", checked>여<br>
            <input type="checkbox" name="computer" checked>컴퓨터<br>
            <input type="checkbox" name="smartphone">스마트폰<br>
            <input type="file" name="file"><br>
            <input type="email" name="email"><br>
            <input type="url" name="url"><br>
            <input type="color" name="color"><br>
            <input type="date" name="date"><br>
            <input type="time" name="time"><br>
            <input type="month" name="month"><br>
            <input type="number" name="number" min="-3" max="10"><br>
            <input type="button" onclick="alert('Yo!')" value="Click"><br>
            <input type="submit">
            <input type="reset">
        </form>
    </body>
</html>
```


> HTML 시리즈
> 1. [HTML의 모든것 1부 - HTML이란 무엇인가](https://code-wanderlust.github.io/posts/HTML의-모든것-1부-HTML이란-무엇인가/)
> 2. [HTML의 모든것 2부 - HTML의 제목, 본문 단락, 목록, 표 태그들](https://code-wanderlust.github.io/posts/HTML의-모든것-2부-HTML-내용-tags/)
> 3. [HTML의 모든것 3부 - HTML의 Media (이미지, 오디오, 비디오) tags](https://code-wanderlust.github.io/posts/HTML의-모든것-3부-HTML의-Media-(이미지,-오디오,-비디오)-tags/)
> 4. [HTML의 모든것 4부 - HTML의 하이퍼링크, 입력 tags](https://code-wanderlust.github.io/posts/HTML의-모든것-4부-HTML의-하이퍼링크,-입력-tags/)
> 5. [HTML의 모든것 5부 - HTML의 구조적 정보와 tags, 그리고 head tags](https://code-wanderlust.github.io/posts/HTML의-모든것-5부-HTML의-구조적-정보와-tags,-그리고-head-tags/)