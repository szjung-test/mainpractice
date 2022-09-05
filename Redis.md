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
  - Hash
  - Sorted set(Ranking)

- Hash table
