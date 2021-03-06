# Week 8 - 테스트

## 01. 소프트웨어 테스트의 목표
* 좁은 의미 : 윈시 코드 속에 남아 있는 오류를 발견하는 것. 결함을 예방하는 것.
* 넓은 의미 : 개발된 소프트웨어가 고객의 요구를 만족시키는지를 확인시켜주는 것.

## 02. 테스트 수행의 문제
* 테스트 케이스가 적어 효과에 한계가 있음.
* 완벽한 테스트 케이스를 도출하기 어려움.
* 테스트를 위한 실제 사용 환경을 구축하기 어렵.
* 작은 실수를 발견하기 어려움.
* 테스트의 중요성에 대한 인식이 부족.

## 03. 테스트의 특징
* 고객의 요구 사항을 충족시켜야함.
* 테스트 단계에서만 수행되는 단순한 활동이 아니라 개발 단계와 함께 함.
* 파레토 원리를 적용 할 수 있음.
* 모듈 단위를 점점 확대해가며 진행.
* 완벽한 테스트는 불가능.
* 개발자와 다른 별도의 팀에서 수행.
* 살충제 패러독스(테스트 내성) 문제해결을 위해 테스트 케이스 업데이트가 필요.

## 04. 테스트 프로세스 
* 1단계 테스트 계획 : 테스트 목표를 정의, 테스트 대상 및 범위를 결정, 테스트 계획서를 작성하고 검토 함.
* 2단계 테스트 케이스 설계 : 테스트 케이스 설계 기법을 정의하고, 결정된 설계 기법에 따른 테스트 케이스 도출, 테스트 케이스 명세서, 설계서, 절차서가 생성됨
* 3단계 테스트 실행 및 측정 : 테스트 환경을 구축하고 도출된 테스트 케이스를 이용하여 테스트를 실시, 실행 결과를 문서화.
* 4단계 테스트 결과 분석 : 계획 대비 결과를 비교, 분석한다. 테스트 결과에 대한 보고서를 작성.
* 5단계 오류 추적 및 수정 : 테스트 결과 어디에서, 어떤 종류의 오류들이 발행 했는지 확인하고 수정.

## 05. 시각에 따른 테스트
* 확인 테스트 : 설계도대로 만들었는지 개발자 시각으로 테스트
* 검증 테스트 : 사용자가 원하는 것을 만들었는지, 완성된 제품이 사용자의 요구 사항을 모두 충족시키는지를 사용자 시각으로 테스트

## 06. 목적에 따른 테스트
* 운영 목적 적합성 테스트 : 시스템의 운영 목적에 적합한지를 테스트.
* 수정 용이성 테스트 : 소프트웨어의 수정이 얼마나 용이한지를 테스트.
* 상호 운용성 테스트 : 양립성, 일치성, 이식성, 재사용성 등을 체크.
* 운영 지원 용이성 테스트 : 문서화, 복원 가능성 등을 체크

## 07. 프로그램 실행 여부에 따른 테스트
* 정적 테스트 : 프로그램을 실행하지 않고 코드를 검토, 오류를 찾는 방법
* 동적 테스트 : 프로그램을 실행하면서 오류를 찾는 방법

## 08. 정적 테스트
* 개별 검토 : 체크리스트를 가지고 본인이 개발한 코드와 산출물 등을 검토하여 오류를 찾는 방법
* 동료 검토 : 동료에게 개발한 원시 코드나 여러 가지 산출물들에 대한 검토를 의뢰하여 오류를 찾는 방법
* 검토 회의 : 일반적으로 개발자가 소집한 전문가들에 의해 개발자의 작업이 검토됨. 요구사항, 설계 문서들에 대해 고객의 요구사항을 정확히 명시하고 있는지 여부를 확인, 작업 진척 상황도 확인
* 소프트웨어 검사 : 소프트웨어 개발 전 과정에 걸쳐 요구 분석 명세서, 설계서, 원시 코드뿐만 아니라 각 단계 산출물의 문서 등을 초함하여 분석, 품질을 평가

## 09. 동적 테스트
테스트 데이터를 이용해 실제 프로그램을 실행함으로써 오류를 찾음.
테스트 정보를 얻는 문서의 종류에 따라 명세 기반 테스트와 구현 기반 테스르로 세분화 할 수 있음

## 10. 명세 기반 테스트 (블랙 박스 테스트)

입력값에 대한 예상 출력 값을 정해놓고 그대로 결과가 나오는지를 확인함으로써 오류를 찾음. 프로그램 내부의 구조나 알고리즘을 보지 않고 추출된 테스트 케이스를 통해 테스트
* 신택스 기법 : 문법을  정해놓고 적합/부적합 입력 값에 따른 예상 결과가 제대로 나오는지 테스트 함. 문법에 맞지 않은 부적합한 값을 입력 했을 때 오류 메시지가 뜨는지 등을 테스트 
* 경계 값 분석 기법 : 동등 분할 기법과 비슷하지만, 영역 내의 임의 값을 테스트 데이터로 사용하는 것이 아니라 경계 값을 테스트 데이터로 사용
* 원인-결과 그래프 기법 : 입력 조건과 그 원인으로 부터 발생되는 출력 결과를 가지고 그래프를 만든 후 의사결정 테이블을 만듦, 테스트 케이스를 위한 데이터는 이 의사결정 테이블을 이용하여 작성

## 11. 구현 기반 테스트 (화이트 박스 테스트)

오류를 찾기 위해 원시 코드의 내부 구조를 테스트 설계의 기반으로 사용 하기 때문에 코드 기반 테스트라고 함

* 문장 검증 기준
* 분기 검증 기준
* 조건 검증 기준 
* 분기/좋건 검증 기준
* 다중 조건 검증 기준
* 기본 경로 테스트

## 12. 소프트웨어 개발 단계에 따른 테스트

단위 테스트로 프로그램의 기본 단위인 모듈을 테스트 하여 모듈 테스트라고 함








