# JavasSript 교육자료 (신입)

## JavaScript 소개
* HTML과 CSS는 정적인 언어
* JavaScript는 HTML과 CSS로 만들어진 웹페이지를 동적으로 변경해주는 언어
* HTML, CSS 기본적인 선행학습 필요
* 작성한 코드를 브라우저에서 바로 실행 가능

### JavaScript의 역할
* HTML 엘리먼트 추가/삭제 및 CSS 스타일 변경
* 폼 유효성 검증
* 사용자와의 상호작용 (마우스, 키보드, 터치)
* 웹 브라우저 쿠키 설정/조회
* AJAX 이용한 웹 서버와 통신

### 과거 JavaScript는?
초창기 웹페이지의 보조적인 기능을 수행하기 위한 용도로 사용

* 1995년 브렌던 아이크(Brendan Eich) 넷스케이프 지원
* 모카 -> 라이브스크립트 -> 자바스크립트
* 국제 표준화 단체인 ECMA International에서 JavaScript 표준화 진행
* 크로스 브라우징, 보안 취약점 문제
* 전문적이지 못한 인식 (Copy & Paste)

### JavaScript 환경 변화

* 데이터의 유형이 텍스트 -> 이미지 -> 미디어로 진화 (개발비용, 난이도, 복잡도 증가)
* 과거에 서버에서 담당하던 역할들이 상당 부분 프론트 이동

* Ajax - 전체 페이지를 다시 렌더링하지 않고 변경되는 부분만 갱신
* jQuery - 보다 쉽게 DOM을 핸들링
* HTML5 - 마크업, JavaScript API를 강화
* NodeJS - 서버 개발 가능, 더 많은 개발자들이 자바스크립트 사용
* ECMAScript2015 (ES6) - 언어로서의 완성도가 높아짐

### 현재 자바스크립트는?
브라우저에서만 사용하는 용도를 벗어나 다양한 환경에서 폭넓게 활용
<img src="img/js_all.png" alt="">

* MeanStack (Full Stack Javascript Framework)
* 클라이언트 / 서버 / 데이터베이스 모두 자바스크립트 기반 (JSON 형태로 통신)
* 모바일 앱(iOS & Android), 데스크탑 앱

### SPA (Single Page Application)
* PC -> 모바일 사용자의 증가 (트래픽 감소와 속도, 사용성, 반응성 이슈)
* 프론트엔드 프레임워크의 강화 (React, Angular, Vue)
* 필요한 모든 정적 리소스를 최초에 한번 다운로드
* 페이지 이동없이 고속으로 화면 전환
* 네이티브 앱과 유사한 사용자 경험 제공

### PWA (Progressive Web Apps)
최적화된 웹 성능에 모바일의 Native 기능을 결합한 최신 웹 앱
* 모바일 앱의 단점 (개발, 빌드, 배포, 검색 다운로드, 설치)
* 홈 화면 아이콘 추가, 오프라인 서비스, 푸시 알림 등 웹에서도 가능하게 하는 기술 (Service Worker, Manifest)

## JavaScript 시작
### 코드 작성 준비
* 아래 코드를 HTML head, body 태그 안에 작성
* script 태그의 src 속성을 사용하여 외부 js 파일 연결
```html
<!-- internal -->
<script type="text/javascript">
    //코드 작성

    //한줄주석
    /* 여러줄 주석 */
</script>

<!-- external -->
<script type="text/javascript" scr="js/ui/ui-base.js"></script>
```

### script 태그 위치
```html
<!DOCTYPE html>
<html>
<head>
    <title>HTML Page</title>
    //Bad
    <script scr="js/lib/jquery-1.9.1.min.js"></script>
    <script scr="js/ui/ui-base.js"></script>
</head>
<body>
    ...
    //Good
    //body 요소 안, 맨 마지막 위치
    <script scr="js/lib/jquery-1.9.1.min.js"></script>
    <script scr="js/ui/ui-base.js"></script>
</body>
</html>
```

### script 태그 속성

<script src="script.js"></script>
<img src="img/Normal-Execution.png " alt="">

<script async src="script.js"></script>
<img src="img/Async-Execution.png " alt="">

<script defer src="script.js"></script>
<img src="img/Defer-Execution.png " alt="">


## 변수 (Variable)
### 변수 선언
* 숫자로 시작 할 수 없음
* 대소문자 구별
* 이미 정의된 예약어 사용 안됨 (var, function, new, typeof..)
```js
var number;
var str;

//한번에 선언 (콤마를 이용해 구분)
var number, str;

//숫자시작 X
var 1st = 10; //SyntaxError

//대소문자 구분, 완전히 다른변수
var value = 25;
var Value = 26;

//예약어 X
//var function; //SyntaxError
```

### 변수의 중복 선언
변수의 중복 선언은 문법적으로 허용, 하지만 사용하지 않는 것이 좋음
```js
var x = 1;
console.log(x); //1

//중복 선언
var x = 100;
console.log(x); //100
```

### 변수 선언 시 var 키워드 생략 허용
의도하지 않게 변수를 전역화할 수 있으므로 사용하지 않는 것이 좋음
```js
x = 1;
console.log(x); //1
```

### 변수 호이스팅 (Hoisting)
* 모든 변수 선언은 각 함수(스코프)의 가장 최상위로 끌어 올려짐
* 첫 줄 이후 선언된 변수들은 호이스팅으로 인해 선언한 곳 이전부터 존재
* 모든 변수들을 최상위에 함께 선안하고 값을 초기화 하는 것이
* 호이스팅으로 인해 발생할 수 있는 문제들을 줄일 수 있음


