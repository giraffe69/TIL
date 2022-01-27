#### <SELECT문>

---

**기본구조**

```
SELECT 컬럼명1,컬러명2,... From 테이블명; 
```

Select문 : 조건에 맞는 데이터. 조건문에 중첩가능.

> 컬럼 : 데이터를 선택할 테이블의 필드 이름
>
> 컬럼 별칭에 공백 및 특수문자가 포함될 때는 "" 필수.

---

```
   SELECT * FROM table WHERE id = 'user';
```

: table 테이블에서 id가 user의 컴럼 데이터를 모두 가져온다.



```
SELECT *|[DISTINCT] 컬럼명 [AS]["] 컬럼별칭 ["],
```

> '[DISTINCT]' : 중복도니 자료를 제외시킨 결과

```
SELECT [PREDICATE] [테이블명] 속성명 [AS별칭]
```

> SELECT 절에 '*'를 사용하면 해당 테이블에 있는 모든 컬럼 전체를 결과를 출력

```
FROM 테이블명 [테이블별칭],[.....]
```

```
[WHERE 조건 [AND | OR 조건]....]
```

> WHERE 절이 생략되면 해당 테이블의 모든 행이 결과로 출력

```
[GROUP BY 컬럼명[,컬럼명, ...]
```

```
[HAVING 조건]
```

```
[ORDER BY 컬럼명|컬럼INDEX [ASC+DESC...]], ...];
```

> '컬럼인덱스'는 SELECT절에 사용된 컬럼의 순번(1부터 사용)
>
> '[ASC|DESC]' 정렬방법, ASC는 오름차순이고 DESC는 내림차순. default는 ASC