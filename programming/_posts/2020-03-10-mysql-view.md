---
layout: post
title: (MySQL) ERROR 1349 해결 (뷰테이블 관련 에러)
image: /assets/img/programming/200310/1.png
---

MySQL의 1349 에러는 뷰 테이블을 만들 때 서브쿼리 사용을 막는 에러입니다.
MySQL 5.6 이하 버전에서만 발생하며, 에러 로그는 다음과 같습니다.

> ERROR 1349 (HY000): View's SELECT contains a subquery in the FROM clause

제가 뷰 테이블을 만들기 위해 작성한 쿼리는 간략하게 표현해서 다음과 같았습니다.

~~~~sql
CREATE OR REPLACE VIEW `new_view` AS
SELECT
	C.*, I.agency_id, I.dsr_id
FROM customer_tb C
	INNER JOIN (
		SELECT * FROM customer_info_tb
		ORDER BY createDate DESC
	) I ON C.id = I.customer_id
GROUP BY C.id
~~~~

customer_tb와 customer_info_tb 두 개의 테이블을 Join하는 구문으로, 이 작업을 빈번하게 사용할 것 같아 뷰 테이블로 구성하고자 하였습니다. 
그리고 customer_info_tb의 최신 데이터를 기준으로 1:1로 가져와야 하는 상황이라 서브쿼리로 역순 정렬 후 Join해야 했습니다. 
그런데 MySQL 5.6 이하 버전에서는 뷰 테이블 생성 시에 서브쿼리를 사용하는 것을 제한하고 있었고 ERROR 1349를 뿜어냈습니다.

어떻게든 뷰 테이블로 빼야 하는 구문이라서 많이 고민했는데 해결방법은 아주 간단했습니다. **내부 서브쿼리를 뷰테이블로 만들면 됩니다**.

~~~~sql
CREATE OR REPLACE VIEW `info_desc_view` AS
SELECT * FROM customer_info_tb
ORDER BY createDate DESC

CREATE OR REPLACE VIEW `new_view` AS
SELECT
	C.*, I.agency_id, I.dsr_id
FROM customer_tb C
	INNER JOIN info_desc_view I ON C.id = I.customer_id
GROUP BY C.id
~~~~

이렇게 뷰 테이블을 두 개로 나누면 됩니다.
Join 해야 할 서브쿼리를 뷰 테이블로 생성한 뒤에, 그 뷰 테이블을 참조하는 결과 뷰 테이블을 생성하면 문제 없이 동작합니다.
아주 간단한 해결방법인데 두 시간 넘게 삽질했네요.
