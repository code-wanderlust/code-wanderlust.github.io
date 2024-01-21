---
title: HTML의 모든것 2부 - HTML의 제목, 본문 단락, 목록, 표 tags
date: 2023-12-30 10:32:30 +0900
categories: [Web, HTML]
tags: [web, html, frontend]     # TAG names should always be lowercase
published: true
---

> [HTML 1부](https://code-wanderlust.github.io/posts/HTML의-모든것-1부-HTML이란-무엇인가/)에서 HTML이 어떤것인지 알아보았다. 
> 이어서 본 포스팅에서는 제목, 글, 표, 목록과 관련된 내용에 대해 다루어 보려고 한다.록
> 지루한 내용이라고 생각할 수 있겠으나, 기본이 되는 중요한 내용이라고 생각한다. 

## 1. HTML 글제목 tag
글의 제목을 나타내는 html tag들은 ```<h1></h1>```, ```<h2></h2>```, ```<h3></h3>```와 같은 tag를 이용합니다. 
여기서 ```h```는 heading의 약자를 나타내고 뒤에 붙은 숫자가 작으면 상위 제목이고, 커지면 하위 제목을 나타낸다. 
예제 html는 아래와 같습니다. 

```html
<!DOCTYPE html>
<html>
    <head>
        <title>My website</title>
    </head>
    <body>
        <h1>1. h1 제목</h1>
        <h2>1-1. h2 제목</h2>
        <h3>1-1-1. h3 제목</h3>
        <h4>1-1-1-1. h4 제목</h4>
        <h5>1-1-1-1-1. h5 제목</h5>
        <h6>1-1-1-1-1-1. h6 제목</h6>
    </body>
</html>
```

```h tag```는 google SEO와도 밀접한 관계가 있는 tag로, 해당 tag를 잘 사용하면 문서가 정리가 잘되어 있다는 느낌을 받습니다. 

## 2. HTML 본문단락 tag
본문의 단략을 나타내는 tag는 ```p tag```를 이용하며, ```<p></p>```와 같이 사용할 수 있습니다. 
여기서 ```p```는 paragraph를 나타냅니다. 
```p tag```는 tag가 시작하기 전/후로 행의 간격을 살짝 벌려준다는 특징이 있다. 
다음은 ```p tag```를 이용해본 예시 이다. 

```html
<!DOCTYPE html>
<html>
    <head>
        <title>My website</title>
    </head>
    <body>
        <h1>1. h1 제목</h1>
        <p>안녕하세요? 저의 홈페이지에 와주셔서 감사합니다. </p>
        <p>오늘도 좋은 하루 보내셔요.</p>
    </body>
</html>
```

해당 tag를 사용할때 유의해야할 점이 있다. 그것은 바로 해당 tag안에서는 <kbd>space</kbd>를 여러변 쳐서 간격을 늘리거나 <kbd>enter</kbd>키가 무시된다는 점 이다. 
가령 아래의 html 문서는 위의 html 문서와 동일하게 web browser에 나타내진다. 

```html
<!DOCTYPE html>
<html>
    <head>
        <title>My website</title>
    </head>
    <body>
        <h1>1. h1 제목</h1>
        <p>안녕하세요?                 저의 홈페이지에 와주셔서 
            감사합니다. </p>
        <p>오늘도 좋은 하루 보내셔요.</p>
    </body>
</html>
```
만약, 실제로 <kbd>space</kbd>를 여러번 치는 효과를 주고 싶다면, **character entity**를 사용하면 됩니다. 
<kbd>space</kbd>에 해당하는 character entity는 ```&nbsp;```로, 여기서 ```nbsp```는 non-breaking space에 약자 입니다. 
즉, 줄바꿈을 하지 않는 space라는 뜻 입니다. 
앞서 보여 듯이 character entity 는 ```&``` 와 ```;```사이에 특정한 이름적게 되는데, entity 번호를 적어도 무방합니다. 
```nbsp```의 번호는 ```#160```으로 ```&nbsp;```와 ```&#160;```은 동일합니다. 
자 그럼, 아래와 같이 ```&nbsp;```를 적용하면 아래와 같다. 

```html
<!DOCTYPE html>
<html>
    <head>
        <title>My website</title>
    </head>
    <body>
        <h1>1. h1 제목</h1>
        <p>안녕하세요? &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;저의 홈페이지에 와주셔서 
            감사합니다. </p>
        <p>오늘도 좋은 하루 보내셔요.</p>
    </body>
</html>
```
그 결과는 직접 web browser를 통해 확인해보면 좋을 것 같습니다. 

Character entity는 ```nbsp```외에도 많이 있는데, 키보드상에 없는 문자나 symbol를 표시하고 싶거나, html에서 이미 지정된 기호를 문자로 사용하고 싶을때 사용합니다. 
가령, html에서 tag를 표시하기 위해 ```<```와 ```>``` 기호를 사용하는데, 이를 사용하고 싶으면, character entity로 ```&lt;```와 ```&gt;```를 사용하면 된다. 
Character entity에는 정말 많은 종류가 있는데, 따로 cheat sheet같은 것을 통해 참조해가면서 쓰면 됩니다. 
가령 다음과 같은 [cheat sheet](https://www.htmlquick.com/reference/character-entity-reference.html)들을 참조하면 되겠습니다. 

마지막으로, <kbd>enter</kbd>키를 사용하는 방법은 character entity가 아닌, 특수한 tag가 있는데 ```<br>```tag를 사용합니다. 
```<br>``` tag는 break를 나타내며, end tag가 없는것이 특징 입니다. 
이와 같이, end tag가 없는것은 안쪽에 적어둘 내용이 없기때문에, 특별히 *empty tag*라 부릅니다. 
그럼, 마지막으로 ```<br>```를 적용해보면 아래와 같습니다. 

```html
<!DOCTYPE html>
<html>
    <head>
        <title>My website</title>
    </head>
    <body>
        <h1>1. h1 제목</h1>
        <p>안녕하세요? &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;저의 홈페이지에 와주셔서 <br> 감사합니다. </p>
        <p>오늘도 좋은 하루 보내셔요.</p>
    </body>
</html>
```



## 3. HTML 목록 tag (List Tag)
목록 tag에는 숫자가 있는 순서가 있는 목록과 단순 symbol이 붙는 순서가 없는 목록으로 나누어 집니다. 
여기서 순서가 있는 목록은 ```<ol></ol>```tag를 이용하며 ordered list의 약자입니다. 
순서가 없는 목록은 ```<ul></ul>```로 표시하며, unordered list의 약자입니다. 
목록의 각 항목들은 list item의 약자로 ```<li></li>```로 표시합니다. 
이는 ```<ol></ol>```, ```<ul></ul>``` 상관없이 사용할 수 있습니다. 
아래는 예시 입니다. 

```html
<!DOCTYPE html>
<html>
    <head>
        <title>My website</title>
    </head>
    <body>
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
    </body>
</html>
```
목록 tag는 어떤 글에서 순서들을 나타낼때도 쓸 수 있지만, layout의 navigation 항목들을 나타낼때도 쓸 수 있습니다. 

## 4. HTML 표 tag (Table Tag)
표는 행과 열로 표시되는 것으로, 표를 만들고 싶으면 ```<table> </table>```이라는 tag를 이용합니다. 
```<table> </table>``` tag를 선언한 후, 그 내부에 행(row)을 선언하는데, table row의 약자인 ```<tr></tr>```을 선언합니다. 
그리고, 각 행의 cell을 나누기 위해서 (혹은 렬(column)을 선언하기 위해), ```<th></th>```와 ```<td></td>```를 이용합니다. 
```<th></th>```는 table header의 약자로, 표의 열에 어떠한 정보가 적혀있는지 알려주는 역할을 하며, 이를 지정하여 내부를 채우면, 자동적으로 bold체가 사용되고, cell의 중앙에 정렬이 됩니다. 
```<td></td>```는 table data의 약자로, 뭔가 표의 내용을 적어두는 역할을 합니다. 
다음은 이를 이용한 간단한 예시 입니다. 

```html
<!DOCTYPE html>
<html>
    <head>
        <title>My website</title>
    </head>
    <body>
        <table>
            <tr>
                <th> 모델 </th>
                <th> 방법 </th>
                <th> 성능1 </th>
                <th> 성능2 </th>
            </tr>
            <tr>
                <th> BERT </th>
                <th> Method-A </th>
                <th> 70.1 </th>
                <th> 34.2 </th>
            </tr>
            <tr>
                <th> Albert </th>
                <th> Method-B </th>
                <th> 65.1 </th>
                <th> 28.2 </th>
            </tr>
        </table>
    </body>
</html>
```

위와 같이 표를 정의하면, 경계선이 없어서, 식별하기 어렵다는 단점이 있다. 
표에 외곽선을 넣어주기 위해서는, 외곽선 속성(attribute)인 ```border```를 입력해주면 됩니다. 
속성값으로는 적당히 입력해 줍니다. 다만, 중요한것이 속성값은 반드시 ```" "```으로 묶어주어야 한다는 점 입니다. 
아래는 예시 입니다. 

```html
<!DOCTYPE html>
<html>
    <head>
        <title>My website</title>
    </head>
    <body>
        <table border="5">
            <tr>
                <th> 모델 </th>
                <th> 방법 </th>
                <th> 성능1 </th>
                <th> 성능2 </th>
            </tr>
            <tr>
                <th> BERT </th>
                <th> Method-A </th>
                <th> 70.1 </th>
                <th> 34.2 </th>
            </tr>
            <tr>
                <th> Albert </th>
                <th> Method-B </th>
                <th> 65.1 </th>
                <th> 28.2 </th>
            </tr>
        </table>
    </body>
</html>
```

추가로, 여러 column에 걸친 row를 만들고 싶다면, ```<tr></tr>```tag에 ```colspan```이라는 attribute를 추가해주고, attribute value로 몇개의 column을 합쳐서 사용할지 명시해 두면 됩니다. ```colspan```은 column span의 약자 입니다. 

```html
<!DOCTYPE html>
<html>
    <head>
        <title>My website</title>
    </head>
    <body>
        <table border="5">
            <tr>
                <th colspan="4">성적표</th>
            </tr>
            <tr>
                <th> 모델 </th>
                <th> 방법 </th>
                <th> 성능1 </th>
                <th> 성능2 </th>
            </tr>
            <tr>
                <th> BERT </th>
                <th> Method-A </th>
                <th> 70.1 </th>
                <th> 34.2 </th>
            </tr>
            <tr>
                <th> BERT </th>
                <th> Method-B </th>
                <th> 65.1 </th>
                <th> 28.2 </th>
            </tr>
        </table>
    </body>
</html>
```

추가로, 두개의 row에서 특정부분을 합치는 방법 ```rowspan```이라는 attribute를 사용하면 됩니다. 
만약 두개의 row를 합치고 싶다면, ```rowspan```의 attribute의 값으로 ```"2"```를 설정해주면 됩니다. 
아래는 row span의 예시 입니다. 
아래 예시에서 ```rowspan``` attribute를 선언한 row를 기준으로, 그 아래의 row의 ```<th></th>```tag는 삭제되어 있는 것을 알 수 있습니다. 

```html
<!DOCTYPE html>
<html>
    <head>
        <title>My website</title>
    </head>
    <body>
        <table border="5">
            <tr>
                <th colspan="4">성적표</th>
            </tr>
            <tr>
                <th> 모델 </th>
                <th> 방법 </th>
                <th> 성능1 </th>
                <th> 성능2 </th>
            </tr>
            <tr>
                <th rowspan="2"> BERT </th>
                <th> Method-A </th>
                <th> 70.1 </th>
                <th> 34.2 </th>
            </tr>
            <tr>
                <th> Method-B </th>
                <th> 65.1 </th>
                <th> 28.2 </th>
            </tr>
        </table>
    </body>
</html>
```

표를 html로 작성하려면 상당히 복잡할 수 있는데, 최상단에서 부터 왼쪽에서 오른쪽으로 차근차근 작성해주어야 헷갈리지 않고 표를 만들 수 있습니다. 


> HTML 시리즈
> 1. [HTML의 모든것 1부 - HTML이란 무엇인가](https://code-wanderlust.github.io/posts/HTML의-모든것-1부-HTML이란-무엇인가/)
> 2. [HTML의 모든것 2부 - HTML의 제목, 본문 단락, 목록, 표 tags](https://code-wanderlust.github.io/posts/HTML의-모든것-2부-HTML-내용-tags/)
> 3. [HTML의 모든것 3부 - HTML의 Media (이미지, 오디오, 비디오) tags](https://code-wanderlust.github.io/posts/HTML의-모든것-3부-HTML의-Media-(이미지,-오디오,-비디오)-tags/)
> 4. [HTML의 모든것 4부 - HTML의 하이퍼링크, 입력 tags](https://code-wanderlust.github.io/posts/HTML의-모든것-4부-HTML의-하이퍼링크,-입력-tags/)
> 5. [HTML의 모든것 5부 - HTML의 구조적 정보와 tags, 그리고 head tags](https://code-wanderlust.github.io/posts/HTML의-모든것-5부-HTML의-구조적-정보와-tags,-그리고-head-tags/)