## 배열 (Array)
## 객체 (Object)
## 함수 (Function)
## 유효범위 (Scope)
## 객체지향 프로그래밍 (OOP)
## jQuery


http://blog.naver.com/PostView.nhn?blogId=love_junim&logNo=220521655429&parentCategoryNo=&categoryNo=59&viewDate=&isShowPopularPosts=false&from=postView


http://webclub.tistory.com/393?category=501048
http://webclub.tistory.com/559?category=501058
https://cimfalab.github.io/deepscan/2016/09/code-review-2

http://guswnsxodlf.github.io/javascript-class-and-prototype-1
https://netil.github.io/slides/naver-fe-oss/

https://github.com/nhnent/fe.javascript/wiki/jquery-%EA%B0%80%EC%9D%B4%EB%93%9C



자바스크립트에서 호이스팅이란 기본적으로 내장된 기능으로 
var 선언문 전에 변수를 사용해도 이미 사용된것으로 간주

변수가 선언되기 전에 사용이 가능
 우선, 아래 예문을 살펴보면 자바스크립트는 실행시 모든 변수가 선언 됩니다. 아직 변수를 정의하기 전이라 undefined 가 출력되고 선언 이후에 값이 나오는 것을 알 수 있습니다.


# 자바스크립트 this 

간단히말해, 자바스크립트에서 this는 메서드를 호출한 호출객체를 가르킵니다.



# 클로저

함수 내부에서 만든 지역 변수가 사라지지 않고 계속해서 값을 유지하면서 사용되는 현상을 말합니다. 장점으로는 관련된 변수와 기능을 하나의 함수로 묶어 독립적 실행이 가능합니다. 아래와 같이 함수를 리턴하는 형태도 있지만, 클로저는 변수가 사라지지 않고 계속해서 값을 유지하는 모든 상태를 말합니다. 




비동기 프로그래밍
이벤트 발생시 이벤트 핸들러에게 처리를 넘기고 메인 프로그램은 다른 이벤트를 기다림
이벤트 처리가 끝나면 콜백 함수를 실행

비동기 콜백
Synchronous callback: blocking  작업이 끝날때까지 기다림
Asynchronous callback: non-blocking 작업을 시켜놓고 다른일 수행


노드js
구글 크롬의 v8 자바스크립트 엔진에 기반한 서버측 플랫폼
아파치와 같은 별도의 서버 프로그램을 사용하지 않고 서비스를 직접 제공
이벤트 기반, 비동기 I/O, 단일 스레드 루프를 통한 높은 처리성능




배열과 객체는 반드시 리터럴로 선언한다. (필수)
리터럴 표기법은 간결하고 직관적이며, 실제로 자바스크립트 엔진은 리터럴 표기법에 맞게 최적화 되어있다


if와 같은 조건문은?ToBoolean방법에 의한 강제 형(Type) 변환으로 구분되고 항상 다음과 같은 간단한 규칙을 따른다












일반적인 스크립트 태그 같은 경우에
html 파싱(Parsing) 중, 스크립트 태그를 읽게 되면 잠시 파싱을 멈추고 스크립트를 다운받아 실행한 후
다시 파싱 작업을 이어간다. 
이 경우에, html 태그의 ?앞부분(<head>)에 스크립트를 배치 하게 되면 
페이지 렌더링이 시작되기도 전에(페이지 렌더링은 body 태그의 시작과 함께 시작) 스크립트를 다운로드하고 실행하는데 시간을 지연하게 된다. 
물론 짧은 스크립트 일 때는 이 시간은 극히 짧아 그리 신경 쓸 필요가 없지만, 
만약에 인터넷 커넥션이 느리거나 용량이 큰 스크립트를 다운받는다면 아마 사용자는 긴 시간 동안 페이지 로딩을 기다려야 한다. 


위 그림에서처럼 defer와 async를 이용하면 ?HTML 파싱과 동시에 스크립트 다운로드를 진행 할 수 있지만?브라우저 버전 별로 지원하는 범위가 다르고, async의 경우 스크립트 실행 순서를 보장할 수 없어 각 모듈과 DOM의 의존성 관리에 특별히 주의해야 한다.



Async :?HTML 파싱과 동시에 스크립트 다운로드가 진행. 스크립트 다운로드가 완료되는 순간 HTML 파싱을 잠시 멈추고 스크립트를 실행. 이러한 특성 때문에?순서대로 다운로드가 시작된 스크립트라도 순서대로 실행되지는 않는다.
Defer :?HTML 파싱과?동시에 스크립트 다운로드가 진행. async 속성과는 달리 HTML 파싱이 완료된(</html> 태그를 읽은 후) 후 스크립트가 실행된다.






전통적인 웹 방식은 
새로운 페이지 요청 시마다 정적 리소스가 다운로드되고 전체 페이지를 다시 렌더링하는 방식을 사용
새로고침이 발생되어 사용성이 좋지 않다. 
그리고 변경이 필요없는 부분를 포함하여 전체 페이지를 갱신하므로 비효율적이다.

SPA는 기본적으로 웹 애플리케이션에 필요한 모든 정적 리소스를 최초에 한번 다운로드한다. 
새로운 페이지 요청 시, 페이지 갱신에 필요한 데이터만을 전달받아 페이지를 갱신

하므로 
전체적인 트래픽을 감소

전체 페이지를 다시 렌더링하지 않고 변경되는 부분만을 갱신
하므로 새로고침이 발생하지 않아 네이티브 앱과 유사한 사용자 경험을 제공할 수 있다.


