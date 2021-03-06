# 클래스 패스  

https://opentutorials.org/course/1223/5527  

- 클래스는 하나는 하나의 클래스 파일이 된다.  

## 클래스의 경로  

`java -classpath ".:lib" ClasspathDemo2`  
- .은 현재 디렉토리  
- 현재 디렉토리 밑에 있는 lib에서 클래스를 찾아보아라는 의미  
- 옵션 `-classpath`는 자바를 실행할 때 사용할 클래스들의 위치를 가상머신에게 알려준다.  
- `classpath` 옵션을 지정하지 않으면 자바는 기본적으로 현재 디렉터리 안에서 명시한 클래스를 찾는다.  


## 환경변수  

- 클래스 패스를 자바를 실행할 때마다 지정하는 것이 귀찮다면 클래스 패스를 시스템의 환경변수로 지정하면 된다.  
- 환경변수는 운영체제에 지정하는 변수로 자바 가상머신과 같은 애플리케이션들은 환경변수의 값을 참고해서 동작하게 된다.   
- 자바는 클래스 패스로 환경변수 `CLASSPATH`를 사용하는데 이 값을 지정하면 실행할 때마다 `-classpath` 옵션을 사용하지 않아도 되기 때문에 편리  
- 하지만 운영체제를 변경하면 클래스 패스가 사라지기 때문에 이식성면에서 불리할 수 있다.  
- [참고](https://opentutorials.org/module/516/5245)  

## 동시대적 감수성  

- 상수, 변수, 연산자, 조건문, 반복문은 가장 기본적인 프로그램 수단 = 로직 자체  
- 반면, 메소드, 유효범위, 클래스, 클래스 패스와 같은 것들은 관통하는 공통분모는 로직의 체계적인 관리수단이라할 수 있다.  
 - 로직 자체는 간단, 관리수단들은 많고 복잡하다. 그리고 중요하다.  
 - 이런 수단들이 단지 공부거리가 아닌 개발을 쾌적하게 도와주는 매우 우용한 도구라고 생각할 수 있다.  
 - 만약 프로그래밍 초창기부터 개발을 했다면 이런 도구들의 등장은 마치 게임의 아이템을 획득하는 것처럼 즐거운 일이 되었을 것!! 
 - 그렇게 생각해보도록 하겠다!! 