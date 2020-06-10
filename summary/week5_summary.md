# 상위 설계
## 1. 설계의 이해

### 좋은 설계의 조건
- 요구 분석 명세서의 내용을 설계서에 모두 포함해야 한다.
- 유지보수가 용이하도록 추적이 가능해야 한다.
- 변화에 쉽게 적응할 수 있어야 한다.
- 시스템 변경으로 인한 영향이 최소화되도록 국지적이어야 한다.
- 설계서는 읽기 쉽고, 이해하기 쉽게 작성해야 한다.
- 결국 모듈이 독립적이어야 하고, 모듈 내 요소들간의 응집력은 높게 설계되어야 하며 결합력은 낮게 설계되어야 한다.

### 설계의 종류
- 상위 설계: 예비설계(preliminary design)라고도 함
    - 아키텍처(구조) 설계: 시스템의 전체적인 구조
    - 데이터 설계: 시스템에 필요한 정보를 자료구조와 데이터베이스 설계에 반영
    - 시스템 분할: 전체 시스템을 여러 개의 서브시스템으로 나눈다
    - 인터페이스 정의: 시스템의 구조와 서브시스템들 사이의 인터페이스가 명확히 정의된다
    - 사용자 인터페이스 설계: 사용자가 익숙하고 편리하게 사용할 수 있도록 사용자 인터페이스를 설계한다
- 하위설계: 내부 구조를 상세히 나타내는 것과 유사
    - 각 모듈의 실제적인 내부를 알고리즘(pseudo-code)형태로 표현
    - 인터페이스에 대한 설명, 자료구조, 변수 등에 대한 상세한 정보를 작성
<hr>

## 2. 설계의 원리

### 분할과 정복
- 가장 세분화된 작은 시스템을 개발하고, 하나씩 위로 올라가면서 완성시키는 방법으로 개발하는 것
- 분산 시스템은 클라이언트와 서버로 분할
- 시스템은 여러 서브시스템으로 분할
- 서브시스템은 하나 이상의 패키지로 분할
- 패키지는 여러 클래스로 분할
- 클래스는 여러 메서드로 분할
- 무작정 작게 쪼개면 통신으로 인한 복잡도가 증가되므로 증가 비용과 처리의 용이성을 고려하여 결정

### 추상화
- 추상화(abstraction)란 문제에서 현재의 관심사에 초점을 맞추기 위해 특정한 목적과 관련된 필수 정보만 추출하여 강조하고 관련이 없는 세부 사항을 생략함으로 본질적인 문제에 집중할 수 있도록 하는 작업
- 객체지향에서의 추상화: 객체들의 공통점을 뽑아 클래스라는 이름을 붙여놓은 것
- 종류
    - 과정 추상화(procedure abstraction)
    - 데이터 추상화(data abstraction)
    - 제어 추상화(control abstraction)

#### 과정 추상화
- 상세 부분은 생략하고 전체 흐름만 파악할 수 있는 알고리즘 형태로 작성하는 것
- ex) 버블/퀵 등 언급 x, '정렬한다'
- ex) 합계구하는 함수 - GetSum()

#### 데이터 추상화
- 데이터와 메서드를 클래스 형태로 캡슐화하여 숨겨놓고, 사용자에게는 꼭 필요한 기능만 사용할 수 있게 개방한 구조

#### 제어 추상화
- 단계가 올라갈수록 표현이 더욱 간결해지고 특징만 나타나게 됨
- ex) 고급언어 | 어셈블리 언어 | 기계 언어 표현

### 단계적 분해
- 하향식 설계에서 사용되며, 기능을 점점 작은 단위로 나누어 점차적으로 구체화하는 방법

### 모듈화
- 실제로 개발할 수 있는 작은 단위로 나누는 것
- 모듈의 특징
    - 다른 것들과 구별될 수 있는 독립적인 기능을 갖는 단위(unit)
    - 유일한 이름
    - 독립적 컴파일 가능
    - 모듈에서 또다른 모듈 호출 가능
    - 다른 프로그램에서도 모듈 호출 가능
- 모듈은 완전한 독립 프로그램
- 모듈의 형태
    - 용도가 비슷: 라이브러리 함수, 그래픽 함수
    - 추상화된 자료, 서브루틴(subroutine), 프로시저(procedure), 객체 메서드(method)