모바일의 사용이 증가하고 있는 현 시점에 트래픽의 감소와 속도, 사용성, 반응성의 향상은 매우 중요한 이슈이다. 

SPA의 핵심 가치는 사용자 경험(UX) 향상에 있으며 부가적으로 애플리케이션 속도의 향상도 기대할 수 있어서 모바일 퍼스트(Mobile First) 전략에 부합한다.



초기 구동 속도
SEO(검색엔진 최적화) 문제


처음 자바스크립트가 나왔을 당시 브라우저에서 작은 단위를 처리하는 스크립트로 사용

데이터의 유형이 텍스트 -> 이미지 -> 미디어로 진화

웹 페이지의 성격이 동적으로 변화

HTML의 정적인 텍스트 데이터와 DB의 동적인 데이터를 결합하여 화면에 표시하기 위해, 서블릿 기반의 Server Side Rendering

앞단 화면에서 자바스크립트를 이용한 비동기 처리로 화면을 동적으로 구성 (Client Side Rendering) 



예전 웹 사이트와 현대 웹 사이트를 보면 기능면에서 많은 차이가 있습니다. 

Airbnb를 예를 들자면, 사용자의 입력을 받아 달력을 표시하고, 일정을 선택하면 해당 숙소의 사용 여부를 체크 및 숙소의 위치정보를 맵으로 표시하는 등의 많은 처리가 한 화면에서 일어납니다. 

결국 이 과정들을 페이지별로 쪼개어 사용자에게 표현해주는 것이 아니라, 한 화면이나 특정 화면 범위 안에서 유동적이면서도 즉각적으로 반응을 해줘야 사용자 입장에서는 불필요한 대기시간을 줄이게 되는 것이죠. 


이러한 동적인 화면 처리가 사용자에게 제공하는 Rich Experience(풍부한 경험)이라고 볼 수 있을 것 같습니다. 
달리 말해 화면의 불필요한 깜빡거림을 줄이거나 매끄러운 화면전환 등을 의미합니다.


자 그럼 그렇게 화면에서의 사용자 경험 향상 이외에 더 편하게 웹을 사용하기 위해 또 어떠한 노력들이 현재 진행되고 있을까요?

바로 Progressive Web Apps입니다. Google에서 2015 년에 발표한 새로운 형태의 진보한 웹 앱 인데요. 한 문장으로 요약하자면 “최적화된 웹 성능에 모바일의 Native 기능을 결합한 최신 웹 앱” 입니다. 

모바일 기기가 보급화되면서 PC Web 보다는 Mobile Web 으로 접속하는 사용자들이 훨씬 많아졌는데요. 

이 사용자들이 웹에서 더 머무르고 다시 웹을 접속하기 수월하게끔, 
웹 사이트에 App Icon & Install Banner & Push Notification 을 추가하여 모바일 앱을 설치하지 않고도 웹을 모바일 앱처럼 접근할 수 있는 편이성을 제공


모바일 앱의 “개발 -> 배포 -> 검색 -> 설치 -> 접속” 의 싸이클을 “개발 -> 배포 -> 검색 (설치 & 접속)” 으로 간편화 하여, 개발자 입장에서나 사용자 입장에서 앱스토어에 올리고 검색해서 다운로드하는 번거로운 시간들을 줄여주는 거죠. 
이런 간편함으로 인해 Web App 이 점점 Native App 의 시장을 침범하고 있습니다. 








JavaScript 와 Java는 근본적으로 다릅니다. 

초기에 자바스크립트는 Mocha라는 이름으로 개발되다 추후에 Livescript라는 이름으로 변경되었다.
그러다 자바라는 언어가 인기가 많아지자 그 인기에 편승할 목적, 즉 마케팅 목적으로 자바스크립트라는 이름으로 변경 후 세상에 나오게 되었다.
자바가 인기가 많으니 묻어가자 

HTML이 한번 화면에 출력된 후에는 그 형태나 동작방법을 바꿀 수 없는 문제를 해결하기 위해서 네스케이프에서 만들어졌다.
이후에 이 언어는 ECMA라는 표준화 기구로 이 언어의 관리 주체가 옮겨졌다.

HTML과 CSS는 정적인 언어입니다. 정적이라는 것은 이것들이 브라우저를 통해서 웹페이지를 화면에 그려주면 이 화면을 변경할 수 있는 방법이 없다는 의미입니다. 

Javascript는 HTML과 CSS로 만들어진 웹페이지를 동적으로 변경해주는 언어입니다. 경고창을 띄우고, 탭인터페이스를 만들고, Drag & Drop 기능의 웹에플리케이션을 만들수 있는거죠. 


웹 개발을 위해 HTML, CSS와 필수적으로 사용 (기본적인 선행학습 필요)
별도 환경설정 필요없이 브라우저에서 바로 실행 가능

사용자 인터렉션에 따른 웹 페이지의 동적 제어 (메뉴, 슬라이드)

## 자바스크립트의 역할
자바스크립트의 일반적인 용도는 웹 페이지에 기능을 더해 HTML 웹 페이지를 동적이고 살아 있게 만드는 것이다.

HTML 페이지 변경 및 HTML 엘리먼트와 콘텐츠의 추가나 제거
CSS 및 HTML 엘리먼트의 스타일 변경
사용자와의 상호작용(인터랙션: Interaction), 폼의 유효성 검증
마우스/키보드 이벤트에 대한 스크립트 실행
웹 브라우저 제어, 쿠키 등의 설정과 조회
AJAX 기술을 이용한 웹 서버와의 통신

