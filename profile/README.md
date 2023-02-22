
![KakaoTalk_Photo_2023-02-21-13-39-10](https://user-images.githubusercontent.com/40031858/220621978-902c35ca-2381-4cd3-b6e0-d54bdc484ad6.png)


# 캐싱 전략

## Cache-Aside(Lazy Loading)

- 항상 캐시를 먼저 체크하고, 없으면 원본(ex: DB) 에서 읽어온 후에 캐시에 저장함
- 장점: 필요한 데이터만 캐시에 저장되고, Cache Miss가 있어도 치명적이지 않음
- 단점: 최초 접근은 느림, 업데이트 주기가 일정하지 않기 때문에 캐시가 최신 데이터가 아닐 수 있음

![image](https://user-images.githubusercontent.com/40031858/220621384-e384df14-2d94-4a2d-8733-66f651e97ab7.png)

## Write-Through

- 데이터를 쓸 때 항상 캐시를 업데이트하여 최신 상태를 유지함.
- 장점: 캐시가 항상 동기화되어 있어 데이터가 최신이다.
- 단점: 자주 사용하지 않는 데이터도 캐시되고, 쓰기 지연시간이 증가한다

![image](https://user-images.githubusercontent.com/40031858/220621621-8698cf3b-a050-41bc-8940-8fd6587c87ad.png)

## Write-Back

- 데이터를 캐시에만 쓰고, 캐시의 데이터를 일정 주기로 DB에 업데이트
- 장점: 쓰기가 많은 경우 DB 부하를 줄일 수 있음
- 단점: 캐시가 DB에 쓰기 전에 장애가 생기면 데이터 유실 가능

![image](https://user-images.githubusercontent.com/40031858/220621842-c02f7f93-fba9-4d16-aef3-bf388cf3f48d.png)

