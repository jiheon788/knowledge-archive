# Node.js란?

> Node.js는 Chrome V8 JavaScript 엔진으로 빌드 된 `JavaScript 런타임`입니다.

자바스크립트는 독립적인 언어가 아닌 스크립트 언어이다. 스크립트언어는 특정한 프로그램 안에서 동작하는 프로그램이기 때문에 웨 브라우저 프로그램 안에서만 동작한다. 즉 웹 브라우저(크롬, 사파리 등)가 없으면 사용할 수가 없는데 이것이 Node.js가 나온 이유이다.

자바스크립트를 웹 브라우저에서 독립시킨 것으로 터미널프로그램에서 브라우저 없이 실행이 가능해졌다. 이를 이용해 서버를 만들 수 있게 되었다. -> 한가지 언어로 웹페이지를 만들수 있게 됨

- Node.js는 노드를 통해 다양한 자바스크립트 애플리케이션을 실행할 수 있다.
- Node.js는 자바스크립트를 서버에서도 사용할 수 있도록 만든 프로그램
- Node.js는 V8이라는 자바스크립트 엔진 위에서 동작하는 자바스크립트 런타임(환경)
- Node.js는 서버사이드 스크립트 언어가 아닌 프로그램(환경)이다.
- Node.js는 웹서버와 같이 확장성있는 네트워크 프로그램을 제작하기 위해 만들어짐
- Node.js는 확장성 잇는 네트워크 어플리케이션 개발에 사용되는 소프트웨어 플랫폼
- 사용언어: 자바스크립트
- 특징: Non-blocking I/O, 단일스레드, 이벤트 루프

## 자바스크립트 런타임

런타임이란 특정언어로 만든 `프로그램을 실행할 수 있는 환경`을 뜻한다. 따라서 노드는 자바스크립트 프로그램을 컴퓨터에서 실행할 수 있게하는 `자바스크립트 실행기`이다.

## 이벤트 기반(Event-driven)

노드는 V8과 더불어 libuv라는 라이브러리를 사용하는데 이는 노드의 특성인 이벤트기반, 논블로킹I/O 모델을 구현하고 있다. 이벤트기반이란 이벤트가 발생할 때 미리 지정해둔 작업을 수행하는 방식을 말한다. 즉 이벤트 기반 시스템에서는 특정 이벤트가 발생할 때 무엇을 할지 미리 등록해두고 이를 이벤트리스너에 콜백함수로 등록한다.

i. 이벤트 리스너에 콜백함수 등록  
ii. 이벤트 발생  
iii. 콜백함수 호출  
iiii. 이벤트가 끝난 후 노드는 다음 이벤트 발생할 때까지 대기

## 이벤트 루프

본 문서의 [Event Loop 이란?](../javascript/event-loop.md)에서 다루었다.

이벤트 루프는 여러이벤트가 동시 발생할 때 어떤 순서로 호출 할지 이벤트루프가 판단한다. 노드는 이벤트가 종료될 때까지 이벤트 처리를 위한 작업을 반복하므로 루프라고 부른다. 이를 활용하여 오래 걸리는 작업을 효율적으로 처리한다.

## 논 블로킹 I/O

작업에는 `동시에 실행가능한 작업`, `동시 실행 불가능한 작업` 두가지가 있다.
입력/출력(파일시스템접근, 네트워크 요청 등)과 같은 작업을 할 때 노드는 비동기 방식으로 블로킹을 만들지 않게 끔 처리한다. -> 논블로킹  
즉, 함수 호출 시 당장 실행하는 것이 아닌(동기->블로킹) 어느 곳에 쌓아 두고 동시에 요청을 처리(비동기->논블로킹) 요청이 완료된 순서대로 처리한다.

- 비동기: 이전 작업이 완료될 때까지 대기하지 않고 동시에 작업을 수행한다.
- 동기: 이전 작업이 끝나야만 다음 작업을 수행한다.

## 싱글 스레드

Node.js는 싱글스레드, 논 블로킹 모델로 싱글 스레드가 혼자서 일을 처리하지만 들어오는 요청 순서가 아닌 논 블로킹 방식으로 이전 작업이 완료될 때까지 대기하지 않고 다음 작업을 수행한다.

- 프로세스 : 운영체제에서 할당하는 `작업의 단위`이다. 노드나 웹 브라우저 같은 프로그램은 개별적인 프로세스이다. 프로세스 간에는 메모리 등의 자원을 공유하지 않는다.

- 스레드 : 스레드는 프로세스 내에서 실행되는 `흐름의 단위`이다. 프로세스는 스레드를 여러 개 생성해 여러 작업을 동시에 처리할 수 있다. 스레드들은 부모 프로세스의 자원을 공유한다. 같은 주소의 메모리에 접근 가능하므로 데이터를 공유할 수 있다.

#### Reference

- [https://hanamon.kr](https://hanamon.kr/nodejs-%EA%B0%9C%EB%85%90-%EC%9D%B4%ED%95%B4%ED%95%98%EA%B8%B0/)

<div align="right">- CreatedAt 2022.12.15</div>

---

[Back](../README.md)