HTML 구조를 조작(DOM 변경)
CSS를 동적으로 변경
사용자가 키보드/마우스 이벤트를 발생하면 처리
클라이언트 측 데이터를 변경/검증 할 수 있습니다.


## 프로그래밍 언어로써의 특징
(1) 스크립트 언어이다.
스크립트 언어는 중요한 부분만 간추려 간략화한 것을 목적으로 만들어진 프로그래밍 언어
이미 다른 언어를 배운 개발자나 처음 프로그래밍을 하는 사람도 단기간에 익힐 수 있다. (러닝커브가 높지 않음)

(2) 인터프리터형 언어이다.
프로그램을 실행하기 위해 컴파일 같은 별도의 절차는 필요 없음
코드를 작성하고 그대로 실행할 수 있는 간편함이 장점

(3) 다양한 환경에서 사용이 가능하다.
브라우저에서만 사용하는 용도를 벗어나 다양한 환경에서 실행되고 있다.
서버 - NodeJs
데이터베이스 - MongoDB
데스크탑 어플리케이션 - Electron (일렉트론)
모바일 어플리케이션 - React Native



디자인요소: View - HTML,CSS
행동, 데이터: Model - JS

OOP in Javascrit
Class는 없음
상속있음 (prototype chain)
다형성 있음 (duck typing)
방식이 다를 뿐 엄연한 객체지항적 언어

jQuery, 앵귤러, 리액트 
capy & paste


## 발전 과정 - Ajax 기술의 등장과 Node.js 등장으로 Javascript의 전성기를 맞이


브라우저 위에 경고 대화창을 띄우거나 웹 페이지의 사이드바를 열고 닫는 용도로만 사용되던, 장난감 같은 언어

Javascript의 비동기 처리 (Ajax)가 나온 시점부터 자바스크립트가 앞 화면의 MVC Framework으로 발전하고, 
화면 뒷단에서 서버의 역할을 할 수 있는 Javascript Runtime Environment (Node.js)을 거쳐, 이제는 모바일 영역의 기능들까지 넘보는 Progressive Web App으로 꾸준히 진화


1990년대 후반 초기 JavaScript의 전성기라고 할 수 있었다.

요소에 마우스 포인터를 가져가면 문자열이 깜박인다
상태 표시줄에 문자열을 보여준다.
페이지 전환 시 페이드인/아웃 등의 전환 효과를 적용할 수 있다.
문자열 흘러가기, 페이드 인 아웃의 화면전환 효과 등의 용도록 사용되기 시작

1990년대 후반: Javascipt 전성기
대부분의 웹 페이지에 마우스를
상태바에 문자열 흘러가기, 페이지 전환 시 페이드 인 아웃의 화면전환 효과 등의 용도록 사용되기 시작

2000년대 초반 Javascipt 후퇴기
모양새가 안 좋은 웹페이지 장식을 위한 언어, 프로그래밍 초보자나 사용하는 저한 언어의 이미지,
크로스 브라우징 문제와 보안 취약점 문제로 하여 나쁜 이미지가 정착

2000년대 중반 Javascirpt 도약기
Ajax (Asynchronous + XML) 기술이 등장하고 Javascript 국제 표준화 단체인 ECMA하에 표준화가 진행되어 언어로서의 완성도가 높아짐

2010년대 초반  :Javascipt 부흥기
2000년대 후반 NodeJS의 등장으로 서버부터 클라이어트까지 전 영역에  Javascript 활용가능
HTML5등장으로 Javascript와 함께 웹 어플리케이션 개발이 가능해 짐

웹이 나오게된 배경 중 하나가 문서 표현 및 전달에 있었기 때문에 초창기 표준 기술은 HTML이나 XML같이 문서를 표현하거나 전달하기 위한 기술이 중심이었다. 이후 웹은 쇼핑이나 뱅킹 등 기존에 오프라인으로만 가능하던 여러 분야에서 사용되기 시작하면서 다양한 분야에서 폭넓게 활용되기 시작했다.

​

이 같은 변화에서 중요하게 쓰이는 기술이 ECMA그룹에서 제정한 ECMA262 스펙과 이를 반영한 스크립트 언어인 자바스크립트다

자바스크립트는 인터프리팅 방식을 사용하고, C++이나 자바같은 정적인(Static) 언어가 아니라 동적 언어이기 때문에 보다 유연하며 추상화(abstraction)나 위임(delegation) 등의 메커니즘이 프로토타입(prototype) 객체나 함수를 통해 구현이 가능하다. 독특한 구조의 유효범위(scope)와 이를 보완하기 위한 클로저(closure)기법 등은 개발을 더욱 편리하게 하고 기능 구현에 풍부함을 더할 수 있도록 돕는다.

## AJAX
AJAX 비동기 JavaScript와 xml의 약어입니다. AJAX는 webpage를 새로 그리지 않고, JavaScript를 이용하여 data를 주고 받을 수 있습니다.

본격적으로 JavaScript Framework이 발전한 것은 AJAX기술이 대두되기 시작할 때 입니다. 이전에 정적인 page에서 벗어나, 적은 data로 새로운 부분만 새로 화면을 수정하는 동적인 page가 만들어지기 시작했습니다. 그렇지만, 초기에 AJAX는 한 마디를 개발자들에게는 지옥이었습니다. 많은 코딩량과 디버깅의 어려움, 그리고, 무엇보다도 AJAX를 지원하는 제대로 JavaScript framework이 없었습니다. 이는 필연적으로 jQuery와 Angular.js와 같은 JavaScript Framework 출현을 불러왔습니다.

## jQuery

