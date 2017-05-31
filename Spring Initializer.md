# 스프링부트 프로젝트를 만드는 방법
1. 웹페이지를 이용하는 방법

```
start.spring.io에 접속
1. Maven이냐 Gradle이냐 선택
2. Spring Boot 버전 선택
3. Group(package 이름), artifact 작성
4. Dependencies 선택(application 특성마다 미리 만들어 놓은 것)
5. 풀버전으로 바꿔서 세부사항 조작도 가능
6. 생성하면 zip파일로 받아서 압축해제
7. maven 프로젝트로 기본구조 설계되어있음
8. src-main-java-com-example : default package 주로 개발할곳
9. src-resources-static : css, javascript, image 들이 들어가는 곳
```
2. 터미널에서 Spring CLI Tool 이용하기

```
spring init -list : 프로젝트 만들기 전 선택할 수 있는 설정들 보기
spring init -d=web my-app : dependencies package이름

```

3. 터미널에서 curl 이용하기

```
curl start.spring.io
Spring CLI Tool과 비슷한 것이 나온다.
```

4. Intellij 이용하기

```
1. create new Project
2. Spring Initializer 를 사용하면 됨.
3. GUI라 편하고 디버깅모드를 사용할 수도 있음.
4. src/main/java/com.example 폴더에 java class 생성
```

```Java
package com.example;

import org.springframework.web.bind.annotation.RequestMapping;
import org.springframework.web.bind.annotation.RestController;

@RestController // (1)
public class HomeController {

  @RequestMapping("/") // (2)
  public String home() {
    return "Hello, Spring Boot!";
  }
}

```
