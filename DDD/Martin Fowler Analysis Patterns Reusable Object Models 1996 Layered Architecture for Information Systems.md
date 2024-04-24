
> DDD 학습 도중 1996년 Layered Architecture에 대해서 찾아본 정보.
> 그 당시에는 Architecture Layer 하는게 어떤 장점이 있다고 봤을까 ? 
> [Martin Fowler Analysis Patterns Reusable Object 1996](https://uml2.narod.ru/files/docs/13/AnalysisPatterns.pdf)

Information system (IS) development involves more than an understanding of a domain, however. A world of many users, databases, and legacy systems must be accommodated.

인포메이션 시스템(IS) 개발에는 도메인에 대한 이해 이상의 것이 필요. 
많은 사용자, 데이터베이스, 레거시 시스템을 수용해야 하는 세계가 존재.

This chapter discusses architectural patterns for information systems. An architectural pattern describes the high-level division of a system into major subsystems and the dependencies among the subsystems. An information system architectural pattern divides the system into layers (or tiers).

이 장에서는 정보 시스템을 위한 아키텍처 패턴에 대해 설명.
아키텍처 패턴은 시스템을 주요 하위 시스템으로 나누고 하위 시스템 간의 종속성을 설명.
정보 시스템 아키텍처 패턴은 시스템을 계층(또는 티어)으로 나눔.

Most information systems are dominated by maintenance, which primarily involves coping with changing information demands.

대부분의 정보 시스템은 유지 보수가 지배적이며, 이는 주로 변화하는 정보 요구에 대처하는 것.

>[!Note] 
>(α)
>많은 사람들이 정보를 공유해야 하고 각각의 사용자는 서로다른 요구사항이 존재하기 때문에 변화하는 요구사항을 반영하는 유연성과 그에따른 유지보수가 지배적임.

#### 2 Tier shortcomings.
---

Server - Client

the two-tier architecture has many s<font color="#00ffcc">hortcomings due to the tight coupling of the user interface to the physical data layout</font>

2 Tier 아키텍처는 <font color="#00ffcc">사용자 인터페이스와 물리적 데이터 레이아웃 간의 긴밀한 결합으로 인해 많은 단점</font>이 존재함.

#### 3 Tier
---

Server - Middle - Client

three-tier architecture, also called the three-schema architecture, addresses this by <font color="#00ffcc">putting an intermediate layer between the user interface and the physical data</font>. 
This <font color="#00ffcc">domain tier closely models the concep-tual structure of the problem domain</font>.
Object technology is particularly well suited to three-tier approaches, and the domain tier can be placed on either client or server machines

3 Tier 아키텍처, 또는 세 개의 스키마 아키텍처 라고도 하는 것은 <font color="#00ffcc">사용자 인터페이스와 물리적 데이터 사이에 중간 계층</font>을 추가하여 이를 해결.
이 <font color="#00ffcc">도메인 계층은 문제 도메인의 개념적 구조를 밀접하게 모델링</font>.
객체의 기술적 활용은 3 Tier 접근 방식에 특히 적합하며, 도메인 계층은 클라이언트 또는 서버 머신에 배치될 수 있음.


Next we turn our <font color="#00ffcc">attention to applications, which manipulate the objects of the domain tier and display information on the user interface</font>. 
These <font color="#00ffcc">two responsibilities can be used to split the application into presentation and application logic</font>. 
The application logic can be organized as a set of facades on the domain tier, one facade for each presentation. This division has many advantages, and the application facades can be used to simplify client/server interactions. 
**Database interaction** can be handled in two ways. 
<font color="#00ffcc">The domain tier can be responsible for accessing the database, which handles its own persis-tence. </font>
This works well for object-oriented or simple relational systems. 
When there are complex data formats or multiple data sources, an <font color="#00ffcc">additional data interface layer may be required</font>

다음으로 <font color="#00ffcc">도메인 계층의 객체를 조작하고 사용자 인터페이스에 정보를 표시하는 애플리케이션</font>에 주목함. 
<font color="#00ffcc">이 두 가지 책임을 사용하여 애플리케이션을 프레젠테이션과 애플리케이션 로직으로 분할</font>할 수 있음. 애플리케이션 로직은 각 프레젠테이션에 대한 파사드 집합으로 구성될 수 있음.
이 분할에는 많은 이점이 있으며, 애플리케이션 파사드를 사용하여 클라이언트/서버 상호작용을 단순화할 수 있음.
데이터베이스 상호작용은 두 가지 방식으로 처리될 수 있음. 
<font color="#00ffcc">도메인 계층이 데이터베이스에 액세스하여 자체 Persistence을 처리</font>할 수 있음.
이는 객체 지향 또는 단순 관계형 시스템에서 잘 작동.
복잡한 데이터 형식이나 여러 데이터 소스가 있는 경우 <font color="#00ffcc">추가 데이터 인터페이스 계층이 필요</font>할 수 있음.

#### 3 Tier Arch 
---

external schema, conceptual schema, and storage (internal) schema. The storage schema is the database design, and the external schema is the applications; the new layer is the con-ceptual schema, which I refer to as the domain tier

외부 스키마, 개념 스키마, 스토리지(내부) 스키마.
스토리지 스키마는 데이터베이스 설계이고, 외부 스키마는 애플리케이션입니다. 여기에 새로운 계층인 개념 스키마, 즉 도메인 계층이 추가.

![3_tier](https://github.com/christopher3810/DomainDrivenDesign/assets/61622657/5bc4a97a-60e5-435b-8d94-aaaeb16a6c5e)

Objects represent a very good way to implement domain tiers. 
They support encapsulation, complex structural relationships, rules, processes, and all the things considered by advanced semantic model-ers. 
Reusable class libraries (or, better still, frameworks) are also at the heart of the domain tier. The key reusable objects of an enterprise are those that describe the domain—the framework that implements the domain tier (hence the term domain framework). 
Thus object modeling and domain tier develop-ment coincide very effectively. 
Implementation issues are somewhat more complex, but the basic princi-ple still works very well: <font color="#00ffcc">If the domain tier is expressed as an object-oriented model and implemented as a domain framework, then applications can be written against this domain framework. </font>
<font color="#00ffcc">This provides the separation between applications and databases that is so sorely needed.</font>

겍체는 도메인 계층을 구현하는 매우 좋은 방법.
캡슐화, 복잡한 구조적 관계, 규칙, 프로세스 등 고급 의미론 모델러들이 고려하는 모든 것을 지원.
재사용 가능한 클래스 라이브러리(또는 프레임워크가 더 나음)도 도메인 계층의 핵심.
기업의 핵심 재사용 가능 객체는 도메인을 설명하는 객체이며, 도메인 계층(따라서 도메인 프레임워크라는 용어 사용)을 구현하는 프레임워크가 중심이 됨. 
따라서 객체 모델링과 도메인 계층 개발은 매우 효과적으로 일치.
구현 이슈는 다소 복잡하지만, 기본 원리는 여전히 잘 작동. 
<font color="#00ffcc">도메인 계층이 객체 지향 모델로 표현되고 도메인 프레임워크로 구현되면, 애플리케이션은 이 도메인 프레임워크를 기반으로 작성될 수 있음. </font>
<font color="#00ffcc">이를 통해 절실히 필요한 애플리케이션과 데이터베이스 간의 분리가 이루어짐.</font>

#### The Location of the Domain Tier
---

With the domain tier we have two basic choices: We can place the domain tier on the clients,
or we can introduce a new layer of processors, which is the domain server and consists of one or many networked machines.

도메인 계층을 사용하면 두 가지 기본 선택지가 있음. 
도메인 계층을 클라이언트에 배치하거나 새로운 계층인 도메인 서버를 만들어 하나 이상의 네트워크 머신에 배치할 수 있음.

We need to consider concurrency issues. 
It is interesting that IS applica-tions probably use more concurrency than any other style of software yet worry about it least. 
This is due to the powerful transaction model that is usually handled very well by a database, freeing the application programmer from most concurrency headaches.

IS 애플리케이션은 아마도 다른 유형의 소프트웨어보다 더 많은 동시성을 사용하지만 이에 대해 가장 적게 걱정함. 
이는 데이터베이스에 의해 매우 잘 처리되는 강력한 트랜잭션 모델 때문에 애플리케이션 프로그래머가 대부분의 동시성 골칫거리에서 자유로워지기 때문.

As the domain tier is introduced, we have to <font color="#00ffcc">ask ourselves where the transaction boundary is to be.</font>

<font color="#00ffcc">도메인 계층이 도입되면서 트랜잭션 경계를 어디에 둘지 고민해야 함.</font>

OO databases provide a solution to this problem.

객체 지향 데이터베이스가 이 문제를 해결할 수 있음.

OO databases have responded to this by providing <font color="#00ffcc">gateways to tradi-tional database products</font>. In this approach an <font color="#00ffcc">OO database can act as the transaction control mechanism without necessarily storing any data itself.</font>

객체 지향 데이터베이스는<font color="#00ffcc"> 기존 데이터베이스 제품과의 게이트웨이</font>를 제공.
이 접근 방식에서 객<font color="#00ffcc">체 지향 데이터베이스는 실제로 어떤 데이터도 저장하지 않고 트랜잭션 제어 메커니즘 역할을 할 수 있음.</font>


If only a <font color="#00ffcc">single OO database is used</font>, then the <font color="#00ffcc">data storage layer is effec-tively collapsed into the domain tier. </font>
This is <font color="#00ffcc">permissible provided that this is an effective architecture and that extensions to the system to support other databases can be done in such a way that these other databases are provided behind the domain tier </font>so that they are not visible from applications

<font color="#00ffcc">단일 객체 지향 데이터베이스만 사용</font>된다면, <font color="#00ffcc">데이터 저장 계층은 효과적으로 도메인 계층에 통합됨. </font>
이것이 효과적인 아키텍처이고 시스템을 확장하여 <font color="#00ffcc">다른 데이터베이스를 지원할 수 있도록 다른 데이터베이스가 도메인 계층 뒤에 제공될 수 있다면, 이는 합당 한 방식이라고 받아들여 질 수 있음. </font>
그래야만 다른 데이터베이스가 애플리케이션에서 보이지 않습니다.

>[!warning]
>permissible - acceptable according to the law or a particular set of rules  : 허용이라는 두단어로는 이해가 안됨 풀어서 봐야함.

### Presentation and Application Logic
---


![application_tier](https://github.com/christopher3810/DomainDrivenDesign/assets/61622657/0bf6e646-599f-40f6-806b-a6a7af47d428)

Setting of parameters is an example of using type conversion. 
Various objects can be placed as parameters in this list, including USD/JPY spot, USD/JPY volatility, USD interest rate, and JPY interest rate. (The list depends on the currencies of the contracts in the portfolio.) 
The facade provides appropriate strings to the presentation, translating from the types in the domain tier (see Section 13.5). 
The facade typically provides a list of such strings for the presentation to place in its pop-up menu. 
The presentation can then select a string. 
The facade correlates the selected string to the underly-ing domain objects (a dictionary handles this nicely). 
In this way the <font color="#00ffcc">user interface is completely insulated from the domain model. </font>
In this situation the visibilities between the domains are defined as shown in Figure 12.6. Visibilities flow only from presentation to application logic to domain tier. 
<font color="#00ffcc">This line of visibility is valuable because it insulates the domain tier completely from the applications that rely on it.</font>

파라미터 설정은 유형 변환을 사용하는 예. 
이 목록에는 USD/JPY 현물 환율, USD/JPY 변동성, USD 이자율, JPY 이자율 등 다양한 객체가 파라미터로 배치될 수 있음(목록은 포트폴리오의 계약 통화에 따라 달라집니다). 
파사드는 도메인 계층의 유형에서 적절한 문자열로 변환하여 프레젠테이션 계층에 제공. 
**파사드는 일반적으로 프레젠테이션의 팝업 메뉴에 배치할 이러한 문자열 목록을 제공.** 
그러면 프레젠테이션에서 문자열을 선택할 수 있음. 
파사드는 선택한 문자열을 기본 도메인 객체와 상호 관계를 갖도록 함.(딕셔너리를 사용하면 유용함). 
이렇게 하면 <font color="#00ffcc">사용자 인터페이스가 도메인 모델로부터 완전히 격리.</font>
이 상황에서 도메인 간 가시성은 그림과 같이 정의. 
<font color="#00ffcc">가시성은 프레젠테이션에서 애플리케이션 로직, 도메인 계층으로만 흐름</font>. 
이 가시성 라인은 중요한데, 이를 통해 도메인 계층이 그것에 의존하는 여러 애플리케이션으로부터 <font color="#00ffcc">완전히 격리될 수 있기 때문.</font>

![facade_application_layer](https://github.com/christopher3810/DomainDrivenDesign/assets/61622657/80bdabb6-924b-41d8-b5ce-47a1f2e24c4f)

#### Advantages of the Presentation/Application Logic Split 
---

Layering is a good idea in principle, but it does have some disadvantages: the extra work is required to build the layer, and a performance penalty can be incurred in using it. <font color="#00ffcc">The important question is, are the advantages worth the costs?</font>

계층을 구축하기 위한 추가 작업이 필요하고, 계층을 사용하면 성능 저하가 발생할 수 있습니다. 중요한 질문은 <font color="#00ffcc">이점이 비용을 상쇄할 만한지 여부</font>


make event handlers that would typically be relayed as calls to the application facade. 
In either case develo pment organizations can use GUI specialists who need to know little about the domain model. 
Similarly the facade programmers need know nothing about how the GUI system works, they concern themselves with getting the right interactions with the domain types. 
Thus we see that there can be GUI developers who understand the user interface environment but need to know nothing about the domain model, and facade developers who understand the domain model but do not need to know about GUI develop-ment. 
The presentation/application logic split separates different required skills, allowing developers to learn less in order to make a contribution.

화면에 컨트롤을 그리고 일반적으로 애플리케이션 파사드에 대한 호출로 전달되는 이벤트 핸들러를 만들 수 있음. 
어떤 경우든 개발 조직에서는 도메인 모델에 대해 전혀 모르는 GUI 전문가를 사용할 수 있고, 파사드 프로그래머는 GUI 개발에 대해 전혀 모르는 상태에서 도메인 유형과의 적절한 상호작용에만 집중할 수 있음. 
프레젠테이션/애플리케이션 로직 분할을 통해 서로 다른 필요 기술을 분리할 수 있어, 개발자가 기여하기 위해 배워야 할 내용이 줄어듬.

The split allows multiple presentations to be developed from a single facade
단일 파사드에서 여러 프레젠테이션을 개발할 수 있다는 점도 장점.

building, this allows a quick turnaround for new presenta-tion styles. 
The facades provide a good platform for testing.
When facade and presen-tation are combined, the base computation can only be tested via the GUI, requiring manual testing (or GUI testing software for regression testing). 
When these are separated a test harness can be written for the facade's inter-face.

파사드와 프레젠테이션이 결합되어 있으면 기본 계산은 GUI를 통해서만 테스트할 수 있으며 수동 테스트(또는 회귀 테스트를 위한 GUI 테스팅 소프트웨어)가 필요함. 
이들이 분리되면 파사드의 인터페이스에 대한 테스트 하네스를 작성할 수 있음.

#### Stretching Facades in Client/Server Environments
---

![client_server_facade](https://github.com/christopher3810/DomainDrivenDesign/assets/61622657/34c67f74-83d2-4141-83d3-75c73541200a)

클라 서버 둘다 Facade 배치로 Facade 확장

><font color="#00ffcc">The point of stretching a facade is that it allows a single point of refer-ence for client/server interaction. </font>
>If a client facade (or a presentation) accesses the server domain classes directly, we will see many calls required across the network to populate the client. 
>These network calls can be a signif-icant overhead on performance. 
><font color="#00ffcc">The facades can have methods to build a single transfer packet and interpret such a packet into the facade's data. We can then pass all information in a single network call.</font>
>
><font color="#00ffcc">파사드를 확장하는 이유는 클라이언트/서버 상호작용을 위한 단일 참조 지점을 제공하기 위함. </font>
>클라이언트 파사드(또는 프레젠테이션)가 서버 도메인 클래스에 직접 액세스하면 클라이언트를 채우기 위해 네트워크를 통해 많은 호출이 필요할 수 있음. 
>이러한 네트워크 호출은 성능에 상당한 오버헤드가 될 수 있음.
><font color="#00ffcc">파사드에는 단일 전송 패킷을 작성하고 해당 패킷을 파사드의 데이터로 해석하는 메서드가 있을 수 있음. </font>
> <font color="#00ffcc">>그러면 모든 정보를 단일 네트워크 호출</font>로 전달할 수 있음.

### Database Interaction
---

<font color="#00ffcc">It can complicate the domain classes excessively by giving them two independent responsibilities: providing an executing model of the business and pulling data from a database. </font>
The code required to interact with the database can be quite substantial, bloating the classes excessively. If data has to be pulled from multiple databases and feeds, then this problem becomes critical. 
<font color="#00ffcc">An answer, of course, is to add another layer—a database interface tier, which is responsible </font><font color="#00ffcc">for loading the domain tier with data from the database and for updating the database when the domain changes. </font>
This tier is also in charge of handling feeds and other legacy interactions.

<font color="#00ffcc">관계형 데이터베이스를 사용하더라도 도메인 클래스가 데이터베이스 상호작용 코드로 인해 비대해질 수 있음.</font>
비즈니스 로직을 구현하고 데이터베이스에서 데이터를 가져오는 코드가 상당할 수 있음.
데이터를 여러 데이터베이스와 피드에서 가져와야 하는 경우 이 문제는 심각해짐.
해결책은 또 다른 계층, <font color="#00ffcc">데이터베이스 인터페이스 계층을 추가하는 것.</font>
<font color="#00ffcc">이 계층은 데이터베이스에서 도메인 계층을 로드하고 도메인이 변경되면 데이터베이스를 업데이트할 책임이 있음. </font>
또한 피드 및 기타 레거시 상호작용을 처리할 책임도 있음.

<font color="#00ffcc">The biggest difference between this tier and the application logic tier lies in the initiation of activity</font>. With the user interface, the user's action causes the presentation to initiate the activity. 
Since the presentation has visibility to the application logic, then it is straightforward for it to call the application logic. 
The initiation of activity follows the line of visibility. 
<font color="#00ffcc">However, this is not the case with the database interface. </font>
<font color="#00ffcc">The domain tier begins the process by wanting to save itself, but we do not want the domain model to see the database. </font>
<font color="#00ffcc">Thus the initiation of activity is opposite to the desired visibilities. </font>
One solution is to use the observer again, but that could well lead to a very high degree of message traffic. 

<font color="#00ffcc">이 계층과 애플리케이션 로직 계층 간의 가장 큰 차이점은 활동 개시 방식.</font>
사용자 인터페이스에서는 사용자 작업으로 인해 프레젠테이션이 활동을 개시.
프레젠테이션이 애플리케이션 로직을 볼 수 있으므로 애플리케이션 로직을 호출하는 것은 간단.
활동 개시는 가시성 라인을 따릅니다. 그러나 <font color="#00ffcc">데이터베이스 인터페이스의 경우에는 그렇지 않음. </font>
<font color="#00ffcc">도메인 계층이 프로세스를 시작하여 자신을 저장하고자 하지만, 우리는 도메인 모델이 데이터베이스를 보지 않기를 원함. </font>
<font color="#00ffcc">따라서 활동 개시는 원하는 가시성과 반대됨. </font>
한 가지 해결책은 옵저버를 다시 사용하는 것이지만, 그렇게 하면 매우 많은 메시지 트래픽이 발생할 수 있음.


<font color="#00ffcc">An alternative is to extend the architecture with an interface broker, which is visible to the domain tier. </font>
This broker provides a <font color="#00ffcc">very small interface</font>, which allows only messages that initiate the database interface. 
These might<font color="#00ffcc"> typically be calls as general as loadMe(anObject) and saveMe(anObject), which pass on all responsibility to dealing with the request to the database interface tier. </font>
<font color="#00ffcc">The broker's responsibility is to then pass this request onto a class in the database interface that can best handle the request. </font>
<font color="#00ffcc">Thus if we have spot contracts held in one database table and conventional options held in another, the interface broker first interrogates the object to find which it is and then passes the request onto the appropriate database interface class </font>

대안은 <font color="#00ffcc">아키텍처를 인터페이스 브로커로 확장하는 것. </font>
<font color="#00ffcc">이 브로커는 도메인 계층에 의해 볼 수 있음. </font>
이 브로커는 데이터베이스 인터페이스를 개시하는 메시지만 허용하는 <font color="#00ffcc">매우 작은 인터페이스를 제공. </font>
이는 <font color="#00ffcc">일반적으로 loadMe(anObject) 및 saveMe(anObject) 호출과 같이 요청 처리의 모든 책임을 데이터베이스 인터페이스 계층으로 전달. </font>
<font color="#00ffcc">브로커의 책임은 요청을 가장 잘 처리할 수 있는 데이터베이스 인터페이스 내의 클래스로 요청을 전달하는 것. </font>
<font color="#00ffcc">따라서 우리가 스팟 계약을 하나의 데이터베이스 테이블에 보유하고 있고 일반 옵션을 다른 테이블에 보유하고 있다면, 인터페이스 브로커는 먼저 해당 객체가 어떤 것인지를 조사한 다음 요청을 적절한 데이터베이스 인터페이스 클래스로 전달.</font>

![Database Integration](https://github.com/christopher3810/DomainDrivenDesign/assets/61622657/c2c79214-320d-4e7d-9f0b-db1b4e1ea27b)

Access to different databases can require different tools and skills. Specialized class libraries exist to interface to database products. 
A knowledge of SQL and of the specific database format may be required. 
Other databases (multidimensional, hierarchical) have their own interfaces and structures to learn. 
Separating this interaction out, particularly if there are many different data sources, allows team members to concentrate on areas where their skills are strongest.

다양한 데이터베이스에 대한 액세스에는 서로 다른 도구와 기술이 필요할 수 있음. 
특정 데이터베이스 제품과 인터페이스하기 위한 전문 클래스 라이브러리가 존재. 
SQL과 특정 데이터베이스 포맷에 대한 지식이 필요할 수 있음. 
다른 데이터베이스(다차원, 계층적)에는 자체 인터페이스와 구조가 있어 배워야 함. 
특히 다양한 데이터 소스가 있는 경우 이 상호작용을 분리하면 팀원들이 가장 역량이 뛰어난 영역에 집중할 수 있음.


### Concluding Thoughts
---

|계층|설명|
|---|---|
|도메인|전체 도메인에 적용되는 비즈니스 객체의 직접적인 모델. 개별 애플리케이션과 데이터 소스와 무관합니다.|
|애플리케이션 로직|애플리케이션을 위한 도메인 모델의 선택 및 단순화. 사용자 인터페이스 코드는 포함하지 않지만 사용자 인터페이스를 위한 도메인 계층의 파사드 집합을 제공합니다. 풍부한 도메인 계층 유형에서 프레젠테이션에 필요한 유형으로 변환합니다.|
|프레젠테이션|애플리케이션 파사드의 정보를 GUI 또는 문서 보고서로 포맷팅합니다. 사용자 인터페이스에만 관여하며 기본 도메인 계층을 모릅니다.|
|데이터 인터페이스|데이터 소스와 도메인 계층 간의 정보 이동을 담당합니다. 도메인 계층이 요청을 발행할 수 있는 간단한 인터페이스 브로커를 제공합니다. 도메인 계층과 데이터 소스 모두를 볼 수 있습니다. 사용된 데이터 소스 유형을 기반으로 하위 시스템으로 나뉩니다.|
