# JDBC API

----

- Java Database Connectivity의 약자
- Java언어로 데이터베이스 프로그래밍을 하기 위한 라이브러리
- 특정 DBMS에 종속되지 않는 API를 제공하기 때문에 데이터베이스의 종류는 상관없다(벤더 독립적 API)
- JDBC를 이용한 데이터베이스 연동 과정
    - Package import
    - JDBC 드라이버 로드
    - Connection 객체 생성
    - PreparedStatement 객체 생성
    - Query 수행 (PreparedStatement 인스턴스 메서드에 Query를 매개변수로 넣음 -> Result인스턴스로 결과 받음)
    - Result객체로부터 데이터 추출
    - 생성된 객체 Close
- 이때 Statement객체와 PreparedStatement객체가 있는데 둘의 차이는
  Statement객체는 캐시를 사용하지 않는다는 점이다. 따라서 Statement객체는 매 쿼리를 수행 할 때마다 1~3단계를 거친다.
- 토비의 스프링 3.1 실습을 하면서 mysql을 연동하면서 직접 사용해봄
> 문제
- JDBC 드라이버 다운로드 및 경로 설정이 까다로웠음
> 해결
- 웹서치를 통해 JDBC 다운로드 하고, 인텔리제이-> file -> project structure -> 다운받은 파일 라이브러리에 추가
- url = com.mysql.cj.jdbc.Driver