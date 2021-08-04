### 동일 출처 원칙

- 비동기 통신을 할 때, 프론트에서 백엔드에 리소스를 요청하는 것은 전혀 문제가 되지 않음.(여기서 프론트 백엔드는 같은 서버 의미. 같은 도메인에 있는 페이지가 비동기로 백엔드에 있는 리소스를  요청하는 것은 문제 x)
- a.com 프론트 페이지가 b.com(다른 도메인)에 데이터 요청을 하면 동일한 도메인의 출처를 따르는 원칙에 위배 → 서비스가 불가능하도록 막혀있음
- 자신의 도메인에서 접근하는 요청은 받아주지만, 타 도메인에서의 요청의 data access는 막아놓음
- 이걸 풀어주기 위한 방법 2가지  

    1. CORS 설정
    - b.com에서 도메인을 가로지르는 요청들도 허용하도록 컨트롤러에 @CORS 설정을 해놓는 것. 출처가 다른 도메인의 접근을 허용하겠다고 데이터를 제공해주는 백엔드 측에서 세팅하는 것.

    ```java
    // 해당 컨트롤러의 모든 요청에 대한 접근 허용(아래 도메인 두개에 대해서만)
    @CrossOrigin(origins = {"http://localhost:18080", "http://localhost:8180" })
    // @CrossOrigin(origins="*") // 이렇게 하면 모든 도메인에게 열어주는 것
    @RestController
    public class CorssampleApplication {
     
    	//아래와 같이 특정 메소드에만 적용도 가능
        //@CrossOrigin(origins = {"http://localhost:18080", "http://localhost:8180" })
        @GetMapping("/hi")
        public String hi() {
            return "hi";
        }
    ```

    그런데 보통 open API 보면 CORS 처리 잘 안돼있음. open API가 권장하는 건 "우리 리소스 비동기적으로 직접 요청 하지마. 동기적인 요청만 허용할게"  

    2. Proxy 기법

    - 우리의 a.com 프론트 페이지가 우리 백엔드에게(a.com 백엔드의 컨트롤러에게) 비동기 요청을 보냄. 그럼 우리 백엔드에서는 Network API로 b.com 리소스를 요청해서 데이터를 받아오고 그대로 프론트엔드에게 토스해줌
    - 우리 백엔드의 컨트롤러가 proxy(대리인) 역할을 하는 것
