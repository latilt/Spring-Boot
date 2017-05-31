h2
spring.h2.console.enabled=true
spring.h2.console.path=/console

h2 데이터베이스는 콘솔로 보고 싶으면 enabled를 트루로 해줘야 한다.

JPA
java persistence api

@Entity 클래스를 엔티티로 등록(테이블을 만든다고 생각?)
@Id primary key 등록
@GeneratedValue
@ManyToOne
@OneToMany( mappedBy = "author")
@PostConstruct

jpa는 private no arg constructor
private의 인자가 없는 생성자가 꼭 필요하다

java persistence 는 javax.persistence에 팩키지되어있다.

private String firstName 으로 만들면
first_name으로 column 생성

Post Repository를 만들때 Id 타입이 Long 일때
public interface PostRepository extends CrudRepository<Post, Long> {}

controller는 클라이언트의 response 처리
Repository는 쿼리문을 만드는곳
domain은 테이블과 values 만드는곳
service는 repository에서 만든 쿼리문을 가져다 쓰는곳

domain에서 만든 테이블로 repository에서 쿼리구문을 만들고 service에서 쿼리구문을 각져와 함수로 만듬.
controller에서 service를 불러와 사용함.

Loading data
spring.datasource.platform=h2
플랫폼 설정
data-h2.sql
데이타-디비이름.sql 파일 resources에 생성
쿼리문을 넣어두는곳?

자동으로 설정된 column을 다른 타입으로 바꾸는 방법
@Column(columnDefinition = "TEXT")

날짜
@CreatedDate @Column( columnDefinition = "TIMESTAMP")

Refactor


@RequestMapping("/view/{slug}")
이건 뭘까?
