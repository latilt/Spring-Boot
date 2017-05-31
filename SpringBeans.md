singleton 한번 생성되는 instance
prototype 여러번 생성되는 instance
request http 요청에 항상 새로운 인스턴스 생성
session
globalsession

싱글톤에는 default bean scope가 지원되지 않음


Autowired
인스턴스가 요청될때 객체가 여러개 생성될 경우

Property Based Injection
이 방법은 좋지 않으므로 다른 방법을 쓰자
```java
@Autowired
private NotificationService notificationService;
```

Setter Based Injection

```java
private NotificationService notificationService;

@Autowired
public void setNotificationService(NotificationService notificationService) {
  this.notificationService = notificationService;
}

```

Constructor Based Injection

```java
private NotificationService notificationService;

@Autowired
public PageController(NotificationService notificationService) {
  this.notificationService = notificationService;
}
```

Externalized Configuration
YAML files
Property Sources

properties 파일들은 여러개를 쓸때 직접 써야하지만
yaml 파일은 오브젝트 형태로 써서 쓰기 편하다

프로퍼티들을 한곳에 모아서 관리하자
그중에 yaml파일로 json 형태이다.
```java
@Value("${pageController.msg}")
```

application.properties 와
application.yaml은 같이 쓸수 있고 병합할수도 있다. properties가 우선순위

edit configuration - program argument 프로그램이 동작할때 변수를 넣을수 있다.
--pageController.msg="Hello from command line"


Configuration Properties
@EnableConfigurationProperties 메인클래스에
@ConfigurationProperties(prefix = "myconfig") 선언클래스에

속성을 정의 할 수 있는 특정 순서가 있다.

dependency 추가
spring-boot-configuration-processor
pojo(?)


Profiles
spring.profiles.active=development,dans

2개 넣을수 있다.


Auto Configuration
configuration은
@SpringBootApplication
@EnableAutoConfiguration 둘다에 작동한다
--debug
