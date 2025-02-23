
```text
1장의 로드맵
1. 복잡성 떄문에 고심하고 있는 프로젝트에 DDD가 어떤 도움이 될 수 있을지 발견 하라.
2. DDD의 투자를 받을 만한 가치가 있는 프로젝트 인지 가늠할 수 있는 방법을 찾아라.
3. DDD의 일반적인 대안을 고려해보고 왜 그 대안들이 문제가 되는지 살펴보라.
4. 프로젝트의 첫발을 떼는 법을 배우는 것으로 DDD의 기초를 다져라.
5. 경영진, 도메인 전문가, 기술 팀원들에게 DDD를 팔 수 있는 법을 배우라.
6. 성공하는 법을 잘 알고 DDD를 사용해 생길 수 있는 문제점에 대응하라.
7. DDD를 구현하는 방법에 대해 배우고 있는 팀을 살펴보라.
```

#### 도메인 전문가가 없다면?

>일하고 있는 비즈니스의 과정을 아주 잘 알고 있는 사람들이 곧 도메인 전문가이지 별도의 직책을 요하는 것이 아니다. \
>많은 배경지식을 갖고 있는 사람, 상품 디자이너, 영업 인력일 수도 있다. \
>일하는 부분에 대해서 누구보다 잘 아는 사람이다.

#### 도메인 모델

>객체 모델로 종종 구현됨. \
>비즈니스적 의미에 정확히 부합하는 이름 데이터, 행동을 담고 있음. \
>크기가 작고, 아주 집중된 형태일 가능성이 크다.

### DDD를 해야 하는 이유
---

>[!Important]
>DDD를 왜 해야 할까
>1. 도메인 전문가와 개발자들의 눈높이를 맞춤으로써, 코더 뿐만 아니라 비즈니스 관계자에게도 말이 되는 소프트웨어를 만들게 한다. (하나의 응집되고 잘 짜여진 팀이 된다.)
>2. 비즈니스의 현 상태에 대해 더 알려줄 수 있게 된다. \
>   DDD를 통해 발견해나가는 토론에 모든 사람이 기여하게 되면서 모든 사람이 배우게 된다.
>3. 지식의 중앙화, 소프트웨어에 대한 이해가 부족 지식에 갇혀 있지 않게됨. \
>   개발자와 같은 선택된 일부만 내용을 이해하는 것은 아니라고 비즈니스 관계자가 확신하게 됨.
>4. 도메인 전문가, 개발자, 소프트웨어 사이에 translate가 불필요하다.
>5. 애자일을 기반한 빠른 경험적 모델링을 통해 더 나은 설계를 할 수 있음.

### 비즈니스 가치 제공의 힘든 부분
---

#### 1. 비즈니스 지식은 절대 중앙화 되지 않는다.

도메인 전문가와 소프트웨어 개발자 간의 이견은 소프트웨어 개발 노력에서 만나는 최악의 단절중 하나다.

비즈니스 관계자가 생각하고 행동하는 방식과 소프트웨어 개발자가 이를 해석한 내요 ㅇ사이의 변환/매핑을 수행하는 소프트웨어가 개발되곤 한다.

그리고 시간이 지남에 따라서 단절된 비용을 치루게 된다.

#### 2. 도메인 전문가 사이에 의견 불일치

1. 모델화 되는 도메인에 대한 경험치 차이
2. 서로 다른 전문 분야.

애매한 심적 모델을 만들어내 충돌하는 소프트웨어를 만들어 낼 수 있음.

#### 3.  개발 기술적 접근이 잘못된 방향으로 주도 할때

위 상황보다 더 심한것은 소프트웨어 개발 기술적 접근이 비즈니스 기능을 잘못된 방향으로 변경 할 때.

ERP 개발이 예시가 될 수 있는데, 비즈니스 전반 기능을 ERP 에 Fit 하게 맞춰서 변경하곤 하는 경향이 있다.

### DDD가 해줄 수 있는 일
---

1. DDD는 비즈니스에 가장 쓸모 있는 모델을 제공한다. \
   UL은 모든 팀의 동의에 의해 개발되며, 쓰이고, 모델에 바로 반영된다. \
   절대로 도메인 전문가와 소프트웨어 개발자를 나누지 않는다. \
   항상 우리여야 한다.

2. DDD는 비즈니스의 전략적 이니셔티브를 다룬다. \
   전략적 설계의 기술적 측면은 시스템과 비즈니스 문제를 명확하게 결합하는 데 목표가 있으며, 이는 각 비즈니스 단계의 서비스를 보호한다. \
   이는 서비스 지향 아키텍쳐 SOA, 비즈니스 주도 아키텍처 를 어떻게 성공시킬지의 측면에서 의미 있는 동기를 부여한다.

### 도메인 복잡성과 씨름하기
---

DDD 는 비즈니스에서 가장 중요한 영역에서부터 사용해나가야 한다.

가장 가치 있고 중요해서 가장 큰 배당금을 돌려받을 수 있다는 약속이 있는 곳에 투자 할 것이다.

핵심 도메인이라 부르는 이유다.

핵심 도메인과 그 다음으로 중요한 지원 서브도메인은 가장 큰 투자가 필요한 부분이다.

그런 뒤에야 우리는 복잡성의 의미에 대해 논의할 수 있다.