jQuery는 JavaScript에서 공통적인 작업을 간편하게 자동화 시킨 library입니다. jQuery와 비슷한 library가 많지만, 이전 버전의 browser에서도 잘 동작하기 때문에, 확실히 뛰어 올랐습니다. jQuery는 JavaScript와 함께 사용이 욉니다. 주로 평범한 JavaScript로는 어려운 동적 움직임과 AJAX를 몇 줄로 코딩으로 해결 할 수 있습니다.

jQuery가 널리 보급되면서, 더 이상 AJAX와 동적 움직임을 처리하는 것이 고된 작업이 아니었습니다. 기존의 악명을 많이 떨치고, 이제는 거의 웹 표준으로 자리 잡았습니다. 그렇지만, 여전히 Model과 View처리 부분에서는 다소 아쉬움이 남아 있어 이는 본격적인 JavaScript Framework를 시대를 이끌게 됩니다.

## NodeJS
 만약 여러분이 웹프로그래밍을 하려고 한다면 자바스크립트는 사실상 필수라고 할 수 있습니다.
최근에는 node.js라는 서버측 자바스크립트가 각광받고 있습니다. 또한 MongoDB와 같은 친 JavaScript 데이터베이스를 사용하면 클라이언트부터 서버 그리고 데이터베이스까지 모든 부분을 JavaScript 기반으로 구현할 수 있습니다. 또한 구글 Apps 스크립트등의 사례에서도 볼 수 있듯이 자바스크립트는 다양한 플랫폼을 프로그래밍적으로 제어하기 위한 도구로 폭넓게 채택되고 있습니다. JavaScript의 시대라고 할만합니다.

공통적인 불만 : 대/소문자 민감성, 브라우저마다 다른 구현, 디버깅 기능의 부재(파이어버그로 해결 가능), 이상한 상속 규칙.
평가 : “유별난 프로토타입 기반 상속, 모듈성의 결여, 그리고 이상한 “this” 처리 방법이 싫다.” - ladimir
피하는 방법 : 웹 개발자로 일하지 않는다.



## AngularJS, React, Vue
이 라이브러리 를 사용하면 단일 페이지 응용 프로그램을 더욱 쉽고 효과적으로 만들 수 있습니다.



이런 다양한 효과가 JavaScript의 중요한 용도였고 알맞게 이용하면 페이지 모양과 느낌을 향상할 수 있었다. 하지만 아쉽게도 당시에 이것이 과열되는 양상을 띠며 동작인 페이지를 만들겠다는 형태로 발전하게 되면서 과도한 형태로 JavaScript를 사용하게 되었다. 
그 결과 느리고 지저분해진 페이지가 양상 되었다.  
이런 과열된 부분은 점차 오래 지속되지  않았고, JavaScript는 페이지에 입력 확인용 스크럽트 언어나 초보 개발자가 이용할 수 있는 언어라는 이미지가 만들어져 우울한 시대로 들어갔다.

이후 브라우저 제공업체가 개별적으로 JavaScript구현을 확장하던 시대이기도 했다. 더 눈에 들어오도록 화려한 기능 위주로 발전함에 따라 브라우저별로 사양 차이(크로스 브라우징 문제)가 커져갔다. 따라서 사용자는 각각의 브라우저를 지원하는 코드를 만들어야 했고, 그런 번거로움 때문에 JavaScript는 사용자와의 갭이 더 커졌다. 이 시대의 JavaScript 구현에 관련된 브라우저의 보안 문제도 간헐적으로 발견된 것도 JavaScript의 부정적인 이미지를 더 정착시키는 요인이 되었다.

다시 컴백하게 된 계기를 만들어준 Ajax와 HTML5의 시대
이런 상황에서 2005년 Ajax(Asyncronous JavaScript + XML)이라는 기술이 등장하게 된다. Ajax는 한마디로 브라우저에서 데스크톱 응용프로그램 와 유사한 페이지를 만드는 기술이다. HTML, CSS, JavaScript 등의 브라우저 표준 기술만으로 다양한 콘텐츠를 만들 수 있어 Ajax는 빠르게 인기를 얻었다.

요즘 브라우저 개발사도들도 경쟁을 거의 하지 않게 되고 호환성 문제도 크게 일어나지 않았다. 국제 표준화 단체인 ECMA International에서 JavaScript를 표준화가 진행되면서 확실한 진화가 이루어졌다. 이런 배경을 통해 JavaScript의 언어로써의 가치를 다시 검토할 기회를 얻었다.

또한, 2000년대 후반에는 HTML5의 등장으로 상황은 더 좋아졌다. HTML5는 마크업으로서 충실하고 응용프로그램 개발을 위한 JavaScript API를 강화한 것이 특징이다. HTML5 권고 자체는 2014년이지만, 2008년 이후 출시된 브라우저 대부분은 HTML5를 대응하여 단계적으로 이용이 가능했다.

## JavaScript에 대한 오해들
JavaScript는 Java나 C#과 같은 프로그래밍 언어뿐만 아니라 엄연한 객체지향 언어이다. 실제로 JavaScript가 Ajax기술의 핵심으로 떠오르면서 이후 프로그래밍 스타일 자체도 많은 변화가 생겼다. 기존의 절차적 프로그래밍 기법에서 본격적인 객체지향 코딩 스타일을 요구하게 되었다. 
다음으로 JavaScript는 보안상 문제가 있다는 것이다. 이는 어떻게 보면 맞는 이야기라고 생각할 수 있지만 좀 더 따져보면 JavaScript의 문제가 아닌 JavaScript를 구현한 브라우저의 문제였다. 즉, 언어로써의 문제가 있는 것은 아니라는 것이다. 또한 브라우저 제조사들도 보안의식이 높아졌고 현재는 보안 문제는 크게 줄었다.

