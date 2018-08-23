## Morning - Programming Practice : Vendingmachine, Branch

* Object-oriented programming
  * Class : Definition of status and operations  
  * Instance :  Practical examples of concepts defined by classes  

* Class 쓸 때 규칙 : VendingMachine
  * Start with uppercase, No spacing between words)

*ex: class Kindle*

```
class Kindle:
    def __init__(self):  # 상태는 init에 나열해 줌
        self.power = False
        self.page = 1

    def toggle_power(self):
        self.power = not self.power

    def next_page(self):
        self.page = self.page + 1

    def prev_page(self):
        if self.page > 1:
            self.page = self.page - 1
```

* verlet integration

* 택시 운행 데이터 분석
  * 승차/하차 이벤트를 수요/공급으로 해석할 수 있다

* 이번 팀 프로젝트에서 만들어낼 수 있는 가치들

  1. 활용하기 쉬운 형태로 가공된 데이터 공유하기:

  - 데이터 수집 코드가 함께 제공되면 더 좋음

  - 데이터에 대한 설명이 제공되면 더 좋음

  - 다른 데이터와 연결되어 있으면 더 좋음

    - ex:책 데이터에는 ISBN 을, 지도라면 위/경도를

    -  → [Linked data](https://www.w3.org/DesignIssues/LinkedData.html) by TBL

    1. Use URIs as names for things
    2. Use HTTP URIs so that people can look up those names.
    3. When someone looks up a URI, provide useful information, using the standards (RDF*, SPARQL)
    4. Include links to other URIs. so that they can discover more things.

2. 이미 알려진 사실이나 정보를 쉽게 표현하기:

- 지역별 상권 특색 드러내기 (A 지역엔 카페가 많고, B 지역엔 서점이 많고 등)	
  - 시간의 흐름에 따른 집값 변화

3. 좋은 지표(index) 제시하기:

- Page View vs. Bounce rate(이탈률)

- conversion rate(전환율)

  - conversion/visit vs. conversion/user

- MMCU(Monthly Max Concurrent Users) vs. Accum. playtime

- 급하게 만든 예시:

- - 각 이디야 매장에 대해 가장 가까운 스벅 매장을 찾는다. E-S 벡터는 땅값이 임대료가 싸지는 방향과 기울기(짧을수록 크게 떨어지는 것?)를 나타낼 가능성이 있다.
  - Bilinear interpolation
  - 이렇게 얻어진 임대료 지형이 알려진 임대료와 얼마나 일치하는지, 특히 잘 맞는 지역은 어디인지 살펴보기.
  - 비슷하다면? 임대료가 알려지지 않은 지역에 대한 추정 가능
  - 이런 식의 인덱스를 여러개 만들어서 조합하기?