가능한 가장 단순하게 복잡한 도메인을 모델링 하라.

### Ubiquitous language
---

어떻게 유비쿼터스 언어를 정확히 담아내야 할까?

>[!important]
>1. 물리적이고 개념적인 도메인 그림을 그리고 이름과 행동을 붙여보라.
>2. 간단한 정의로 구성된 용어집을 만들라. \
>   잘 쓰일것 같은 용어든 그렇지 않은 용어든, 대체 용어를 나열하고 그 이유를 밝혀라. \
>   정의를 추가할 땐 도메인의 언어를 사용해야만 하기 때문에 재사용 가능한 구문을 만들어야만 한다.
>3. 만들어진 구문을 나머지 팀원들과 돌려보며 리뷰하자.

```java
public interface Customer {
	public void changePersonalName(
		String firstName, String lastName);
	public void postalAddress(PostalAddress postaladdress)
	public void relocateTo(PostalAddress postaladdress)
	public void chageHomeTelephone(Telephone telephone);
	public void disconnectHomeTelephone();
	public void changeMobileTelephone()
	public void disconnectMobileTelephone();
	public void primaryEmailAddress(EmailAddress emailAddress)
	public void secondaryEmailAddress(EmailAddress emailAddress)
}
```

Cusotmer가 지원해야할 다양한 비즈니스 목표를 명시적으로 반영헀으며, 지속적인 향상을 통해 개선 가능하다.

각 애플리케이션 서비스 메서드는 하나의 유스케이스 플로우나 사용자 스토리를 처리하도록 수정된다.

```java
@Transactional
public void changeCustomerPersonalName(){

// repository find

// null check

customer.changePersonalName(customerFistname, customerLastName)

}
```

유저 인터페이스 역시 더 좁은 사용자 목표를 반영해야 한다는 점을 의미한다.

>[!important]
>유비쿼터스 언어는 소프트웨어 모델 자체에 특정 핵심 비즈니스 도메인의 개념과 용어를 포착하는데 사용되는 팀의 패턴이다. \
>소프트웨어 모델은 잘 짜여진 팀에 의해 공식적으로 만들어지고 쓰여지는 명사, 형용사, 동사 그리고 풍부한 표현들을 통합한다.

>[!important]
>바운디드 컨텍스트당 하나의 유비쿼터스 언어가 있다. \
>바운디드 컨텍스트는 우리가 처음 상상했던 것보다 상대적으로 더 작다. \
>바운디드 컨텍스트는 격리된 비즈니스 도메인의 완전한 유비쿼터스 언어를 포착할 만큼 크다. \
>유비쿼터스 언어는 바운디드 컨텍스트를 격리시키고 그 안에서 프로젝트의 개발 업무를 수행하는 팀 내부에서만 유비쿼터스하다. \
>바운디드 컨텍스트를 밝혀내라, 그러므로서 당신은 도메인 모델 주변에 명시적인 경계를 그을 수 있다. \
>바운디드 컨텍스트 내 격리된 도메인 모델에서 유비쿼터스 언어를 토론하고, 연구하고, 개념화하고, 개발하고, 사용하라. \
>격리된 컨텍스트상에서 합의된 유비쿼터스 언어가 아닌 모든 개념을 거부하라.

>만약 바운디드 컨텍스트가 복잡하고 혁신적이며 변화를 겪는 오랜 시간 동안 견뎌내야 한다면, 당신 비즈니스의 미래에 대한 투자로 전술적 패턴을 사용하는 방안을 진지하게 고민해보라. \
>이는 당신의 핵심도메인에 높은 기술 수준의 최고 개발자가 참여한다는 가정을 전제한다.

위와 같은 핵심 도메인 레이어 내부에 주요 도메인 로직이 들어가 있는 것과 같은것을 고민해봐라 인것 같고, 높은 기술 수준의 최고 개발자 참여는 핵심 도메인 모델링이 그만큼 복잡성을 다루기가 힘들고 모델링 구현 방식이 하드 하다는 뜻.

### DDD는 무겁지 않다.
---

오히려 테스트 우선 방식에 따라 소프트웨어 모델을 빠르게 정제해나가는 방식에 더 가깝다.

1. 새로운 도메인 객체를 사용하는 방법을 보여주는 테스트를 작성하라.
2. 새로운 도메인 객체를 만들 때는 테스트를 컴파일할 수 있을 정도로 충분한 코드와 함께 작성 하라.
3. 테스트가 클라이언트가 도메인 객체를 사용하는 방법을 제대로 나타내고, 도메인 객체가 올바른 행동적 메소드 시그니처를 갖게 될 때까지 리팩토링 하라.
4. 테스트가 성공 할 때까지 각 도메인 객체의 행동을 구현하고, 부적절한 코드의 중복이 없어질 때 까지 도메인 객체를 리팩토링 하라.
5. 유비쿼터스 언어의 현재 의미에 맞는 도메인 객체를 사용해 테스트하는지 확인할 수 있도록, 도메인 전문가를 포함한 팀원에게 코드를 시연하라.
6. 새로운 도메인 객체의 정확성을 검증하기 위해 모든 가능한 측면을 따져 테스트를 추가한다.

>[!important]
>DDD는 경량 개발을 추구하지, 선행투자가 많이 필요한 설계는 아니다.
>DDD는 일반적인 애자일 개발과 정말 다르지 않다.

