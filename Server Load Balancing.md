서버 부하 분산(Server Load Balancing)
- 외부의 사용자로부터 들어오는 여러 요청들을 서버들에게 적절히 배분하여 처리하도록 하는 것
- 분산 처리는 부하 분산 Network Switch 혹은 소프트웨어가 담당. 외부로부터의 요청을 서버가 직접 받는 것이 아니라 '부하 분산 Network Switch'나 '소프트웨어'가 받은 후, 이를 서버로 적절히 나누어 주는 것
- 서버 부하 분산을 담당하는 Network Switch를 L4/L7 Switch(Layer 4)라고 부르며 Cloud에서는 Load Balancer라 지칭

방식
* Round Robin: Round Robin은 로드밸런서가 다수의 서버에게 순서대로 요청을 할당하는 방법
* Least Connection
* Ratio(가중치)
* Fastest(Response Time): 응답속도가 가장 빠른 서버에게 우선적으로 할당하는 방식
