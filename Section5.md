Spring MVC
model : representing the application data
view : interface that renders that model
controller : kind of acts as a traffic controller between the model and the view


컨트롤러들
@controller
@RestController
리퀘스트맵핑
@RequestMapping("/")


Spring Application Class
메인파일

resources폴더
static폴더
그림이나 html파일같은 것 넣어두는곳
templates폴더
템플릿 엔진들 넣어두는곳

java 폴더 클래스폴더에
config, controller, service 팩키지 생성
기본작업모형임
service에는 개발한 코드를 넣는곳

index.html과 RestController가 디폴트로 같이 있으면 RestController가 실행됨

RestController와 controller의 차이점?
레스트컨트롤러는 응답에 즉각적으로 반응하길 기다림?

@SpringBootApplication에 들어있는 3개의 공통 annotations
@Configuration
@EnableAutoConfiguration
@ComponentScan


Static Content
html, css, javascript, images

webjar
부트스트랩이나 제이쿼리같은 라이브러리들을 사용할때 클라이언트 쪽에 dependency를 추가해서 사용하는 방법
www.webjars.org 사이트
```css
<link href="webjars/bootstrap/3.3.5/css/bootstrap.min.css" rel="stylesheet" />
```

Bower
package manager for the webjars

grunt

Template Engines

thymeleaf
타임리프는 내츄럴 템플릿 엔진이다
기본 문법
```
<title th:text="${pageTitle}">Blog Post - List</title>
```
기존 내용이 th로 덮어씌워진다.
```
Variable Expressions ${...}
Selection Variable Expressions *{...}
Message Expressions #{...}
Link URL Expressions @{...}
```

application.properties에
spring.thymeleaf.cache=false 해주는것 잊지 말고 해주자(왜 해주는거지?)

<html lang="en"
  xmlns="http://www.w3.org/1999/xhtml"
  xmlns:th="http://www.thymleaf.org">

th:text 태그안의 텍스트 변경
th:href href 링크 변경
th:each forEach랑 비슷한건가 리스트 갯수만큼 for문 효과?

칼렌더 효과
"${#calendars.format(post.posted, 'mm/dd/yyyy')}"

th:utext


GSP Template
Groovy Server Page
내용변경이후 서버 리스타트 없이 바로 변경이 가능하다.

jsp는 몇가지 제한사항이 있어서 가능하면 안스는게 좋다

i18n
Internationalization : 국제화
어플리케이션을 글로벌하게 해주는 것

th:text="#{copyright}"
messages.properties
messages_fr.properties
두개를 준비
spring.mvc.locale=fr
로케일이 바뀌면 알아서 바꿔줌


Error Handling
에러 종류
white label error page
custom error pages
  create your own /error page
  400 / 404/ 500
Controller Exception Handler
Global Controller Exception Handler
  handlerExceptionResolver
  Controller Advice


  Exercise

  Create a new application using the Spring Initializr
  Select Web dependency
  Select Template dependency (your choice which one)
  Create an index.html template in the static folder
  what happens when you run the app and go to http://localhost:8080
  Create a controller package
  create a controller (@Controller)
  create a couple of methods with request mappings
  Create a service package
  create a service (don't forget the @Service annotation)
  create a method that will return some data (any data)
  Views
  create some templates (in the templates folder) that will be displayed and match your controller requests
  create some static content to include in those views (css/images/js)
  add static content to your views using one or more of the following
  manually (example: download bootstrap and drop it in your project)
  Webjars
  bower
  Error Handling
  create a custom error handler template
  create a cool 404 page
  Exception Handling
  have one of your controller methods throw an exception
  catch that exception in the controller using @ExceptionHandler
  catch the exception using Controller Advice
   
