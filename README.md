# ElasticStackStudy

## ELK구성요소(Elasticsearch, Logstash, Kibana)

### Elasticsearch (데이터베이스)
Logstash로부터 받은 데이터를 검색 및 집계를 하여 필요한 관심 있는 정보를 획득.
Lucene 검색엔진 기반의 데이터베이스로 고성능의 검색 기능, 대규모 분산 시스템 기능 등을 제공한다. 표준 RESTful API와 JSON을 이용해 데이터를 처리합니다.

### Logstash (Input > filter > output 의 pipeline 구조로 수집하고 필터링하여 전달)
다양한 소스( DB, csv파일 등 )의 로그 또는 트랜잭션 데이터를 수집, 집계, 파싱하여 Elasticsearch로 전달
데이터 수집 파이프라인 도구입니다. 
각 데이터베이스의 데이터, 로우 데이터, 윈도우 이벤트 등으로부터 데이터를 수집합니다.
다양한 플러그인을 이용하여 데이터를 집계 및 보관, 서버 데이터 처리, 파이프라인으로 데이터를 수집하여 필터를 통해 변환 후
ElasticSearch로 전송합니다.

### Kibana (시각화 담당)
Elasticsearch의 빠른 검색을 통해 데이터를 시각화 및 모니터링
Elastic Search에 저장된 정보들을 검색 및 분석하고 시각화하는 기능을 갖고 있습니다.

### Beats (데이터 전송 담당)
경량 에이전트로 설치되어 데이터를 Logstash 또는 ElasticSearch로 전송합니다.
1) FileBeat
- 서버에서 로그파일을 제공합니다.
2) PacketBeat
- 응용 프로그램 서버간에 교환되는 트랜잭션에 대한 정보를 제공하는 네트워크 패킷 분석기 입니다.
3) MetricBeat
- 운영 체제 및 서비스에서 Metrics를 주기적으로 수집하는 서버 모니터링 에이전트입니다.
4) WinlogBeat
- Windows 이벤트 로그를 제공합니다.

## RDBMS와 Elasticsearch비교
![RDBMS_Elastic](./img/RDBMS대응.jpg)
![RDBMS_Elastic_](./img/RDBMS대응_.png)

## Elasticsearch 용어 정리
### 1) 클러스터( cluseter )
클러스터란 Elasticsearch에서 가장 큰 시스템 단위를 의미하며, 최소 하나 이상의 노드로 이루어진 노드들의 집합입니다.
서로 다른 클러스터는 데이터의 접근, 교환을 할 수 없는 독립적인 시스템으로 유지되며,
여러 대의 서버가 하나의 클러스터를 구성할 수 있고, 한 서버에 여러 개의 클러스터가 존재할수도 있습니다.

