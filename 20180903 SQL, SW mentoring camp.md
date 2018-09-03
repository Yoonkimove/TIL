## Morning - SQL

* Grant - 권한 부여 구문



**Practice**

1. 구매테이블에서 구매 고객의 유니크한 이름만을 구해 보세요.

```sql
SELECT Customers.CustomerName
FROM Orders
INNER JOIN Customers ON Orders.CustomerID = Customers.CustomerID
GROUP BY Customers.CustomerName
```



2. 구매 테이블에서 5번 이상 구매한 고객의 이름과 구매한 횟수를 구해 보세요. 

```sql
SELECT Orders.OrderID, Customers.CustomerName, OrderDetails.Quantity
FROM ((Orders
INNER JOIN Customers ON Orders.CustomerID = Customers.CustomerID)
INNER JOIN OrderDetails ON Orders.OrderID = OrderDetails.OrderID)
WHERE Quantity>=5
GROUP BY Customers.CustomerName
```



3. 구매 테이블에서 가장 많이 판매된 5개의 상품의 이름과 횟수를 구해 보세요. 

```sql
SELECT Products.ProductName, sum(OrderDetails.Quantity)
FROM ((Orders
INNER JOIN Products ON Products.ProductID = OrderDetails.ProductID)
INNER JOIN OrderDetails ON Orders.OrderID = OrderDetails.OrderID)
group by (Products.ProductID)
ORDER BY sum(OrderDetails.Quantity) DESC
LIMIT 5;
```



4. 배송기사(Shippers)가 배송한 주문 건과 상품 갯수를 구해 보세요.

```sql
SELECT COUNT(DISTINCT Orders.OrderID), Shippers.ShipperID, SUM(OrderDetails.Quantity)
FROM ((Shippers
INNER JOIN Orders ON Shippers.ShipperID = Orders.ShipperID)
INNER JOIN OrderDetails ON Orders.OrderID = OrderDetails.OrderID)
GROUP BY Shippers.ShipperID
```



5. 가장 많이 판매된 상품의 이름을 구해 보세요. 

```sql
SELECT MAX(Quantity), Products.ProductName
FROM ((Orders
INNER JOIN Products ON Products.ProductID = OrderDetails.ProductID)
INNER JOIN OrderDetails ON Orders.OrderID = OrderDetails.OrderID)
```



## Afternoon - SW mentoring camp

시각디자인, 외국어, 심리학, 기획

일본은 새로운 시스템을 도입하는 것에 있어서 신중함

디테일의 중요성 - 사용자는 모두 다르기 때문

단계를 줄이는 게 늘 좋은 것은 아님

오프라인 프로젝트 - 현실의 문제 해결 (ex:개발도상국에서 자동차 부품으로 인큐베이터 개발)

스토리를 콘텐츠화시킬 수 있어야 - 궁금하게 만들기

강점 다섯 가지 정도를 포함한 나만의 이력서

MVP (Mimimum Viable Product) -> MLP (Minimum Loveable Product)

감성적 측면 강조, 사용성과 결합된 경험

개발 -> 배포 -> 수정 -> 다시 배포 의 빠른 사이클을 반복.

3가지 이상의 능력치 - 기준: 프로젝트를 할 수 있는지 여부

ex) 기획자 : 와이어프레임을 그릴 수 있는 기획자

	       	   레이아웃시트를 그릴 수 있는 기획자

그래서 뭘 할 수 있는가가 중요.

어떤 업무를 해야 하는지, 하게 될지 설명을 요구하기

분야를 개척한다고 생각하면 더 재미있음

리뷰: 보지 말고 읽고 쓰자

	남의 것을 편집하는 능력, 내 컨텐츠를 만드는 능력
	
	비교

뭘 만들든 상대를 편하게 해 줘야 - 포트폴리오도 마찬가지 (잘 정리된 홈페이지)

카테고리 정리 : 분야별이 제일 좋음

공동작업의 경우 자신의 역할 명확히 명시

쓴 프로그램, 기간 등 명시

이력은 최신순으로

블로그를 잘 관리했다면 그것도 포폴 될 수 있음

영상 편집, 모션그래픽 가능하면 좋음(프리미어, 에프터이펙트)

마케팅 툴 경험

회사가 커도 팀이 작으면 좋지 않음.

떠오르고 있는 회사

pogoory@gmail.com