그리고 JavaScript에는 크로스 브라우저 문제가 있어, 개발 생상성이 낮다는 말들이 있는데 이것도 브라우저의 구현 문제이다. 또한 다시 이야기하지만, 표준화 통일을 가져가고 있어 호환성 문제는 감소 중이다.

이런 오해들을 줄이다 보면, JavaScript는 쉽게 도입할 수 있고 대중화한다는 의미에서 초보자들이 학습하기 편한 언어라고 말할 수 있다. 또한 Ajax 및 HTML5가 보급됨에 따라 웹 개발자들은 다시 JavaScript라는 언어에 대한 이해를 요구하고 있다.



프로토타입에 기반한 프로그래밍은 객체 지향 프로그래밍의 스타일이며, 
(상속으로 알려진) 동작 재사용은 프로토타입으로 제공되는 이미 존재하는 객체를 복제하는 과정을 수반한다.





## 쓰이는 곳 활용범위 확대
SPA
웹브라우저
서버 node.js
MongoDB
윈도우 프로그램 일렉트론
앱 리액트네이티브

## 왜 쓰는가
웹 페이지를 좀 더 동적으로 만들어 보기 위해



## 특징
사용자 액션에 따라 DOM을 일일이 다루는 개발 방식(jQuery)과는 달리 개발자가 DOM을 직접 다루지 않고 


## Namespacing
* 팀 프로젝트 시 많은 양의 자바스크립트 코드를 작성할 때, 타 팀원이 작성한 전역변수가 overwrite 되는 경우가 발생한다.
* 이를 막기 위해 namespacing 을 활용한다.


자바스크립트 적용 방법 internal
html 스크립트 태그안에 작성
<script>
    alert('Hello world!');
</script>

external
js파일을 생성 후 작성한 뒤 임폴트
<script src="test.js"></script>

## 스크립트 태그 위치는 어디가 좋을까?
우리가 보는 웹페이지는 싱글쓰레드 방식
쉽게 말해서 뭐 하나 하면 다른일을 못하는 스타일
그래서 브라우저가 js를 읽는 동안은 다른 일을 못함
js가 하단에 있으면 HTML, CSS 다 그리고 나서 다운받고 읽겠죠
사용자 입장에서 생각해보면 흰화면에서 기다리는 것보다는
뭐라도 먼저 살짝 보이는게 반응속도가 빨라 보이겠죠
위치를 꼭 반드시, 머스트 지키지 않아도 되지만 가급적 용량이 크거나
복잡한 코드는 하단에 위치


## JS Data type 변수 선언
Number, String, Boolean, Array, Object -> var
심지어 var를 생략해도 된다?!
test = 3;
글로벌로 변수 선언됩니다. 


제이쿼리 간단한 사용방법 비교
순수 스크립트랑 코드 비교

#자바스크립트 데모를 통한 제이쿼리
메뉴 툴팁 토글
아코디언
라이브러리 사용법 BX슬라이드 라이브러리 선정방법(깃스타 최신업데이트 유지 여부)
aJax처리 방법 done().done()


## 개발자들이 자주하는 실수
블록 vs. 함수 유효범위
C, JAVA등의 유효범위는 {} Block
블록이 끝났다고 유효범위가 끝나지 않는다
자바스크립트의 유효범위는 함수

변수 중복 선언 시 기존 변수를 덮어 버립니다.
호이스팅 끌어올림
변수 선언 시 체크 

```js
var a = a || {};
```




## 자바스크립트 Hoisting 이란???
 'hoist = 끌어올리다' 라는 뜻으로 자바스크립트에서는 변수 선언과 함수 선언은 해당 유효범위의 가장 최상위로 끌어 올려짐을 의미합니다.

 변수의 선언이 초기화나 할당시에 발생하는 것이 아니고, 유효범위의 최상위로 호이스트 되는 것입니다. 유효 범위 안에서 변수에 할당한 값을 활용하고 싶을 때에는 항상 유효범위의 최상위에 선안하고 값을 초기화 해주도록 하는 것이 자바스크립트의 호이스팅기능으로 인해 발생할 수 있는 문제들을 조금이나마 줄여줄 것 입니다.


## 자바스크립트의 Scope chain
  자바스크립트는 변수를 찾을 때 스코프의 계층 구조에 기반한 검색 체인을 거슬러 올라가며 추적하게 됩니다.

  그림에서 보면 console.log를 통해 "scopeChain"을 찍어 내는 모습을 볼 수 있습니다. console.log를 func2 스코프에 쓰여있지만 실제로 자바스크립트 scope chain을 통해 전역 스코프의 scopeChain 변수에 접근에 값을 출력하게 됩니다. func2 함수 스코프 내에 포함되어 있지 않은 scopeChain 값을 찾는 과정은 먼저 func2 함수에서 scopeChain 라는 변수를 찾게 되고, 이 값이 없으면 func2 의 부모 함수인 func1에서 검색을 하게 되고 여기에도 없으면 func1 의 부모 함수가 없기 때문에 전역 스코프에서 값을 찾게 됩니다. 
  전역 스코프에서 scopeChain을 발견하게 되면 이 값을 func2로 전달하게 되는 것을 자바스크립트의 scopeChain의 핵심 역할 입니다. 
  만약 전역 스코프에도 해당 내용이 정의되어 있지 않았다면 자바스크립트는 undefinded를 반환하게 됩니다. 

