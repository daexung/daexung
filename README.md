# DAESEONG JU
## About Me

건설환경공학 전공을 기반으로 데이터 엔지니어링과 AI 서비스 구현을 학습하고 있습니다.  
토목·인프라 도메인 문제를 데이터 수집, 모델링, 파이프라인, API, 시각화까지 연결하는 end-to-end 프로젝트에 관심이 있습니다.

- 세종대학교 건설환경공학 전공 / AI 연계 마이크로디그리 이수
- SKplanet Data Engineering 교육 과정 수강 중
- 관심 분야: Data Engineering, AI Service, Smart Construction, Infrastructure Data
- 토목기사, ADsP

## 🛠️ Stacks

<img src="https://img.shields.io/badge/python-3776AB?style=for-the-badge&logo=python&logoColor=white"> <img src="https://img.shields.io/badge/pandas-%23150458.svg?style=for-the-badge&logo=pandas&logoColor=white"> <img src="https://img.shields.io/badge/numpy-%23013243.svg?style=for-the-badge&logo=numpy&logoColor=white"> <img src="https://img.shields.io/badge/scikit--learn-%23F7931E.svg?style=for-the-badge&logo=scikit-learn&logoColor=white"> <img src="https://img.shields.io/badge/Matplotlib-%23d9ead3.svg?style=for-the-badge&logo=Matplotlib&logoColor=black"> <img src="https://img.shields.io/badge/ultralytics-%23111F68.svg?style=for-the-badge&logo=ultralytics&logoColor=white"> <img src="https://img.shields.io/badge/PyTorch-%23EE4C2C.svg?style=for-the-badge&logo=PyTorch&logoColor=white"> <img src="https://img.shields.io/badge/Claude-D97757?style=for-the-badge&logo=claude&logoColor=white"> <img src="https://img.shields.io/badge/Apache%20Kafka-000?style=for-the-badge&logo=apachekafka"> <img src="https://img.shields.io/badge/Apache%20Airflow-017CEE?style=for-the-badge&logo=Apache%20Airflow&logoColor=white"> <img src="https://img.shields.io/badge/docker-%230db7ed.svg?style=for-the-badge&logo=docker&logoColor=white"> <img src="https://img.shields.io/badge/AWS-%23FF9900.svg?style=for-the-badge&logo=amazon-aws&logoColor=white"> <img src="https://img.shields.io/badge/Amazon%20S3-FF9900?style=for-the-badge&logo=amazons3&logoColor=white"> <img src="https://img.shields.io/badge/postgres-%23316192.svg?style=for-the-badge&logo=postgresql&logoColor=white"> <img src="https://img.shields.io/badge/mysql-4479A1.svg?style=for-the-badge&logo=mysql&logoColor=white"> <img src="https://img.shields.io/badge/github-181717?style=for-the-badge&logo=github&logoColor=white"> <img src="https://img.shields.io/badge/autocad-%23E51050.svg?style=for-the-badge&logo=autocad&logoColor=white">

---

## Projects

### 1. 공사 리스크 기반 추가비용 산정 AI 에이전트

LangGraph FastAPI PostgreSQL pgvector AWS Bedrock React Docker

* 건설 현장의 기상 악화, 추가 물량, 자재 단가 변화, 장비 대기 등 리스크를 기반으로 추가비용을 산정하는 AI 에이전트 서비스 개발
* FastAPI 채팅 API와 LangGraph 기반 멀티 노드 구조를 연결하여 router, extractor, material, labor_cost, equipment, weather, aggregator, synthesize 흐름 구성
* LLM은 의도 분류, 입력값 추출, 최종 리포트 생성에 활용하고, 실제 비용 계산은 deterministic core 함수와 DB 조회 기반으로 처리
* PostgreSQL RDS와 pgvector를 활용해 표준품셈 RAG를 구축하고, 방수·콘크리트·철골 공종의 인건비 산정 fallback에 활용
* AWS Bedrock Claude, Titan Embeddings, KMA API, React, Docker 기반으로 MVP 서비스 배포

### 2. CP 기반 포트홀 탐지 모델 개발

YOLOv8 PyTorch Conformal Prediction Claude

* Claude Haiku·Sonnet을 활용한 3단계 Human-in-the-loop 방식으로 데이터 라벨 정제
* YOLOv8-CLS + Conformal Prediction 적용, 단순 이진 분류 대신 4단계 불확실성 기반 분류 구현
* ICP·MCP 기반 Conformal Prediction으로 모델 불확실성 검증
* Hard Negative Mining 후보를 추출하여 모델이 오분류하거나 불확실하게 판단한 샘플을 재학습 데이터로 활용할 수 있는 구조 설계
* Hyperband 방식을 참고한 베이지안 최적화 기반 하이퍼파라미터 튜닝 적용

### 3. 포트홀 탐지 데이터 파이프라인 및 AWS 서비스 배포

Kafka Airflow AWS YOLOv8 Conformal Prediction React FastAPI

* 버스 블랙박스 영상에서 포트홀을 실시간 감지하고 Kafka, S3/RDS, Airflow, 대시보드까지 연결한 end-to-end 파이프라인 구축
* 서울시 버스 API 미작동으로 Naver 지도 크롤링을 통해 영등포구 13개 노선 GPS 데이터 직접 수집
* Airflow DAG로 HNM 후보 자동 추출 및 일일 리포트 생성
* 멀티프로세싱 기반 13개 노선 동시 페이크 로그 생성기 구현 및 Kafka 연동 파이프라인 테스트

### 4. 비래염분 농도 데이터 분석 및 회귀 모델링

scikit-learn pandas numpy

* 기상·환경 데이터를 활용한 비래염분 농도 EDA 및 Feature Selection
* 회귀 모델을 활용한 비래염분 농도 예측 모델 구축
* 동해·서해·남해 등 공간적 요인이 염분 농도에 미치는 영향 인사이트 도출

### 5. 사면 안정성 다중분류 모델링

scikit-learn pandas numpy

* 사면 데이터를 활용한 다중분류 모델 개발
* 안전 고려 자체 제작 지표 기반 파라미터 튜닝