<hr>

## 3. 소프트웨어 아키텍처(Software architecture)
- 대규모 소프트웨어를 개발할 때의 복잡성 해결 방법
    - 개발할 소프트웨어의 전체 구조를 가장 먼저 생각한다
    - 그 구조를 이루는 각 구성 요소를 찾는다
    - 각 구성 요소들 간의 명확한 관계를 설정한다
    - 일정한 규칙을 따른다
- 즉 잘 정의된 전체적인 구조와 품질 좋은 소프트웨어를 만들려면 소프트웨어 아키텍처가 필요!

### 아키텍처의 특징과 기능
- 소프트웨어 아키텍처: 외부에서 인식 할 수 있는 특성이 담긴 소프트웨어의 골격이 되는 기본구조, 시스템 전체에 대한 밑그림
- 그 외 소프트웨어 아키텍처 정의
    - 구성 요소
    - 구성 요소들 사이의 관계
    - 구성 요소들이 외부에 드러내는 속성
    - 구성 요소들과 주변 환경 사이의 관계
    - 구성 요소들이 제공하는 인터페이스
    - 구성 요소들의 협력 및 조립 방법
- 소프트웨어 아키텍처의 공통 특징
    - 개발할 소프트웨어의 전체적인 구조를 다룬다
    - 소프트웨어를 이루고 있는 여러 구성 요소(서브시스템, 컴포넌트)를 다룬다
    - 구성 요소들이 인터페이스를 통해서 어떻게 상호작용하는지를 정의해야 한다
    - 세부 내용보다는 중요한 부분만을 다룬다
    - 시스템 설계와 개발 시 적용되는 원칙과 지침이 있어야 한다
- 소프트웨어 아키텍처 설계 고려사항
     - 의사소통 도구로 활용할 수 있어야 한다
     - 구현에 대한 제약 사항을 정의해야 한다
     - 품질 속성(성능성, 사용성, 보안성, 안전성, 검증성, 변경성 등)을 결정해야 한다
     - 재사용할 수 있게 설계해야 한다

## 아키텍처의 품질 속성
### 시스템 품질 속성
- 가용성(availability): 시스템이 운용될 수 있는 확률, 장애 발생 없이 서비스를 제공할 수 있는 능력
    - 가용성이 중요한 품질 속성이라면 이중화처럼 여분의 구성 요소를 포함하도록 설계
- 변경용이성(modifiablity): 변경 요구사항 발생 시 쉽게 변경할 수 있는 능력
- 성능(performance): 이벤트 발생 시, 빠르고 적절하게 반응할 수 있는 능력
- 보안성(security): 허용되지 않은 접근에 대응할 수 있는 능력
- 사용성(usability): 사용하는 순간에 혼란스럽지 않고 고민하지 않게 하는 편의성
- 테스트용이성(testability): 요구 기능에 대하여 쉽고 철저하게 테스트할 수 있는지

### 비즈니스 품질 속성
- 시장적시성(time to market): 정해진 날짜에 소프트웨어를 출시해 경쟁력을 높일 수 있는 정도
- 비용과 이익(cost and benefit): 더 들여 효과적일 것이냐, 비용을 절약할 것이냐
- 예상 시스템 수명(predicted lifetime of the system)
    - 이것이 중요한 경우라면, 변경 용이성, 확장성, 이식성을 중요하게 고려해야 함
- 목표 시장(targeted market)
    - 기능성, 이식성 등을 충분히 고려
- 신규 판매 일정 또는 공개 일정(rollout schedule)
- 기존 시스템과의 통합(integration with legacy system)

### 이해 관계자별 품질 속성
- 발주자 관점: 개발비 적은 업체
- 사용자 관점: 사용하기 쉽고 빨리 이해
- 개발자 관점: 변경 용이성

