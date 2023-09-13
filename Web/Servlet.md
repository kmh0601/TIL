# 서블릿 Survlet

-----

- 개념
    - 동적 웹 페이지를 만들 때 사용되는 자바 기반의 웹 애플리케이션 프로그래밍 기술
    - 웹 요청과 응답을 간단한 메서드 호출만으로 다룰 수 있게 한다
    - 아직 웹에 대한 지식이 부족해 어색한 용어가 많지만 웹에 요청에 대한 응답을 메서드로 작성해두고 이를 필요한때에 	호출해서  필요한 작업을 수행하는 것으로 보인다
    - 웹 애플리케이션 서버(WAS) 에서 컴파일되고 동작한다
    - JSP와의 차이점은 JSP는 HTML코드 내부에 JAVA코드가 들어가 있고, 서블릿은 JAVA코드 내에 HTML코드가 있다


- 동작 과정
    1. 클라이언트 요청
    2. HttpServletRequest, HttpServletResponse 객체 생성 // override된 init()호출, 맨 처음 한 번만 호출
    3. Web.xml이 어느 서블릿에 대해 요청한 것인지 탐색
    4. 해당하는 서블릿에서 service() 메소드 호출   // 미리 메서드로 작성된 작업 수행
    5. doGet() 또는 doPost() 호출  // override해서 미리 작성되어 있음
    6. 동적 페이지 생성 후 ServletResponse 객체에 응답 전송
    7. HttpServletRequest, HttpServletResponse 객체 소멸 // override된 destroy()호출


- 비고
    - 스프링부트 및 웹 공부하면서 개념 및 동작과정 보충하기
    - 소켓, 웹서버, 통신 등 공부하기
    - 서블릿 컨테이너 공부하기