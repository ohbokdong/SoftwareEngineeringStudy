# Week 4 보충 - Z 명세 (z-notation)

![01](https://github.com/ohbokdong/SoftwareEngineeringStudy/blob/master/summary/img/week4/z-notation.png)
  
### 01. 정형명세 (Formal methods)

- #### 정형 명세의 정의  
  
    - 수리, 논리를 이용하여 시스템의 기능, 행위, 동작 환경을 기술하는 것
  
- #### 정형 명세의 목적  
  
    - 시스템의 기능, 행위, 동작 환경을 정형적으로 명세함으로써 모호함을 없앨 수 있다.  
  
- #### 정형 명세에 대한 설명
  
    - 먼저, 요구사항(Requirement)를 정형적으로 명세할 수 있음. 무엇을 명세하는지, What에 해당함. 정형 명세를 통해 수 많은 요구사항 간 Inconsistency를 없앨 수 있음. 
    - 또한 설계사항(Design)을 정형적으로 명세할 수 있음. 어떻게 명세하는지, How에 해당함. 
    - 정형 명세를 통해 요구사항과 설계사항을 명세하면, 이를 수학적으로 증명할 수 있음. 즉, 설계가 요구사항을 만족하는지 "증명"할 수 있으며, 이는 소프트웨어 테스팅으로는 달성할 수 없는 매우 Powerful한 정형기법의 장점


- #### 정형기법과 소프트웨어 테스팅(Software testing)의 차이
    - Testing의 목적은 에러와 버그를 찾는 것. Testing의 결과 에러와 버그가 발견되지 않았다고 해도, 프로그램에 에러와 버그가 없다고 단정지을 수는 없음. 
    - 정형 기법의 목적은 버그와 에러를 확인하여 없애는 것에 있다. 완벽한 Specification이 전제된다면, 정형 기법의 결과를 신뢰할 수 있음.

> 결론적으로 Z 명세(Z Notation)는 위 설명된 정형기법의 종류 중 하나

### 02. 정형명세 언어 Z

- #### 장점
    - 집합론, 일차논리에 기반을 둔 언어
    - 시스템의 상태 및 오퍼레이션을 명세하여 시스템에 대한 일관성, 완전성 및 시스템이 만족하여야 할 특성들을 검증할 수 있음
  
- #### 단점
    - 하지만 Z는 단일 시스템을 대상으로 하기에 여러 시스템 및 컴포넌트들로 구성되어 네트워크로 통신하는 시스템을 나타내는 데에 있어서 명세하기 어려운 점이
    많음
    - Z에서는 오퍼레이션을 전 상태와 후 상태의관계로써 정의하기 때문에 프로토콜과 같이 순차적으로 수행되는 대상을 명세하기에는 어려운 점이 있음
    - 프로토콜 명세를 위해 SPIN, CSP와 같이 통신 명세에 특화된 언어들을 사용하면 시스템의 기능성을 나타내는 데에 있어 많은 제약사항들이 따름.