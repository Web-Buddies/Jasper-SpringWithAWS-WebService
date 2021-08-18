## SpringBoot Framework 

### SpringBoot , JPA , Social Login with SpringSecurity ++ JUnit
### AWS Infra & EC2 & RDS

#### Library

Lombok
-> Getter , Setter , 기본 생성자, toString 등을 어노테이션으로 자동 생성해준다. 
(롬복은 프로젝트마다 설정해야 한다. -> build.gradle 과 enable annotation processing 과정 %%)

#### TEST Code

[TDD](https://repo.yona.io/doortts/blog/issue/1) 

-> 테스트가 주도하는 개발. 테스트 코드를 먼저 작성한다.

Red ( 항상 실패하는 테스트를 먼저 작성하고 )

Green ( 테스트가 통과하는 프로덕션 코드를 작성 )

Refactoring ( 테스트가 통과하면 프로덕션 코드를 리팩토링 )

Unit Test

-> TDD 의 첫번째 단계인 기능 단위의 테스트 코드를 작성하는 것 

1. 빠른 피드백
2. 자동검증 가능
3. 개발자가 만든 기능을 안전하게 보호

#### Annotation

@SpringBootApplication

-> 스프링 부트의 자동설정, 스프링 Bean 읽기와 생성을 모두 자동으로 설정 이 위치에서 부터 설정을 읽어가기 때문에 항상 프로젝트의 최상단에 위치해야 한다. 

-> main 메소드에서 실행하는 SpringApplication.run 으로 인해 내장 WAS 를 실행한다.  ( 항상 서버에 톰캣을 설치할 필요가 없고, 스프링 부트로 만들어진 Jar 파일로 실행하면 된다.  -> 언제 어디서나 같은 환경에서 스프링 부트를 배포 할수 있음)


@RestController

-> 컨트롤러를 JSON을 반환하는 컨트롤러로 만들어준다. 

-> 과거에는 @ResponseBody 를 각 메소드다 선언했던 것을 한번에 사용할 수 있게 해준다고 생각하면 된다.

@GetMapping

-> Http Method 인 Get 의 요청을 받을 수 있는 API 를 만들어준다. 

-> 과거에는 @RequestMApping(method = RequestMethod.GET) 으로 사용했다.

#### Test Annotation

JUnit4  -> @RunWith(SpringRunner.class)

JUnit5 -> @ExtendWith(SpringExtension.class)

-> 테스트를 진행할때 JUnit 에 내장된 실행자 외에 다른 실행자를 실행시킨다. 

-> 스프링부트 테스트와 JUnit 사이의 연결자 역할을 한다. 

@WebMvcTest
-> 여러 스프링 test Annotation 중, Web( Spring MVC )에 집중할 수 있는 어노테이션 이다. 

-> 선언할 경우, @Controller, @ControllerAdvice 등을 사용할 수 있다. 

-> 단, @Service, @Component, @Repository 등은 사용할 수 없다. 

(%)@AutoWired

-> 스프링이 관리하는 빈(Bean)을 주입 받는다. 

#### Lombok Annotation

@Getter

-> 선언된 모든 필드의 get 메소드를 생성해준다. 

@ RequiredArgsConstructor

-> 선언된 모든 final 필드가 포함된 생성자를 생성해준다. 
-> final 이 없는 필드는 생성자에 포함되지 않는다. 