### 아키텍처 구축 절차
1. 요구 사항 분석
- 요구 사항 취득, 식별, 명세, 분류, 검증
- 기능적/비기능적 요구사항 분류 및 명세
2. 아키텍처 분석
- 품질 속성 식별, 우선 순위 결정, 품질 속성 반영 방법 개발
3. 아키텍처 설계
- 관점 정의(이해관계자 별)
- 아키텍처 스타일 (pipe-filter, MVC, layering 등)
- 후보 아키텍쳐 도출 (SAD-Software Architecure Description 기술, 관점별 다이어그램 등)
4. 검증 및 승인
- 아키텍처 평가
- 아키텍쳐 상세화
- 아키텍쳐 승인

![UML4+1관점](https://slidesplayer.org/slide/14653385/90/images/36/5.+%EC%95%84%ED%82%A4%ED%85%8D%EC%B2%98%EC%9D%98+4%2B1+%EA%B4%80%EC%A0%90%282%29.jpg)

### 아키텍처 스타일
[보편적 아키텍처 스타일의 장점]
- 개발 시간 단축, 고품질의 소프트웨어 생산
- 수월한 의사소통
- 용이한 유지보수
- 검증된 아키텍처
- 구축 전 시스템 특성에 대한 시뮬레이션 가능
- 기존 시스템에 대한 빠른 이해

[아키텍처 스타일의 기능]
- 소프트웨어 시스템의 구조를 체계적으로 구성하기 위해 기본 스키마 제시
- 미리 정의된 서브시스템 제공
- 각 아키텍처 패턴 간 책임 명시
- 패턴 간의 관계를 조직화하는 규칙, 가이드라인 제시
- 문제를 소프트웨어 모듈 단위로 분해하는 방법 제시
- 분해한 소프트웨어 모듈 단위가 상호작용하는 방법을 제시

### 아키텍처 모델
![아키텍처 모델의 분류](https://slidesplayer.org/slide/14653385/90/images/43/7.+%EC%95%84%ED%82%A4%ED%85%8D%EC%B2%98+%EB%AA%A8%EB%8D%B8.jpg)

#### 데이터 중심형 모델
![데이터중심형모델](https://slidesplayer.org/slide/14653385/90/images/44/7-1+%EB%8D%B0%EC%9D%B4%ED%84%B0+%EC%A4%91%EC%8B%AC%ED%98%95+%EB%AA%A8%EB%8D%B8%281%29+repository+model+%ED%8A%B9%EC%A7%95%3A+%EC%A3%BC%EC%9A%94+%EB%8D%B0%EC%9D%B4%ED%84%B0%EA%B0%80+repository%EC%97%90%EC%84%9C+%EC%A4%91%EC%95%99+%EA%B4%80%EB%A6%AC.jpg)
![데이터중심형모델의](https://slidesplayer.org/slide/14653385/90/images/45/7-1+%EB%8D%B0%EC%9D%B4%ED%84%B0+%EC%A4%91%EC%8B%AC%ED%98%95+%EB%AA%A8%EB%8D%B8%282%29+%EC%9E%A5%EC%A0%90+%EB%8B%A8%EC%A0%90+%EB%8D%B0%EC%9D%B4%ED%84%B0%EA%B0%80+%ED%95%9C%EA%B5%B0%EB%8D%B0%EC%97%90+%EB%AA%A8%EC%97%AC+%EC%9E%88%EA%B8%B0+%EB%95%8C%EB%AC%B8%EC%97%90+%EB%8D%B0%EC%9D%B4%ED%84%B0%EB%A5%BC+%EB%AA%A8%EC%88%9C%EB%90%98%EC%A7%80+%EC%95%8A%EA%B3%A0+%EC%9D%BC%EA%B4%80%EC%84%B1+%EC%9E%88%EA%B2%8C+%EA%B4%80%EB%A6%AC+%EA%B0%80%EB%8A%A5.jpg)

#### 클라이언트-서버 모델
![클라이언트서버모델](https://slidesplayer.org/slide/14653385/90/images/46/7-2+client-server+%EB%AA%A8%EB%8D%B8+Client-server+%EB%AA%A8%EB%8D%B8+%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC%EB%A5%BC+%EC%9D%B4%EC%9A%A9%ED%95%98%EB%8A%94+%EB%B6%84%EC%82%B0+%EC%8B%9C%EC%8A%A4%ED%85%9C+%ED%98%95%ED%83%9C.jpg)

#### 계층 모델
![계층모델](https://slidesplayer.org/slide/14653385/90/images/47/7-3+%EA%B3%84%EC%B8%B5+%EB%AA%A8%EB%8D%B8+layering+%EB%AA%A8%EB%8D%B8+%EA%B8%B0%EB%8A%A5%EC%9D%84+%EB%AA%87+%EA%B0%9C%EC%9D%98+%EA%B3%84%EC%B8%B5%EC%9C%BC%EB%A1%9C+%EB%82%98%EB%88%84%EC%96%B4+%EB%B0%B0%EC%B9%98.jpg)

#### MVC 모델
![MVC1](https://slidesplayer.org/slide/14653385/90/images/48/7-4+MVC+%EB%AA%A8%EB%8D%B8%281%29+Model%2FView%2FController+%EB%AA%A8%EB%8D%B8+%EC%A4%91%EC%95%99+%EB%8D%B0%EC%9D%B4%ED%84%B0+%EA%B5%AC%EC%A1%B0.jpg)
![mvc2](https://slidesplayer.org/slide/14653385/90/images/49/7-4+MVC+%EB%AA%A8%EB%8D%B8%282%29+Model+%EC%84%9C%EB%B8%8C%EC%8B%9C%EC%8A%A4%ED%85%9C+View+%EC%84%9C%EB%B8%8C%EC%8B%9C%EC%8A%A4%ED%85%9C+Controller+%EC%84%9C%EB%B8%8C%EC%8B%9C%EC%8A%A4%ED%85%9C.jpg)
![MVC3](https://slidesplayer.org/slide/14653385/90/images/50/7-4+MVC+%EB%AA%A8%EB%8D%B8%283%29+%EC%9E%A5%EC%A0%90.+%EA%B4%80%EC%8B%AC%EC%9D%98+%EB%B6%84%EB%A6%AC.+%EB%8D%B0%EC%9D%B4%ED%84%B0%EB%A5%BC+%ED%99%94%EB%A9%B4%EC%97%90+%ED%91%9C%ED%98%84%28%EB%B7%B0%29%ED%95%98%EB%8A%94+%EB%94%94%EC%9E%90%EC%9D%B8%EA%B3%BC+%EB%A1%9C%EC%A7%81%28%EB%AA%A8%EB%8D%B8%29%EC%9D%84+%EB%B6%84%EB%A6%AC%ED%95%A8%EC%9C%BC%EB%A1%9C%EC%8D%A8+%EB%8A%90%EC%8A%A8%ED%95%9C+%EA%B2%B0%ED%95%A9+%EA%B0%80%EB%8A%A5.+%EA%B5%AC%EC%A1%B0+%EB%B3%80%EA%B2%BD+%EC%9A%94%EC%B2%AD+%EC%8B%9C+%EC%88%98%EC%A0%95+%EC%9A%A9%EC%9D%B4.+%EB%8B%A8%EC%A0%90..jpg)

#### 데이터 흐름 모델
![데이터흐름](https://slidesplayer.org/slide/14653385/90/images/51/7-5+%EB%8D%B0%EC%9D%B4%ED%84%B0+%ED%9D%90%EB%A6%84+%EB%AA%A8%EB%8D%B8+Pipe+and+filter+%EA%B5%AC%EC%A1%B0.jpg)

## 디자인패턴
### 디자인 패턴
- 자주 사용하는 설계 형를 정형화해서 이를 유형별로 설계 템플릿을 만들어 둔 것
- 효율성과 재사용성을 높일 수 있음
- 많은 개발자들이 경험으로 체득한 설계 지식을 검증하고 이를 추상화하여 일반화한 템플릿
[장점]
- 개발자(설계자) 간의 원활한 의사소통
- 소프트웨어 구조 파악 용이
- 재사용을 통한 개발 시간 단축
- 설계 변경 요청에 대한 유연한 대처
[단점]
- 객체지향 설계/구현 위주
- 초기 투자 비용 부담

### GoF 디자인 패턴
<table>
    <tr>
        <th rowspan=2>생성 패턴</th>
        <th>기능</th>
        <td>객체를 생성하는 것과 관련된 패턴<br>
        객체의 생성과 참조 과정을 추상화함으로써 시스템을 개발할 때 부담을 덜어준다</td>
    </tr>
    <tr>
        <th>종류</th>
        <td>
            <ul>
                <li>factory method</li>
                <li>singleton</li>
                <li>prototype</li>
                <li>builder</li>
                <li>abstract factory</li>
            </ul>
        </td>
    </tr>
    <tr>
        <th rowspan=2>구조 패턴</th>
        <th>기능</th>
        <td>프로그램 내의 자료구조나 인터페이스 구조 등 프로그램의 구조를 설계하는 데 많이 활용할 수 있는 패턴</td>
    </tr>
    <tr>
        <th>종류</th>
        <td>
            <ul>
                <li>adapter</li>
                <li>compoiste</li>
                <li>bridge</li>
                <li>decorator</li>
                <li>facade</li>
                <li>flyweight</li>
                <li>proxy</li>
            </ul>
        </td>
    </tr>
    <tr>
        <th rowspan=2>행위 패턴</th>
        <th>기능</th>
        <td>반복적으로 사용되는 객체들의 상호작용을 패턴화한 것으로, 클래스나 객체들이 상호작용하는 방법과 책임을 분산하는 방법을 정의</td>
    </tr>
    <tr>
        <th>종류</th>
        <td>
            <ul>
                <li>template method</li>
                <li>interpreter</li>
                <li>iterotor</li>
                <li>observer</li>
                <li>strategy</li>
                <li>visitor</li>
                <li>chain of responsibility</li>
                <li>command</li>
                <li>mediator</li>
                <li>state</li>
                <li>memento</li>
            </ul>
        </td>
    </tr>
</table>

- 참고 (https://slidesplayer.org/slide/14653385)

![factory](https://slidesplayer.org/slide/14653385/90/images/57/4-1+factory+method+%ED%8C%A8%ED%84%B4+Factory%3A+%EA%B3%B5%EC%9E%A5%2C+%EB%AC%BC%EA%B1%B4%EC%9D%84+%EB%A7%8C%EB%93%9C%EB%8A%94+%EA%B3%B3%28%EB%AC%BC%EA%B1%B4-%EC%9D%B8%EC%8A%A4%ED%84%B4%EC%8A%A4%29.jpg)
![singleton](https://slidesplayer.org/slide/14653385/90/images/58/4-2+Singleton+%ED%8C%A8%ED%84%B4+Singleton%3A+%E2%80%98%EB%8B%A8%EB%8F%85+%EA%B0%9C%EC%B2%B4%E2%80%99%2C+%E2%80%98%EB%8F%85%EC%8B%A0%EC%9E%90%E2%80%99%EB%9D%BC%EB%8A%94+%EB%9C%BB+%EB%A7%90%EA%B3%A0%EB%8F%84+%E2%80%98%EC%A0%95%ED%99%95%ED%9E%88+%ED%95%98%EB%82%98%EC%9D%98+%EC%9A%94%EC%86%8C%EB%A7%8C+%EA%B0%96%EB%8A%94+%EC%A7%91%ED%95%A9%E2%80%99.jpg)
![prototype](https://slidesplayer.org/slide/14653385/90/images/59/4-3+prototype+%ED%8C%A8%ED%84%B4+new+Object%28+%29%EB%B3%B4%EB%8B%A4+clone%28+%29%EC%9D%84+%EC%9D%B4%EC%9A%A9%ED%95%B4+%EA%B8%B0%EC%A1%B4%EC%9D%98+%EA%B2%83%EC%9D%84+%EB%B3%B5%EC%82%AC%ED%95%98%EC%97%AC+%EC%9D%BC%EB%B6%80%EB%A7%8C+%EB%B0%94%EA%BF%94+%EC%9D%B8%EC%8A%A4%ED%84%B4%EC%8A%A4+%EC%83%9D%EC%84%B1.+%EC%9D%BC%EB%B0%98%EC%A0%81%EC%9D%B8+prototype%28%EC%9B%90%ED%98%95%29%EC%9D%84+%EB%A7%8C%EB%93%A4%EC%96%B4%EB%86%93%EA%B3%A0%2C+%EA%B7%B8%EA%B2%83%EC%9D%84+%EB%B3%B5%EC%82%AC%ED%95%9C+%ED%9B%84+%ED%95%84%EC%9A%94%ED%95%9C+%EB%B6%80%EB%B6%84%EB%A7%8C+%EC%88%98%EC%A0%95%ED%95%98%EC%97%AC+%EC%82%AC%EC%9A%A9..jpg)
![builder](https://slidesplayer.org/slide/14653385/90/images/60/4-4+Builder+%ED%8C%A8%ED%84%B4+%EB%B3%B5%EC%9E%A1%ED%95%9C+%EC%9D%B8%EC%8A%A4%ED%84%B4%EC%8A%A4%EB%A5%BC+%EC%A1%B0%EB%A6%BD%ED%95%98%EC%97%AC+%EB%A7%8C%EB%93%9C%EB%8A%94+%EA%B5%AC%EC%A1%B0.jpg)
![abstract](https://slidesplayer.org/slide/14653385/90/images/61/4-5+abstract+factory+%ED%8C%A8%ED%84%B4+abstract+factory%3A+%E2%80%98%EC%B6%94%EC%83%81%EC%A0%81%EC%9D%B8+%EA%B3%B5%EC%9E%A5%E2%80%99%2C.jpg)
![composite](https://slidesplayer.org/slide/14653385/90/images/62/4-6+Composite+%ED%8C%A8%ED%84%B4+Composite%3A+%E2%80%98%ED%95%A9%EC%84%B1%EC%9D%98%E2%80%99%2C+%E2%80%98%ED%95%A9%EC%84%B1%EB%AC%BC%E2%80%99%2C+%E2%80%98%ED%98%BC%ED%95%A9+%EC%96%91%EC%8B%9D%E2%80%99.jpg)
![adapter](https://slidesplayer.org/slide/14653385/90/images/64/4-7+adapter+%ED%8C%A8%ED%84%B4%282%29+adapter+%ED%8C%A8%ED%84%B4+%EA%B8%B0%EC%A1%B4+%ED%81%B4%EB%9E%98%EC%8A%A4%EB%A5%BC+%EC%9E%AC%EC%82%AC%EC%9A%A9%ED%95%A0+%EC%88%98+%EC%9E%88%EB%8F%84%EB%A1%9D+%EC%A4%91%EA%B0%84%EC%97%90%EC%84%9C+%EB%A7%9E%EC%B6%B0%EC%A3%BC%EB%8A%94+%EC%97%AD%ED%95%A0.jpg)
![bridge](https://slidesplayer.org/slide/14653385/90/images/65/4-8+bridge+%ED%8C%A8%ED%84%B4+bridge%3A+%E2%80%98%EB%AC%B4%EC%97%87%EC%9D%B8%EA%B0%80%EB%A5%BC+%EC%97%B0%EA%B2%B0%ED%95%9C%EB%8B%A4%E2%80%99+%EB%91%90+%EC%9E%A5%EC%86%8C%EB%A5%BC+%EC%97%B0%EA%B2%B0%ED%95%98%EB%8A%94+%EC%97%AD%ED%95%A0.jpg)
![decorator](https://slidesplayer.org/slide/14653385/90/images/66/4-9+decorator+%ED%8C%A8%ED%84%B4+Decoration%3A+%E2%80%98%EC%9E%A5%EC%8B%9D%28%ED%8F%AC%EC%9E%A5%29%E2%80%99.jpg)
![facade](https://slidesplayer.org/slide/14653385/90/images/67/4-10+facade+%ED%8C%A8%ED%84%B4+Fa%C3%A7ade%3A+%E2%80%98%EA%B1%B4%EB%AC%BC%EC%9D%98+%EC%95%9E%EC%AA%BD+%EC%A0%95%EB%A9%B4%28%EC%A0%84%EB%A9%B4%29%E2%80%99.jpg)
![flyweight](https://slidesplayer.org/slide/14653385/90/images/68/4-11+Flyweight+%ED%8C%A8%ED%84%B4+Flyweight%3A+%E2%80%98%28%EA%B6%8C%ED%88%AC%C2%B7%EB%A0%88%EC%8A%AC%EB%A7%81+%EB%93%B1%EC%9D%98%29+%ED%94%8C%EB%9D%BC%EC%9D%B4%EA%B8%89+%EC%84%A0%EC%88%98%28%EB%B3%B4%ED%86%B5+%EC%B2%B4%EC%A4%91+48~51kg+%EC%82%AC%EC%9D%B4%29%E2%80%99%2C+%EC%A6%89+%EA%B0%80%EB%B2%BC%EC%9A%B4+%EA%B2%83.+%EB%A9%94%EB%AA%A8%EB%A6%AC%EB%A5%BC+%EA%B0%80%EB%B3%8D%EA%B2%8C+%ED%95%B4%EC%A4%80%EB%8B%A4%EA%B3%A0+%EC%A7%90%EC%9E%91%ED%95%A0+%EC%88%98+%EC%9E%88%EB%8B%A4..jpg)
![proxy](https://slidesplayer.org/slide/14653385/90/images/69/4-12+Proxy+%ED%8C%A8%ED%84%B4+Proxy%3A+%E2%80%98%EB%8C%80%EB%A6%AC%EC%9D%B8%E2%80%99%2C+%EC%A6%89+%EB%AD%94%EA%B0%80%EB%A5%BC+%EB%8C%80%EC%8B%A0%ED%95%B4%EC%84%9C+%EC%B2%98%EB%A6%AC%ED%95%98%EB%8A%94+%EA%B2%83.jpg)
![iterator1](https://slidesplayer.org/slide/14653385/90/images/70/4-13+iterator+%ED%8C%A8%ED%84%B4%281%29+Iterate%3A+%E2%80%98%EB%B0%98%EB%B3%B5%ED%95%98%EB%8B%A4%E2%80%99%2C+iterator%3A+%E2%80%98%EB%B0%98%EB%B3%B5%EC%9E%90%E2%80%99.jpg)
![iterator2](https://slidesplayer.org/slide/14653385/90/images/71/4-13+iterator+%ED%8C%A8%ED%84%B4%282%29.jpg)
![observer1](https://slidesplayer.org/slide/14653385/90/images/72/4-14+Observer+%ED%8C%A8%ED%84%B4%281%29+Observer%3A+%E2%80%98%EA%B4%80%EC%B0%B0%ED%95%98%EB%8A%94+%EC%82%AC%EB%9E%8C%E2%80%99%2C+%E2%80%98%EA%B4%80%EC%B0%B0%EC%9E%90%E2%80%99.jpg)
![observer2](https://slidesplayer.org/slide/14653385/90/images/73/4-14+Observer+%ED%8C%A8%ED%84%B4%282%29.jpg)
![strategy1](https://slidesplayer.org/slide/14653385/90/images/74/4-15+strategy+%ED%8C%A8%ED%84%B4%281%29+Strategy%3A+%E2%80%98%EC%A0%84%EB%9E%B5%E2%80%99%2C+%E2%80%98%EC%A0%84%EC%88%A0%E2%80%99+%EC%86%8C%ED%94%84%ED%8A%B8%EC%9B%A8%EC%96%B4+%EA%B0%9C%EB%B0%9C%EC%97%90%EC%84%9C+%EC%A0%84%EB%9E%B5%EC%9D%B4%EB%82%98+%EC%A0%84%EC%88%A0%EC%9D%80+%EC%95%8C%EA%B3%A0%EB%A6%AC%EC%A6%98%EC%9C%BC%EB%A1%9C+%EA%B5%AC%ED%98%84.jpg)
![strategy2](https://slidesplayer.org/slide/14653385/90/images/75/4-15+strategy+%ED%8C%A8%ED%84%B4%282%29+Strategy+%ED%8C%A8%ED%84%B4.jpg)
![template](https://slidesplayer.org/slide/14653385/90/images/76/4-16+template+method+%ED%8C%A8%ED%84%B4+Template%3A+%ED%95%98%EB%82%98%EC%9D%98+%E2%80%98%ED%8B%80%E2%80%99.jpg)
![visitor](https://slidesplayer.org/slide/14653385/90/images/77/4-17+Visitor+%ED%8C%A8%ED%84%B4%281%29+Visitor%3A+%E2%80%98%EB%B0%A9%EB%AC%B8%EC%9E%90.jpg)
![visitor2](https://slidesplayer.org/slide/14653385/90/images/78/4-17+Visitor+%ED%8C%A8%ED%84%B4%282%29+Visitor+%ED%8C%A8%ED%84%B4+%EA%B0%9D%EC%B2%B4%EC%9D%98+%EA%B5%AC%EC%A1%B0%EC%99%80+%EA%B8%B0%EB%8A%A5%EC%9D%84+%EB%B6%84%EB%A6%AC.jpg)

- chain of responsibility

![chainofresponsibility](https://slidesplayer.org/slide/14653385/90/images/79/4-18+chine+of+responsibility+%ED%8C%A8%ED%84%B4%281%29.jpg)
![chain2](https://slidesplayer.org/slide/14653385/90/images/80/4-18+chine+of+responsibility+%ED%8C%A8%ED%84%B4%282%29.jpg)
![command](https://slidesplayer.org/slide/14653385/90/images/81/4-19+command+%ED%8C%A8%ED%84%B4%281%29+Command%3A+%E2%80%98%EB%AA%85%EB%A0%B9%EC%96%B4%E2%80%99.jpg)
![command2](https://slidesplayer.org/slide/14653385/90/images/82/4-19+command+%ED%8C%A8%ED%84%B4%282%29+Command+%ED%8C%A8%ED%84%B4.jpg)
![mediator](https://slidesplayer.org/slide/14653385/90/images/83/4-20+mediator+%ED%8C%A8%ED%84%B4%281%29+Mediator%3A+%E2%80%98%EC%A4%91%EC%9E%AC%EC%9E%90%E2%80%99%2C+%E2%80%98%EC%A1%B0%EC%A0%95%EC%9E%90%E2%80%99%2C+%E2%80%98%EC%A4%91%EA%B0%9C%EC%9D%B8%E2%80%99.jpg)
![mediator2](https://slidesplayer.org/slide/14653385/90/images/84/4-20+mediator+%ED%8C%A8%ED%84%B4%282%29.jpg)
![state](https://slidesplayer.org/slide/14653385/90/images/85/4-21+state+%ED%8C%A8%ED%84%B4+State%3A+%E2%80%98%EC%83%81%ED%83%9C%E2%80%99+%EB%8F%99%EC%9D%BC%ED%95%9C+%EB%8F%99%EC%9E%91%EC%9D%84+%EA%B0%9D%EC%B2%B4+%EC%83%81%ED%83%9C%EC%97%90+%EB%94%B0%EB%9D%BC+%EB%8B%A4%EB%A5%B4%EA%B2%8C+%EC%B2%98%EB%A6%AC%ED%95%B4%EC%95%BC+%ED%95%A0+%EB%95%8C+%EC%82%AC%EC%9A%A9.jpg)
![memento](https://slidesplayer.org/slide/14653385/90/images/86/4-22+memento+%ED%8C%A8%ED%84%B4+Memento%3A+%E2%80%98%28%EC%82%AC%EB%9E%8C%2C+%EC%9E%A5%EC%86%8C%EB%A5%BC+%EA%B8%B0%EC%96%B5%ED%95%98%EA%B8%B0+%EC%9C%84%ED%95%9C%29+%EA%B8%B0%EB%85%90%ED%92%88%E2%80%99+undo+%EA%B8%B0%EB%8A%A5%EC%9D%84+%EA%B0%9C%EB%B0%9C%ED%95%A0+%EB%95%8C+%EC%9C%A0%EC%9A%A9.jpg)
![interpreter](https://slidesplayer.org/slide/14653385/90/images/87/4-23+interpreter+%ED%8C%A8%ED%84%B4+Interpreter%3A+%E2%80%98%ED%86%B5%EC%97%AD%EC%9E%90%E2%80%99+%EA%B0%84%EB%8B%A8%ED%95%9C+%EC%96%B8%EC%96%B4%EC%9D%98+%EB%AC%B8%EB%B2%95%EC%9D%84+%EC%A0%95%EC%9D%98%ED%95%98%EA%B3%A0+%ED%95%B4%EC%84%9D%ED%95%98%EB%8A%94+%EB%8D%B0+%EC%82%AC%EC%9A%A9.jpg)