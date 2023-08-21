## ElasticSearch Essential

- [인프런 강의 링크](https://www.inflearn.com/course/elasticsearch-essential)
- 2023/08/13 ~ 2023/08/20

**섹션1. ElasticSearch 살펴보기**

- ES의 클러스터 구성 - 노드들로 구성, 어느 노드로 요청하더라도 응답은 같다
- ES 노드의 종류 - 마스터, 데이터, 코디네이팅, 인제스트
- 인덱스와 샤드 - 문서가 저장되는 논리적 공간, 실제 공간
- 매핑 - 문서의 구조를 나타냄, 정적매핑, 동적매핑

**섹션2. ElasticSearch 동작 이해하기**

- 색인 과정 이해하기 - 인덱스가 샤드에 저장되는 과정
- 검색 과정 이해하기 - 토큰을 만들어서 저장
- text와 keyword의 차이

**섹션3. ElasticSearch모니터링하기**

- cat api를 사용해서 상태 확인할 수 있다
  - _cat/health: 클러스터 전반적인 상태
  - _cat/indices: 인덱스 상태 확인
  - _cat/nodes: 노드 상태 확인
  - _cat/shards: 샤드 상태 확인
- 모니터링 지표 확인 -  kibana의 stack monitoring
