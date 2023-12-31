# MVC

---
- 개념
    - Model-View-Controller의 세 부분으로 애플리케이션을 기능적으로 구분하는 디자인 패턴이다
    - 각 부분은 서로 다른 역할을 수행한다
  

    - Model
        - 데이터를 가진 객체, 데이터를 처리하는 객체(응집도 높임)
        - 모델의 상태에 변화가 있을 때 컨트롤러와 뷰에 이를 통보
        - 뷰, 컨트롤러에 대한 어떠한 정보도 몰라야 함(의존성 x, 결합도 낮춤)
    - View
        - 사용자에게 제공할 결과물을 생성하기 위해 모델로부터 데이터를 받아옴
        - 모델로부터 받아온 데이터를 따로 저장해서는 안됨(얘의 역할이 아님)
        - 모델, 컨트롤러에 대한 정보를 몰라야 함
    - Controller
        - 모델, 뷰에 대한 정보를 알아야 함(의존성)
        - 모델, 뷰의 변경을 모니터링 해야 함
        - 사용자의 요청사항을 파악한 후에 그 요청에 맞는 데이터를 Model에 의뢰하고, 데이터를 View에 반영해
          사용자에게 알려줌


- 동작
  1. 사용자가 요청을 컨트롤러에게 보냄
  2. 컨트롤러가 모델을 사용하여 요청에 맞는 비지니스 로직 수행
  3. 모델로부터 처리한 결과를 사용자에게 보여줄 알맞은 뷰 선택
  4. 뷰는 컨트롤러부터 데이터를 전달받아 사용자에게 알맞은 결과 화면을 보여줌


- MVC 패턴의 장점 
  - 비지니스 로직과 UI로직을 분리하여 변경에 대한 파급효과를 줄여 유지보수를 독립적으로 수행함  
    >(첨언) 오브젝트를 공부하면서 객체지향 프로그래밍의 핵심은 유지보수라고 배웠다. MVC패턴을 많이 사용하는게 유지보수에서 큰 이점을 가지기 때문인 것 같다.


- MVC 패턴의 한계 
  - 하나의 Controller에 다수의 Model과 View가 복잡하게 연결될 수 있다

> <비고>   
> MVC1,2 공부하고, 스프링 공부하면서 직접 웹에서 사용하는 MVC예제 실습해보기

> Model
```java
@Getter
@NoArgsConstructor
public class Bread{
    private Long id;
    private Stirng name;
    public Bread(Long id, String bread){
        this.id = id;
        this.name = bread;
    }
        }
```
> Controller
```java
@Controller
public class BreadController{
    private final BreadService breadService;
    
    @GetMapping("/search/bread")
    public String searchBread(@PathVariable String name, Mondel model){
        boolean result = breadService.findByName(name);
        model.addAttribute("result", result);
    } 
}
```
> View 생략 
> Todo : 어노테이션 없는 MVC 모델 예제 찾아서 추가해보기
