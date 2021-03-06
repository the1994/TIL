# 분산 및 다중(병렬) 처리 시스템  

## 네트워크의 구성  

- 네트워크: 몇 개의 독립적인 시스템이 적절한 영역 내에서 빠른 속도의 통신 채널을 이용해 상호 통신할 수 있도록 지원하는 데이터 통신 시스템이다.    
- **강결합<sup>tightly coupled</sup> 시스템**: 프로세서들이 메모리를 공유하는 다중 처리 시스템  
- **약결합<sup>loosely coupled</sup> 시스템**: 둘 이상의 독립된 시스템이 통신선으로 연결되며, 시스템은 자신만의 운영체제, 메모리, 프로세서, 입출력장치 등으로 독립적으로 운영  

## 네트워크 구조<sup>topology</sup>

- **망<sup>mesh</sup> 구조**: 각 노드가 시스템(네트워크) 내의 다른 모든 노드와 직접 연결하는 완전 연결 구조, 네트워크의 각 노드는 하나 이상의 노드에 연결되나 서로 각각 모두 연결된 노드 없이 부분적으로 연결된 부분 연결 구조로 나눔.  
- **트리<sup>tree</sup> 구조**: 트리 도는 계층 구조는 회사의 컴퓨터 네트워크에 사용되는 구조로 네트워크의 각 노드가 트리로 구성  
- **성형<sup>star</sup> 구조**: 모든 노드가 중앙 노드에 직접 연결되고, 중앙 노드 외의 다른 모든 노드는 서로 연결되어 있지 않다.  
- **링<sup>ring</sup> 구조**: 각 노드가 정확히 2개의 다른 노드와 연결된다.  
- **버스<sup>bus</sup> 구조**: 연결 버스(중앙의 통신회선) 하나에 모든 노드가 연결된다.  

## 원격 프로시저 호출<sup>RPC, Remote Procedure Call</sup>  
- 한 컴퓨터에서 실행되는 프로세스가 다른 컴퓨터에서 실행되는 프로세스의 프로시저(또는 함수)를 호출할 수 있게 하는 것으로 클라이언트/서버 모델을 전제로 한다.   

## 분산 시스템  

- 저렴한 노드 여러 개를 하나의 운영체제가 제어할 수 있도록 구현한 시스템  
- **분산 시스템의 구축 목적**: 자원 공유 용이, 연산 속도 향상, 신뢰성 향상, 통신 가능  
- **분산 시스템의 투명성**: 시스템에 있는 각종 자원의 투명성 보장  
 - 투명성: 상호 연결된 컴퓨터를 사용자가 하나의 컴퓨터 시스템으로 인식할 수 있도록 분산을 감추어 사용자가 이에 대한 정보를 몰라도 작업을 수행할 수 있도록 지원하는 개념  
 - 종류: 액세스 투명성, 위치 투명성, 고장 투명성, 중복 투명성, 이동 투명성, 병행 투명성 등  

## 네트워크 운영체제<sup>NOS, Network Operating System</sup>  
- 통신을 제어하고 분산된 자원을 공유하면서 독립된 시스템들을 서로 연결하려고 개발  
- **네트워크 운영체제의 주요 기능**: 자원 공유, 액세스 권한 부여, 파일 전송, 데이터 보호, 관리 제어  
- **네트워크 운영체제의 운용 방법**: 네트워크 운영체제는 자원 운영 방법에 따라 피투피<sup>peer-to-peer</sup> 모델과 클라이언트/서버 모델로 분류  

## 분산 운영체제<sup>DOS, Distributed Operating System</sup>  
- 네트워크 운영체제의 지역적인 자원 관리와 지역 제어의 제한을 벗어나 시스템 자원의 전역 제어 및 관리의 필요성에 따라 발전  
- 공동 운영체제로 사용자에게 시스템이 제공하는 여러 자원에 액세스가 가능한 참조 투명성을 제공  
- 분산된 컴퓨터 간의 자원을 쉽게 공유하고 액세스 할 수 있다.  

## 분산 시스템의 교착 상태  
- 자원 할당 교착 상태  
- 메시지 전송 교착 상태(통신 교착 상태)  

## 클라이언트/서버 시스템  
- 분산 시스템 환경이 **한 대의 메인 컴퓨터가 모든 일을 처리하는 중앙 집중화된 환경**에서 **여러 대의 컴퓨터가 작업을 기능별로 분담**하여 처리하는 분산 처리 컴퓨팅 환경  

## 미들웨어  
- 클라이언트/서버 컴퓨팅 기술의 이점을 살리기 위해선 서로 다른 환경에서 실행되는 응용 프로그램이 서로 원만하게 통신할 수 있고 개발자가 모든 플랫폼으로 시스템 자원에 액세스할 수 있는 도구가 필요.  
- 교량 역할을 하며, 서비스를 제공하는 소프트웨어를 **미들웨어<sup>middleware</sup>**라고 한다.  

## 다중(병렬) 처리  
- 다수의 프로세서를 동시에 수행함으로써 시스템 성능ㅇ을 향상  
- 구분(연결하는 방법에 따라)    
 - 공동 버스 시스템  
 - 크로스바 교환 행렬 시스템  
 - 다중 포트 메모리 시스템  
 - 하이퍼큐브 시스템  

## 다중 처리 시스템의 운영체제  

- **주종<sup>master/slave</sup> 운영체제**: 하나의 프로세서를 주(M)로 지정해 운영체제를 실행하고 나머지 프로세서는 사용자 수준의 프로그램을 실행할 수 있는 종(S)으로 지정  
- **분리 실행**: 각 프로세서가 서로 다른 운영체제를 가지며 각 프로세서에서 발생하는 인터럽트는 해당 프로세서에서 해결하는 구성 방법  
- **대칭**: 모든 프로세서가 동등한 입장에 있으며, 운영체제는 모든 프로세서와 입출력장치, 기억장치를 사용할 수 있도록 관리  

## 클러스터  
- 네트워크로 여러 대의 컴퓨터를 연결해 하나의 단일 컴퓨터처럼 동작하도록 구현한 시스템  
- 대칭형 다중 처리 대안으로 높은 성능과 확장성을 제공  