var number1 = 1;
var func1 = function(){
    var number2 = 2;
    var func2 = function(){
        var number3 = 3;
        console.log(number1 + number2 + number3); //6
        //number3 지역 스코프, number2, number1은 스코프 체인에서 찾게된다.
    }();
}();

그림에서 보듯이 console.log는 func2에서 수행되고 있으면 "number1 + number2 + number3"의 연산을 수행하게 됩니다. 각각의 변수들은 각기 다른 스코프에서 선언이 되었습니다. 자바스크립트는 scope chain을 통해 해당 변수들을 찾게 되고 number3, number2, number1의 순서로 chain을 통해 접근하여 값을 func2 함수로 전달하여 연산을 수행하게 됩니다. 이렇듯 func2 함수에서 참조한 변수는 지역 스코프에 없을 경우 스코프 체인에서 변수를 검색하게 되며 스코프 체인을 검색할 때는 가장 처음 발견한 값을 반한하게 됩니다. (예를 들어 위에 number1, number2 의 명칭을 number3으로 변경해 주게 되면 console.log에는 9가 찍히게 됩니다.)

이렇듯 스코프 체인을 검색할 때는 가장 처음 발견한 값을 반환하게 되므로 상위 범위에 대해서는 검색을 하지 않고 연산을 수행하여 9가 찍히게 됩니다. 

var number3 = 1;
var func1 = function(){
    var number3 = 2;
    var func2 = function(){
        var number3 = 3;
        console.log(number3 + number3 + number3); //9
    }();
}();


스코프 체인은 함수를 실행한 위치가 아닌 정의한 위치에 의해 결정되어 집니다. 이를 가리켜 문법적 스코핑(lexical scoping)이라고도 합니다. 스코프 체인은 함수를 호출하기 전에 이미 만들어지며, 이 덕분에 우리는 클로저(closure)를 만들 수 있게 됩니다. 





 자바스크립트에서는 scope chain을 통해서 연결이 가능하게 됩니다. 내부 함수는 자신이 선언된 환경에 대한 연결을 갖게 됩니다. 다시 말해 foo() 함수가 클로져를 갖게 됩니다. 클로져는 두개의 것으로 이루어진 특별한 오브젝트로 첫 번째는 함수, 두 번째는 그 함수가 만들어진 환경을 가지게 됩니다. 그 함수가 만들어진 환경은 함수가 만들어질 때 사용할 수 있었던 변수들로 이루어지고 이 경우에 foo()함수는 sequencer의 내부 함수와 seq 변수를 포함하는 클로져가 됩니다. 

var add = function() {
    var counter = 0;
    return function() {
        return ++counter;
    };
};

var foo = add();
foo(); //1 
foo(); //2
foo(); //3


우리 모두는 자신의 힘으로 발견한 내용을 가장 쉽게 익힌다.(“The Art of Computer Programming”의 저자 도널드 커누스) https://ko.wikipedia.org/wiki/%EB%8F%84%EB%84%90%EB%93%9C_%EC%BB%A4%EB%88%84%EC%8A%A4
클로져는 함수 안의 또 다른 함수를 이용해 하나의 독립된 스코프를 생성하는 메카니즘이다.
​
​
코드에 대해 설명 해 줄 수 있는가?
counter 함수를 실행 함으로써 add 함수가 반환되는데 중요한 점은 counter 함수가 실행 된 후에도 반환된 내부 함수를 통해 count 변수에 접근이 가능 하다는 것이다. 즉, count 변수와 반환된 함수를 포함하는독립된 환경이 생성된 것이다.
​
알겠다. 하지만 그 독립된 환경이라는 것이 가져다 주는 특별한 의미가 있는가?
자바스크립트 코어에는 private 함수나 변수의 개념이 없다. 클로져를 이용해 이런 private 함수나 변수를 만들 수 있게 된다.

변수 counter는 외부에서 직접 접근할 수 없는 private 변수이므로 전역 변수를 사용했을 때와 같이 의도되지 않은 변경을 걱정할 필요도 없다.
​




                    https://blog.asamaru.net/2017/05/04/script-async-defer/
                    defer


                    <section>
                        <h2>전역변수 or 지역변수</h2>
                        <p></p>
                        <pre><code class="js">
            //암묵적 전역
            //var 키워드 생략 시 전역변수로 인식
            foo = '';
                        </code></pre>
                    </section>



jQuery 라이브러리의 목표는 웹 브라우저 마다 다르게 작성해야 되는 크로스 브라우저 자바스크립트 코드[2]를, jQuery 라이브러리를 사용하여 최대한 쉽게 작성할 수 있도록 해 주는 것이다.




```css
.blind{overflow:hidden;position:absolute;top:0;left:0;width:1px;height:1px;font-size:0;line-height:999em}
.tit{text-align:center}
.slide_wrapper {position:relative;max-width:376px;margin:0 auto;height:609px}
.slide_wrapper .slide_container .slide{float:left;width:376px;height:609px}
.slide_wrapper .bx-controls{position:absolute;left:0;bottom:0;text-align:center}
.slide_wrapper .bx-controls .bx-pager-item{display:inline-block;padding:0 5px}
.slide_wrapper .bx-controls a{color:#fff}
.slide_wrapper .slide_button{position:absolute;z-index:2010;width:100px;height:100px;background-color:transparent;background-position:center center;background-repeat:no-repeat;overflow:visible;border:0 none;border-radius:0;cursor:pointer}
.slide_wrapper .button_prev{top:50%;left:0;margin-top:-50px;background-image:url(http://static.ssgcdn.com/ui/sm/img/promotion/2016/160104_shopat/mobile/m_btn_left.png)}
.slide_wrapper .button_next{top:50%;right:0;margin-top:-50px;background-image:url(http://static.ssgcdn.com/ui/sm/img/promotion/2016/160104_shopat/mobile/m_btn_right.png)}
.slide_wrapper .button_top{top:0;left:50%;margin-left:-50px;background-image:url(http://static.ssgcdn.com/ui/sm/img/promotion/2016/160104_shopat/mobile/m_btn_top.png)}
.slide_wrapper .button_bottom{bottom:0;left:50%;margin-left:-50px;background-image:url(http://static.ssgcdn.com/ui/sm/img/promotion/2016/160104_shopat/mobile/m_btn_bottom.png)}
```

