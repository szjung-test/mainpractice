# Redis
- 오픈소스 In-memory cache  솔루션으로 가방 많이 쓰이는 것은 redis와 memcached
- 사용처
  - 주로 cache를 저장하기 위한 저장소로 사용
  - 특수한 케이스는 DB 자체로 Redis를 사용
    - SQL은 지원하지 않음
  - 주로 대규모 서비스를 하는 곳에서 많이 사용함
- 제공 자료구조
  - Strings
    - Key/Value 를 사용하는 자료구조
    - Key를 이용해서 data를 저장하고 가져오게 된다.
    - key와 value를 저장하는 set 명령과 key로 value를 가져오는 get 명령이 있다.
    - 기본적인 hash table을 이용한다.
  - List
  - Set
    - 유일한 값들만 있는 집합을 유지하는 자료구조
    - 중복 불가
    - 특정 그룹을 저장할 때 사용할 수 있음
  - Hash
  - Sorted set(Ranking)

- Hash table


- Cache = 재요청이 오면 재계산 없이 바로 결과를 돌려주는 것
- 사용 예) 
- API 응답 cache 
  - 피드가 추가될 때(Redis 에 저장) - sorted set
  - 피드를 가져올 때

- Access Token
  - 서비스에서 매번 로그인을 하는 것을 피하기 위해서 Access Token(유효기간 존재)을 사용한다.
  - 보통은 access token에 대응하는 유저 정보가 DB에 존재함
  - JWT의 경우에는 해당 키가 유용한지 여부만 저장하고, 실제 유저 정보는 JWT안에 저장하는 경우가 많음
  - value는 어떻게 정의되어야할까? - User정보: User ID, User 권한, 토큰의 유효기간

- Rate Limit
  - 오픈 API나 외부에 특정 API를 제공하는 서비스의 경우 시간당 몇 회 호출이나, 하루에 몇 회 호출 등의 제한을 걸어 두는데, 이를 구현하는데도 많이 사용
  - Key 를 어떻게 정의하는지?
    - 특정 기간에 n회라는 제한이 있음
    - n회는 지속적으로 바뀌는 값이므로 Key에 반영되기 어려움
    - 시간이라는 정보는 계속 바뀌지만 해당 시간이라는 정보는 바뀌지 않음
    - 호출 횟수만 저장하면 된다.

# Host Metrics
- redis CPU 사용률
- 메모리 사용량(Free Memory)
- Network In/Out Size
- Disk Usage

# Redis 장애 원인
- Redis는 main thread 가 대부분의 처리를 하는 single threaded 형태이기 때문에, 하나의 명령에서 시간이 많이 걸리면 전체 성능 저하가 일어난다.
- 실제로 더 빠른 CPU, 더 많은 메모리를 달수록 좋아지지만 scale up을 하더라도, 잘못된 사용 패턴은 장애를 일으킬 수 있다.
- 메모리, 설정, 싱글스레드
