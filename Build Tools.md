# Java Build Tools

Automation of developer tasks
개발간 할일을 자동으로 해준다

Compiling Source Code Into Binary
Packaging that Binary
Running Tests
Deployment to other systems(QA/UAT/PROD)

3개의 자바 빌드 툴
1) Ant
오래되서 이제 잘 안쓰는거 같다.

2) Maven
Dependency를 관리 할 수 있는게 가장 큰 장점인듯
dependency를 선언할때 버전 입력을 안해도 된다.
IDE 코드 어시스트 해줌.(자동 입력?)
parent POM.xml문서를 작성해서관리 할 수 있음
터미널에서 mvn spring-boot:run 서버실행 명령어

3) Gradle
Groovy를 사용하는 툴.
새로나와서 정말 정말 좋은 툴 같다고 한다...
apply plugin

gradle Build
gradle bootRun

4) 결론
maven이나 gradle이나 별 차이 없으니 알아서 정해서 사용해라.

Starter POMs
스타터 폼(?)을 이용하는 이유 : 필요한 것들이 대부분 들어있기 때문에 개발할때마다 복사붙여넣기 하지 말고 한번에 쓰자
Set of convenient dependency descriptors
Avoid copy / paste

웹 개발자들에게 필요한 것들이 들어 있음
Spring-boot-starter-web



Executable JARs
클라우드 서비스에 올리기 좋다.(?)

Spring CLI = spring jar command
spring jar my-app.jar app.groovy app.groovy의 my-app.jar라는 jar 파일을 만들어주세요.
my-app.jar 와 my-app.jar.original 파일이 만들어짐
jar tf my-app.jar.original
오리지날은 필요한것만 들어있는 파일
my-app.jar 는 모든게 들어있는 파일

java -jar my-app.jar 실행

Maven = spring-boot-maven-plugin
mvn clean package 를 해주면
target/ 디렉토리에 jar 파일이 생긴다

Gradle = spring-boot plugin
gradle build 를 해주면
build/libs/ 에 jar 파일이 생긴다
java -jar ... 실행


DevTools & Live Reload
Spring Boot 1.3+
spring-boot-devtools
Property Defaults
  - spring.thymeleaf.cache
Automatic Restart
 - spring Loaded & JRebel
Live Reload
Remote Debug Tunneling

디벨로퍼툴 추가 하기
프로그램이 오토컴파일해주고
브라우저에서 자동리프레쉬해줌.(livereload)