```html
<h3 class="tit">가로형 슬라이드</h3>
<div id="horizontal" class="slide_wrapper">
    <div class="slide_container">
        <div class="slide"><img src="http://static.ssgcdn.com/ui/sm/img/promotion/2016/160104_shopat/mobile/m_sa_01.jpg" alt=""></div>
        <div class="slide"><img src="http://static.ssgcdn.com/ui/sm/img/promotion/2016/160104_shopat/mobile/m_sa_02.jpg" alt=""></div>
        <div class="slide"><img src="http://static.ssgcdn.com/ui/sm/img/promotion/2016/160104_shopat/mobile/m_sa_03.jpg" alt=""></div>
        <div class="slide"><img src="http://static.ssgcdn.com/ui/sm/img/promotion/2016/160104_shopat/mobile/m_sa_04.jpg" alt=""></div>
        <div class="slide"><img src="http://static.ssgcdn.com/ui/sm/img/promotion/2016/160104_shopat/mobile/m_sa_05.jpg" alt=""></div>
        <div class="slide"><img src="http://static.ssgcdn.com/ui/sm/img/promotion/2016/160104_shopat/mobile/m_sa_06.jpg" alt=""></div>
        <div class="slide"><img src="http://static.ssgcdn.com/ui/sm/img/promotion/2016/160104_shopat/mobile/m_sa_07.jpg" alt=""></div>
    </div>
    <button class="button_prev slide_button"><span class="blind">이전</span></button>
    <button class="button_next slide_button"><span class="blind">다음</span></button>
</div>


<h3 class="tit">세로형 슬라이드</h3>
<div id="vertical" class="slide_wrapper">
    <div class="slide_container">
        <div class="slide"><img src="http://static.ssgcdn.com/ui/sm/img/promotion/2016/160104_shopat/mobile/m_sa_01.jpg" alt=""></div>
        <div class="slide"><img src="http://static.ssgcdn.com/ui/sm/img/promotion/2016/160104_shopat/mobile/m_sa_02.jpg" alt=""></div>
        <div class="slide"><img src="http://static.ssgcdn.com/ui/sm/img/promotion/2016/160104_shopat/mobile/m_sa_03.jpg" alt=""></div>
        <div class="slide"><img src="http://static.ssgcdn.com/ui/sm/img/promotion/2016/160104_shopat/mobile/m_sa_04.jpg" alt=""></div>
        <div class="slide"><img src="http://static.ssgcdn.com/ui/sm/img/promotion/2016/160104_shopat/mobile/m_sa_05.jpg" alt=""></div>
        <div class="slide"><img src="http://static.ssgcdn.com/ui/sm/img/promotion/2016/160104_shopat/mobile/m_sa_06.jpg" alt=""></div>
        <div class="slide"><img src="http://static.ssgcdn.com/ui/sm/img/promotion/2016/160104_shopat/mobile/m_sa_07.jpg" alt=""></div>
    </div>
    <button class="button_top slide_button"><span class="blind">이전</span></button>
    <button class="button_bottom slide_button"><span class="blind">다음</span></button>
</div>
```


```js
    var welHorizontal = $('#horizontal');
    var welHorizPrev = welHorizontal.find('.button_prev');
    var welHorizNext = welHorizontal.find('.button_next');
    var oHorizontal = welHorizontal.find('.slide_container').bxSlider({
        mode: 'horizontal',
        controls: false,
        pager: false,
        infiniteLoop: false
    });

    welHorizPrev.on('click', function() {
        var curSlideIndex = oHorizontal.getCurrentSlide();

        if(curSlideIndex === 0){
            alert('처음 슬라이드 입니다.');
        } else {
            oHorizontal.goToPrevSlide();
        }
    });

    welHorizNext.on('click', function() {
        var curSlideIndex = oHorizontal.getCurrentSlide(),
            lastSlideIndex = oHorizontal.getSlideCount() - 1;

        if(curSlideIndex === lastSlideIndex){
            alert('마지막 슬라이드 입니다.');
        } else {
            oHorizontal.goToNextSlide();
        }
    });


    var welVertical = $('#vertical');
    var welVerticalPrev = welVertical.find('.button_top');
    var welVerticalNext = welVertical.find('.button_bottom');
    var oVertical = welVertical.find('.slide_container').bxSlider({
        mode: 'vertical',
        controls: false,
        pager: false,
        infiniteLoop: false
    });

    welVerticalPrev.on('click', function() {
        var curSlideIndex = oVertical.getCurrentSlide();

        if(curSlideIndex === 0){
            alert('처음 슬라이드 입니다.');
        } else {
            oVertical.goToPrevSlide();
        }
    });

    welVerticalNext.on('click', function() {
        var curSlideIndex = oVertical.getCurrentSlide(),
            lastSlideIndex = oVertical.getSlideCount() - 1;

        if(curSlideIndex === lastSlideIndex){
            alert('마지막 슬라이드 입니다.');
        } else {
            oVertical.goToNextSlide();
        }
    });
```






