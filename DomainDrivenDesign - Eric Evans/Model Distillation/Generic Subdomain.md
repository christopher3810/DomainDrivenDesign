
### Generic Subdomain
---

모델의 일부는 전문 지식을 포착하거나 전달하지 않고 복잡성을 더하곤 한다.\
부수적인 요소는 Core Domain을 식별하고 이해하는 일을 더욱 어렵게 만든다.\
모델은 일반 원칙이나 세부 사항 탓에 정체된다 (여기서 일반 원칙이란 누구나 알고 있는 것을 말하며, 세부사항은 주된 관심사가 아닌 보조적인 역할을 수행하는 전문 분야에 속하는 것을 의미한다.)\
그럼에도 아무리 일반적이더라도 이러한 그 밖의 요소는 시스템이 기능을 수행하고 모델을 완전히 표현하는데 중요하다.

>[!important]
>일반 적인 모델 요소가 매우 중요한 것으로 여겨지더라도 전체 도메인 모델은 시스템에서 가장 가치를 더하는 특별한 측면을 두드러지게 하고, 가능한 한 그 부분에 많은 힘이 실리게끔 구조화 해야 한다.\
>Core가 모든 상호 관련된 요소와 섞여 있다면 이렇게 하기 어렵다.
> 그러므로, 현재 진행 중인 프로젝트를 위한 것이 아닌 응집력 있는 하위 도메인을 식별하라.\
> 하위도메인에서 일반화된 모델 요소를 추출해서 별도 MODULE에 배치하라.\
> 해당 MODULE에는 여러분이 지닌 전문성의 자취를 남기지 않는다.\
> 일단 하위 도메인이 분리되고 나면 해당 하위 도메인의 개발에 대해서는 CoreDomain 보다 낮은 우선순위를 부여하고 그일에 핵심 개발자를 배치하지 않는다. (개발자가 거기서 도메인 지식을 얻지 못하므로)\
> Generic SubDomain에 대해서는 기성솔루션이나 공표된 모델을 고려해본다.

### 선택 1 : 기성 솔루션
---

장점

1. 개발할 코드가 적어짐
2. 유지보수 부담 외부화
3. 실수가 적고 코드가 완전한편임.

단점

1. 평가 및 이해 과정 필요
2. 업체를 신뢰하기가 힘듬.
3. 최소주의적인 구현이 아닐수 있으며 통합이 힘들 수 있음.
4. 통합하기가 힘듬, 별도의 Bounded Context가 존재 할 수 있음.
5. 플랫폼 의존성, 버전 의존성등 의존도가 생김.


### 선택 2 : 공표된 설계나 모델
---

장점

1. 사내 모델보다 더 성숙되고 많은 사람들의 통찰력을 반영.
2. 즉각적이고 높은 품질의 문서화.

단점

1. 요구사항에 fit 하지 않은 과한 설계일 수 있음.

>[!note]
>위와 같은 상황에 대한 예제는 많다.\
>정말 단순한 api call의 경우 resttemplate 만 필요 할 수도 있다.\
>별도의 로드벨런싱, 서킷브레이커와 같은 설계들을 필요로 하지 않기 때문이다.

톰 레터는 수학의 성공 비결을 다음과 같이 말한적이 있다.\
도용하라, 도용하라 누구의 업적도 여러분의 눈을 피해가지 못하게 하라.\
그저 항상 연구 중이라고 말하기만 하면 된다.

Generic subdomain을 공략할때 훌륭한 충고이다.

정형화돼 있고 엄밀한 모델이 있을 때는 그것을 사용하면 된다.

자주 사용되고 문서화가 잘 되어 있거나, 또는 더 좋은 경우 정형화된 모델을 활용할 수 있을 때는 시간과 노력을 낭비할 이유가 전혀 없다.

### 선택3 : 외주제작된 구현
---

장점

> 1. CoreDomain 과 관련된 업무에서 핵심 팀을 해방 시켜줌. (번역서)

이부분에 대해서는 아무리봐도 번역이 개구리다 라고 밖에 설명이 안됨

> "keeps core team free to work on core domain, where most knowledge is needed and accumulated"
> - 원문 -

"핵심 팀이 가장 많은 지식이 필요하고 축적되는 코어 도메인에서 자유롭게 일할 수 있게 해준다" 라는 표현이 맞음.

해방같은 소리를;;
해방이 말이 되려면 Core Domain을 외주사에서 제작을 해야함.
   
2. 팀을 영구히 확대하거나 Core Domain 지식이 흩어져 없어지지 않고 더욱 많은 개발을 이뤄낼 수 있음.
3. 명세가 외부 전달 되어야 함. 인터페이스 중심의 설계가 이뤄지고 하위 도메인을 일반화 된 상태로 유지하는데 도움이 된다.

단점

1. 인터페이스, 코딩표준 모든 중요 측면 대상 의사소통 필요.
2. 코드를 이해해야 하기 때문에 소유권을 내부로 이전할때 상당한 부담감 야기.
3. 코드 품질이 고르지 않음. 상대적 역량에 따라 코드품질이 좋거나 나쁘거나 함.

