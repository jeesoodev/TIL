하둡
- 데용량 데이터를 분산 처리할 수 있는 자바기반의 오픈소스 프레임 워크
- DBMS가 X → 프레임 워크 O
- 하둡은 분산시스템인 HDFY(Hadoop Distributed File Systme)에 데이터를 저장하고, 맵리듀스를 이용해 데이터를 처리

분산저장(HDFS: Hadoop Distributed File System)

- 빅데이터 파일을 여러 대의 서버에 분산 저장하기 위한 파일 시스템

분산처리(MapReduce)

- 각 서버에서 데이터를 분산처리하는 분산 병렬 처리를 위한 분석 시스템

<br>

### Linux와 HDFS

- 데이터 생성, 코딩은 Linux에서 하고, MapReduce 코드와 입력 데이터는 HDFS에 옮겨서 MapReduce 알고리즘 수행

- src 디렉토리에 새롭게 java 파일을 만들 때마다 Driver.java 파일에 아래처럼 추가 시켜줘야 컴파일이 된다.
- 실제로 돌릴 때는 첫 번째 인자 " " 로 수행하게 됨
- Driver.java 파일이 바뀌면 ant를 반드시 다시 수행해야 한다.
- ant를 할 때 src 디렉토리에 있는 모든 파일이 컴파일이 되는 것

```jsx
pgd.addClass("wordcount", Wordcount.class, "A map/reduce program that perform word counting.");

pgd.addClass("사용명",클래스 이름(.class),"설명");
```

- 아래 처럼 하면 실행됨
- ex. hadoop jar ssafy.jar wordcount wordcount_test wordcount_test_out

### ant

- Unix의 make 같은 것으로 Java 개발 환경에서의 표준 빌드 도구
- 자바 파일을 컴파일하는 Javac도 있지만, ant는 여러 dependency를 고려하여 소스파일을 컴파일
- src 디렉토리에 있는 것을 다 모아서 컴파일 한 후에 ssafy.jar을 생성한다.
- Project 디렉토리에 있는 build.xml 파일에 정의한 대로 수행한다.

- 테스트 데이터를 HDFS에 넣어야 함
- 반드시 맵리듀스 프로그램이 결과를 저장할 디렉토리를 삭제한 후 프로그램을 실행해야 한다. 맵리듀스 출력파일이 저장되는 디렉토리가 없어야 맵리듀스 코드가 하둡에서 돌아감
    - hdfs dfs -rm -r wordcount_test_out

### Hadoop 실행 방법

- hadoop jar [jar file] [program name] <input arguments...>
