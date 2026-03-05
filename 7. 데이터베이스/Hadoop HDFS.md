#데이터베이스 #빅데이터 #분산시스템 #HDFS #필수
## 정의
대용량 분산 파일 시스템
- 대용량 데이터를 여러 서버에 분산 저장하고 병렬 처리하는 Apache 오픈소스 프레임워크
- HDFS(Hadoop Distributed File System)는 Hadoop의 핵심 저장소 컴포넌트
## 키워드
* NameNode, DataNode, Secondary NameNode
* Block(128MB), Replication(복제), Rack Awareness
* MapReduce, YARN, 내결함성(Fault Tolerance)
## 암기법
* "네데세블복" - NameNode, DataNode, Secondary, Block, 복제
* "하둡은 HDFS+MR+YARN" - 저장(HDFS), 처리(MapReduce), 자원관리(YARN)
## 구성요소/특징/유형
### HDFS 핵심 구성요소
| 구성요소 | 역할 | 특징 |
|---------|------|------|
| NameNode | 마스터 노드 | 메타데이터 관리, 파일 위치 정보 |
| DataNode | 슬레이브 노드 | 실제 데이터 블록 저장 |
| Secondary NameNode | 보조 노드 | 메타데이터 병합 (백업 아님) |
### HDFS 특징
- **블록 기반 저장**: 기본 128MB 블록 단위 분할
- **복제(Replication)**: 기본 3개 복제본 유지
- **Rack Awareness**: 랙 장애 대비 분산 배치
- **Write Once Read Many**: 수정 불가, 추가만 가능
- **내결함성**: 노드 장애 시 자동 복구
### Hadoop 에코시스템
| 계층 | 컴포넌트 | 역할 |
|------|---------|------|
| 저장 | HDFS | 분산 파일 시스템 |
| 처리 | MapReduce | 분산 병렬 처리 |
| 자원관리 | YARN | 클러스터 자원 관리 |
| 쿼리 | Hive | SQL 기반 데이터 분석 |
| 실시간 | HBase | NoSQL 데이터베이스 |
| 수집 | Sqoop, Flume | 데이터 수집/이관 |
### HDFS 읽기/쓰기 프로세스
**읽기 프로세스**
1. 클라이언트 → NameNode: 파일 위치 요청
2. NameNode → 클라이언트: 블록 위치 정보 반환
3. 클라이언트 → DataNode: 직접 데이터 읽기
**쓰기 프로세스**
1. 클라이언트 → NameNode: 파일 생성 요청
2. NameNode: 블록 배치 결정
3. 클라이언트 → DataNode1 → DataNode2 → DataNode3: Pipeline 복제
### HDFS vs 기존 파일시스템
| 구분 | HDFS | 기존 파일시스템 |
|------|------|----------------|
| 파일 크기 | GB~TB | KB~MB |
| 확장성 | 수천 노드 | 단일 서버 |
| 내결함성 | 자동 복구 | 수동 백업 |
| 처리 방식 | 배치 처리 | 실시간 처리 |
## 구성도
```
┌─────────────────────────────────────────────────────┐
│                HDFS 아키텍처                         │
├─────────────────────────────────────────────────────┤
│                                                     │
│  ┌─────────────┐        ┌─────────────┐            │
│  │  NameNode   │◄──────▶│ Secondary   │            │
│  │  (Master)   │        │ NameNode    │            │
│  │             │        │ (Checkpoint)│            │
│  │ ┌─────────┐ │        └─────────────┘            │
│  │ │Metadata │ │                                   │
│  │ │FsImage  │ │                                   │
│  │ │EditLog  │ │                                   │
│  │ └─────────┘ │                                   │
│  └──────┬──────┘                                   │
│         │ Heartbeat / Block Report                 │
│    ┌────┴────┬────────────┐                       │
│    ▼         ▼            ▼                        │
│ ┌──────┐ ┌──────┐    ┌──────┐                     │
│ │Data  │ │Data  │    │Data  │                     │
│ │Node1 │ │Node2 │    │NodeN │                     │
│ │      │ │      │    │      │                     │
│ │┌────┐│ │┌────┐│    │┌────┐│                     │
│ ││Blk1││ ││Blk1││    ││Blk2││  (복제본)           │
│ │├────┤│ │├────┤│    │├────┤│                     │
│ ││Blk2││ ││Blk3││    ││Blk3││                     │
│ │└────┘│ │└────┘│    │└────┘│                     │
│ └──────┘ └──────┘    └──────┘                     │
│   Rack 1              Rack 2                       │
├─────────────────────────────────────────────────────┤
│  [데이터 쓰기 Pipeline]                             │
│  Client ──▶ DN1 ──▶ DN2 ──▶ DN3 (Replication)     │
└─────────────────────────────────────────────────────┘
```
## 연관 토픽
- [[MapReduce]] - Hadoop 분산 처리 모델
- [[YARN]] - Hadoop 자원 관리
- [[빅데이터 아키텍처]] - 빅데이터 시스템 설계
- [[NoSQL]] - 비정형 데이터 저장소