>[!important]
>자동화된 테스트는 외주 제작에 중요한 역할을 할 수 있음.\
>품질 수준 보증, 명세 명확, reintegration을 매끄럽게 하는 효과적인 접근 법은 외주 제작 컴포넌트에 대한 자동화된 인수 테스트를 명시하거나 아예 작성하는 것.\
>외주 제작된 구현은 공표된 설계나 모델과 잘 어울릴 수 있다.


### 선택4 : 사내 구현
---

장점

1. 통합하기 쉽다.
2. 원하는것만 가능.
3. 임시 계약자 할당 가능.

단점

1. 유지보수, 교육 부담
2. 패키지 개발에 필요한 시간과 비용 과소평가 쉬움.

사내구현도 물론 공표된 모델이나 설계와 잘어울림.

Generic SubDomain은 외부 설계 전문가를 적용 해볼수 있는 분야.

특화된 CoreDomain을 심층적으로 이해하지 않아도 되며 해당 도메인을 배울 기회가 좀처럼 없기 때문.

시간이 지나면 Core 모델을 구성하는 것은 한정되고, 점점 더 많은 일반화된 모델이 프레임워크로 구현되거나 적어도 공표된 모델 또는 분석 패턴의 형태로 이용할 수 있게 될 것이다.

여전히 사내에서 개발해야 하지만 CoreDomain과 나누는 데는 상당한 가치가 있다.

### 해운 프로젝트와 보험 프로젝트
---

| 프로젝트 | 구분 | 내용 |
|---------|------|------|
| 해운 프로젝트 | 유리한 점 | 1. core로부터 분리된 generic 모델 |
| | | 2. core 모델이 성숙해져서 자원을 축내지 않고 모델을 독차지 가능 |
| | | 3. 원하는 바를 정확하게 알게 됨 |
| | | 4. 국제 일정 관리를 위한 중요 지원 가능 |
| | | 5. generic 업무에 단기 계약직 프로그래머를 활용할 수 있음 |
| | 불리한 점 | 1. 일류 프로그래머가 핵심 영역에서 벗어나게 됨 |
| 보험 프로젝트 | 유리한 점 | 1. core로부터 분리된 generic 모델 |
| | 불리한 점 | 1. core 모델이 개발돼 있지 않아 다른 문제를 신경쓰게 되어 core 모델에 계속 소홀해짐 |
| | | 2. 파악되지 않은 요구사항 탓에 좀 더 단순한 북미에 국한된 변환으로도 충분할 상황에서 완전한 일반화를 시도함 |
| | | 3. 프로젝트에 오랫동안 참여해온 프로그래머가, core 모델이 아닌 업무에 할당됨 (해당 프로그래머는 도메인 지식의 저장고가 될 수도 있었음) |

우리 같은 기술자들은 시간대 변환과 같은 범위가 한정된 문제를 즐기는 경향이 있고 그러한 문제에 시간을 보내는것을 쉽게 정당화 한다.

우선순위를 바라보는 안목을 연마하면 보통 Core Domain을 염두에 두게 된다.

### 일반화가 재사용 가능하다는 의미는 아니다.
---

코드의 재사용에 대해서는 언급하지 않았다.

특히 코드의 재사용에 신경 써서는 안된다.

디스틸레이션의 기본적인 동기에 어긋난다.

모델의 개념을 여러 상황에 적용할 수 있더라도 완벽한 일반성을 갖춘 모델을 개발할 필요는 없다.

당면 업무에 필요한 부분에 대해서만 모델링하고 구현해도 된다.

>[!important]
>재사용을 목표로 설계할 일은 거의 없더라도, 일반 개념의 범위 내에서 설계를 유지하는 것과 관련해서는 엄격해야 한다.

agile process는 가장 위험스러운 업무를 먼저 다루는 식으로 위험을 관리할 것을 요구한다.

xp에서는 end to end 시스템을 구축하고 그것을 즉시 작동하게 만들도록 요구한다.

이러한 초기 시스템은 종종 기술적인 아키텍처 검증을 하는 역할을 한다.

일부 보조적인 Generic Subdomain을 다루는 보조시스템을 구축하고 싶어지는데, 이러한 시스템은 보통 분석하기가 더 쉽기 때뭍이다.

그러나 이렇게 하는 것은 위험 관리의 목적을 헛되게 할 수 있으므로 주의해야 한다.

위험도가 높은 업무를 추진하려는 모든 프로세스에서도 같은 원칙이 적용되는데, Core Domain은 매우 위험도가 높다.

이는 Core Domain이 종종 예상외로 쉽지 않고,Core Domain 없이는 프로젝트가 성공할수 없기 때문이다.

>[!important] 
> (α)
>Generic SubDomain 디스틸레이션 패턴은 위와 같은 서브도메인을 추출해 나가면서 CoreDomain의 정수를 추출하는 방법을 보여준다.\
>SubDomain을 추출하기 위해 모델과 코드를 어떻게 변경했었는지 논의를 해보았다.

