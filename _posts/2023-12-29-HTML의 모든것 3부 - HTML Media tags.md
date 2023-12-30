---
title: HTML의 모든것 3부 - HTML의 Media (이미지, 오디오, 비디오) tags
date: 2023-12-30 13:47:30 +0900
categories: [Web, HTML]
tags: [web, html, frontend]     # TAG names should always be lowercase
published: true
---

> [HTML 2부]()에 이어서, 본 포스팅에서는 Media들을 html에서는 어떻게 다룰 수 있는지 알아보려고 한다. 

## 1. HTML 이미지 태그
그림 태그를 이용하면, web page에 그림을 넣어줄 수 있다. ```<img>```라는 태그를 사용하며, empty tag로 끝태그가 필요가 없습니다. 
다만, 어떤 그림을 넣을지 지정해준 ```src```라는 attribute를 사용합니다. 

```html
<!DOCTYPE html>
<html>
    <head>
        <title>My website</title>
    </head>
    <body>
        <img src="something_img_path/img.jpg">
    </body>
</html>
```

간혹 image경로가 잘못되었거나 해서, image대신 text를 띄울 수도 있는데, ```alt```라는 attribute를 사용하면 됩니다. 
```alt```는 alternate의 약자입니다. 

```html
<!DOCTYPE html>
<html>
    <head>
        <title>My website</title>
    </head>
    <body>
        <img src="something_img_path/img.jpg", alt="My image">
    </body>
</html>
```

그림의 크기를 조절하고 싶으면 ```width```, ```height``` attribute를 사용하면 됩니다. 
각 attribute의 값들은 pixel단위 입니다. 

```html
<!DOCTYPE html>
<html>
    <head>
        <title>My website</title>
    </head>
    <body>
        <img src="something_img_path/img.jpg", alt="My image", width="70", height="100">
    </body>
</html>
```

```<img>```태그는 다른 태그와 섞어서 사용이 가능합니다. 가령 image에 hyperlink를 걸고 싶으면, ```<a></a>```태그로 감싸줍니다. 

```html
<!DOCTYPE html>
<html>
    <head>
        <title>My website</title>
    </head>
    <body>
        <a href="https://hostlink">
            <img src="something_img_path/img.jpg", alt="My image", width="70", height="100">
        </a>
    </body>
</html>
```

또한, 특정 tag의 배경에 그림을 넣어주는 방법도 있는데, ```style``` attribute를 선언해서 사용하면 됩니다.
가령, ```<body></body>```태그에 ```style``` 속성을 선언하고, image 링크를 걸어두면, web page 전체 배경에 image가 보여집니다. 
혹은, ```<p></p>```태그에 ```style``` 속성으로 image를 부여하면, 특정 paragraph의 배경에 image가 보여집니다. 
아래는 예시 입니다. 

```html
<!DOCTYPE html>
<html>
    <head>
        <title>My website</title>
    </head>
    <body style="background-image:url('somewheere_img_path/img2.jpg')">
        <a href="https://hostlink">
            <img src="something_img_path/img.jpg", alt="My image", width="70", height="100">
        </a>
        <p style="background-image:url('somewheere_img_path/img3.jpg')">
            안녕하세요 여긴 paragraph입니다. 
        </p>
    </body>
</html>
```

## 2. HTML 오디오 태그
오디오 태그를 이용하면 음악파일을 재생할 수 있습니다. 우선 ```<audio></audio>```태그를 선언하고, ```src``` attribute를 이용하여 경로를 넣어줍니다. 
아래는 예시 입니다. 

```html
<!DOCTYPE html>
<html>
    <head>
        <title>My website</title>
    </head>
    <body>
        <audio src="something_path/music.mp3"></audio>
    </body>
</html>
```

위와 같이 문서를 작성해서 web browser를 띄우면 아무것도 보이지 않습니다. 
보통 오디오 재생과 관련한 controller가 있으면 좋은데, ```controls```라는 attribute를 선언해야 합니다. 

```html
<!DOCTYPE html>
<html>
    <head>
        <title>My website</title>
    </head>
    <body>
        <audio src="something_path/music.mp3" controls></audio>
    </body>
</html>
```

위와 같이 작성하면 재생하고 멈추고 하는 기능을 할 수 있는 controller가 보일것 입니다. 
추가적으로, ```autoplay``` 속성을 추가하면, web page가 열리면 바로 음악이 재생이 됩니다. 
무한반복 속성은 ```loop```로 지정하면 됩니다. ```loop```속성을 지정하면, 음악이 모두 재생되자마자 바로 처음으로 와서 재생이 됩니다. 
아래는 모든 속성을 적용시킨 html 문서 입니다. 

```html
<!DOCTYPE html>
<html>
    <head>
        <title>My website</title>
    </head>
    <body>
        <audio src="something_path/music.mp3" controls autoplay loop></audio>
    </body>
</html>
```

## 3. HTML 비디오 태그
비디오 태그를 사용하면 동영상 파일을 재생할 수 있습니다. 비디오 태그는 ```<video></video>```태그를 이용하며, 사용법은 image나 audio와 유사합니다. 
아래는 예시 입니다. 

```html
<!DOCTYPE html>
<html>
    <head>
        <title>My website</title>
    </head>
    <body>
        <video src="something_path/video.mp4"></video>
    </body>
</html>
```

동영상은 다수의 image와 audio가 포함된 데이터로, 그 attribute들도 ```<img>```와 ```<audio></audio>```태그의 것들을 포함합니다. 
즉, ```width```, ```height```, ```controls```, ```autoplay```, ```loop``` attribute모두 사용 가능합니다. 
아래는 예시 입니다. 

```html
<!DOCTYPE html>
<html>
    <head>
        <title>My website</title>
    </head>
    <body>
        <video src="something_path/video.mp4" width="400" height="300" controls, autoplay loop></video>
    </body>
</html>
```

한편, 유튜브와 같이 외부에 있는 동영상을 web page에 나타나게 하는 방법도 있습니다. 
바로 ```<iframe></iframe>```태그를 이용하면 됩니다. ```<iframe></iframe>```태그는 inline frame의 약자 입니다. 
이는 우리의 web page안에 다른 web page의 내용을 넣어서 보여주게 해준다는 의미 입니다. 
사실, 유튜브에서 동영상을 가져올때, "퍼가기"라는 기능이 있는데, 해당 기능을 사용하면, 알아서 ```<iframe></iframe>```태그를 이용하여 html 문서를 만들어 줍니다. 
아래는 예시 입니다. 

```html
<!DOCTYPE html>
<html>
    <head>
        <title>My website</title>
    </head>
    <body>
        <video src="something_path/video.mp4" width="400" height="300" controls, autoplay loop></video>

        <iframe width="560" height="315" 
                src="Something_YouTube_Link" 
                title="YouTube video player" 
                frameborder="0" 
                allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen>
        </iframe>

    </body>
</html>
```

> HTML 시리즈
> 1. [HTML의 모든것 1부 - HTML이란 무엇인가]()
> 1. [HTML의 모든것 2부 - HTML의 제목, 본문 단락, 목록, 표 태그들]()
> 2. [HTML의 모든것 3부 - HTML의 Media (이미지, 오디오, 비디오) tags]()
> 3. [HTML의 모든것 4부 - HTML의 하이퍼링크, 입력 tags]()
> 4. [HTML의 모든것 4부 - HTML의 구조적 정보와 tags, 그리고 head tags]()