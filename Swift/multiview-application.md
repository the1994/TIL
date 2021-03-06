# 화면이 여러 개 있는 애플리케이션  
1. 화면 변경 방법 결정
2. 화면마다 뷰 컨트롤러 만들기
3. 데이터 연동 방법 결정 

## 1. 화면 변경 방법 결정   

- 화면 위에 띄워서 변경: Modal  
 - 일시적인 화면에 사용  
 - 화면 위의 버튼을 탭하면 다른 화면으로, 또한 돌아가기 버튼을 눌러 원래의 화면으로  

- 내비게이션으로 변경: Navigation Controller  
 - 애플리케이션에 내비게이션 바가 있고, 계층적으로 화면을 전환하는 방법  
 - 여러 개의 항목 중에서 하나를 탭하면 화면이 오른쪽에서 왼쪽으로 밀리면서 전환. 돌아가기 버튼으로 돌아감  
 - Master-Detail Application 템플릿을 이용해 쉽게 만들 수 있다.  

- 탭바로 변경: Tab Bar Controller 
 - 애플리케이션 아래에 탭바가 있고, 병렬적으로 화면을 전환하는 방법  
 - Tabbed Application 템플릿을 사용 

**화면 변경 방법은 세그웨이로 지정**  

- 어떤 화면에서 다른 화면으로 변경할 때는 세그웨이(segue)를 사용해서 연결  

## 2. 화면마다 뷰 컨트롤러 만들기 

- 1개의 화면은 1개의 뷰 컨트롤러로 컨트롤한다.  
- 델리게이트  
 - 가게(뷰)  
 - 점원(객체)  
 - 점장(뷰 컨트롤러)  
 - 델리게이트: 아르바이트 점원이 점장에게 일의 내용을 질문할 때 사용하는 것  

- 여러 개의 화면이 있으면 뷰 컨트롤러도 여러 개  
 - 앱 델리게이트라는 중앙 센터 같은 것으로 속성을 공유한다.  

## 3. 데이터 연동 방법  

1. 직접 데이터를 주고 받기  
 - 화면이 다음 화면으로 변경될 때 데이터를 전달.  
 - 원래 화면으로 돌아올 때 데이터를 받음  
2. 앱 델리게이트를 사용해 데이터를 공유  
 - 앱 델리게이트에 속성을 만들고  
 - 처음 화면에서 앱 델리게이트의 속성에 데이터를 저장  
 - 다음 화면에서 앱 델리게이트의 속성에서 데이터를 읽어 들인다.    

