# DAESEONG JU

## About Me

건설환경공학(토목기사) 도메인을 기반으로, 문제 해결에 필요한 데이터 기반을 구축해 AI와 서비스로 연결하는 엔지니어입니다.
데이터 수집 → 모델링 → 파이프라인 → API → 운영까지 경험한 프로젝트들을 기록해놨습니다.

- 세종대학교 건설환경공학 전공 · AI연계건설환경공학 마이크로디그리 이수
- SK플래닛 생성형 AI 활용 데이터 엔지니어 2기 수료 — **최종 프로젝트 최우수상 (BidFriend)**
- 토목기사 · ADsP
- 관심 분야: Data Engineering, AI Service, Smart Construction, Infrastructure Data

## Stacks

**Data Engineering**

<img src="https://img.shields.io/badge/Apache%20Kafka-000?style=for-the-badge&logo=apachekafka"> <img src="https://img.shields.io/badge/Apache%20Airflow-017CEE?style=for-the-badge&logo=Apache%20Airflow&logoColor=white"> <img src="https://img.shields.io/badge/postgres-%23316192.svg?style=for-the-badge&logo=postgresql&logoColor=white"> <img src="https://img.shields.io/badge/OpenSearch-005EB8?style=for-the-badge&logo=opensearch&logoColor=white"> <img src="https://img.shields.io/badge/Amazon%20S3-FF9900?style=for-the-badge&logo=amazons3&logoColor=white"> <img src="https://img.shields.io/badge/pandas-%23150458.svg?style=for-the-badge&logo=pandas&logoColor=white"> <img src="https://img.shields.io/badge/numpy-%23013243.svg?style=for-the-badge&logo=numpy&logoColor=white">

**AI · ML**

<img src="https://img.shields.io/badge/LangGraph-1C3C3C?style=for-the-badge&logo=langgraph&logoColor=white"> <img src="https://img.shields.io/badge/PyTorch-%23EE4C2C.svg?style=for-the-badge&logo=PyTorch&logoColor=white"> <img src="https://img.shields.io/badge/ultralytics-%23111F68.svg?style=for-the-badge&logo=ultralytics&logoColor=white"> <img src="https://img.shields.io/badge/scikit--learn-%23F7931E.svg?style=for-the-badge&logo=scikit-learn&logoColor=white"> <img src="https://img.shields.io/badge/Claude-D97757?style=for-the-badge&logo=claude&logoColor=white">

**Backend · Infra**

<img src="https://img.shields.io/badge/python-3776AB?style=for-the-badge&logo=python&logoColor=white"> <img src="https://img.shields.io/badge/docker-%230db7ed.svg?style=for-the-badge&logo=docker&logoColor=white"> <img src="https://img.shields.io/badge/AWS-%23FF9900.svg?style=for-the-badge&logo=amazon-aws&logoColor=white"> <img src="https://img.shields.io/badge/Grafana-F46800?style=for-the-badge&logo=grafana&logoColor=white"> <img src="https://img.shields.io/badge/GitHub%20Actions-2088FF?style=for-the-badge&logo=githubactions&logoColor=white">

**Domain**

<img src="https://img.shields.io/badge/autocad-%23E51050.svg?style=for-the-badge&logo=autocad&logoColor=white">

---

## Projects

### 1. BidFriend — 공공조달 입찰 분석·추천 서비스 🏆

`Airflow` `SQS·Lambda` `PostgreSQL` `OpenSearch` `Bedrock` `FastAPI` `React`

> 5인 팀 · 2026.06–08 · SK플래닛 최종 프로젝트 **최우수상** · 담당: ETL 파이프라인 · 품목분류 ML · 백엔드 · 프론트엔드 · CI/CD
> 레포: [pipeline](https://github.com/final-pjt-supply/bidmate-pipeline) · [backend](https://github.com/final-pjt-supply/bidmate-backend) · [frontend](https://github.com/final-pjt-supply/bidmate-frontend) · 서비스: bidfriend.ai.kr (2026.07–08 운영)

* 공고 **24,872건 · 문서 105,572건(114GB)** 수집·처리, 자격요건 병합 완료율 **98.9%**, 검색 색인 **1,206,455 청크** — 백필 완료 후 **무인 자동 수집 128건/일**
* Airflow 정기 수집 + **SQS 6큐·DLQ 6 + Lambda** 이벤트 처리 — 실행량 과금 구조로 유휴 시간 비용 제거(scale-to-zero)
* LLM 자격요건 추출: 3개 모델 × 36회 재현 비교로 Qwen3-Next-80B 채택, **evidence 그라운딩으로 근거 없는 값은 null 강등**
* 품목분류: 클러스터링 기각(882조합) 후 지도학습 재정의 — **TF-IDF+LinearSVC F1 0.802 vs LLM 최선 0.752**, NumPy 이식으로 189.6MB → **33MB**
* 운영: Grafana 18패널 관측 · Blue/Green 무중단 배포 · 인프라 비용 **$614/월** 실측 관리

### 2. 건설 리스크 비용 산정 에이전트 (Construction Risk Agent)

`LangGraph` `FastAPI` `PostgreSQL` `pgvector` `AWS Bedrock` `React` `Docker`

> 팀 프로젝트 · [civilai-construction-risk-agent](https://github.com/daexung/civilai-construction-risk-agent)

* 기상 악화·추가 물량·자재 단가·장비 대기 리스크 기반 **추가비용 자동 산정** 에이전트 — 표준품셈·노임단가 등 실제 기준 문서 사용
* LangGraph 멀티 노드 구성: router → extractor → [weather · material · labor_cost · equipment] → aggregator → synthesize
* **LLM은 계산하지 않음** — 의도 분류·입력 추출·리포트 문장화만 담당, 비용 계산은 deterministic 함수와 DB 조회로 처리
* PostgreSQL(RDS) + pgvector로 표준품셈 RAG 구축 — 산출식과 품셈 항목 번호 등 **근거를 명시한 리포트** 생성

### 3. CP 기반 포트홀 탐지 모델

`YOLOv8` `PyTorch` `Conformal Prediction` `Claude`

> 7인 팀

* 대시캠 이미지 **81,236장**(1:20 불균형) — Claude Haiku·Sonnet 2단계 + 육안 검수의 **3단계 Human-in-the-loop 라벨 정제**
* YOLOv8-CLS + **Conformal Prediction(ICP·MCP)** — 이진 분류 대신 불확실성 기반 4클래스 출력, 불확실한 예측은 판정에서 제외
* **F1 0.7697 → 0.8607 (오탐 45.4%↓ · 미탐 58.4%↓)** — 제외된 샘플은 Hard Negative Mining 재학습 루프로 환류
* YOLO 학습 구조 제약으로 Hyperband 대신 **TPE 기반 베이지안 최적화**로 전환해 튜닝

### 4. 포트홀 탐지 파이프라인 · AWS 배포

`Kafka` `Airflow` `AWS` `FastAPI` `React`

> 2인 팀 · 10일 · [road-defect-pipeline](https://github.com/daexung/pothole-classification-pipeline)

* 버스 블랙박스 추론 → Kafka → RDS·S3 → Airflow → 대시보드까지 **end-to-end 실시간 파이프라인** — 13개 노선 **초당 39건** 처리
* Consumer 이원화: 포트홀 확정·의심은 RDS 즉시 적재(서비스), 전체 로그는 S3 Parquet 데이터 레이크(재학습·분석)
* Airflow DAG — 실제 배차 간격(12분) 주기 GPS 클러스터링 · 일일 HNM 후보 추출 리포트
* 운영비 실측 **일 $3.9** — 공공 인프라 성격에 맞춘 비용 설계

### 5. 비래염분 농도 예측 모델

`scikit-learn` `pandas` `numpy`

> 개인 프로젝트 · [airborne-chloride-prediction](https://github.com/daexung/airborne-chloride-prediction)

* 변수선택(SBS·LASSO) × 타깃 변환(Log·Box-Cox) × 모델 4종 **전수 비교** — 최종 Test R² **0.7095** (변환 스케일 0.8237)
* GPR 95% 예측구간 커버리지 **0.9416** — 점 추정과 불확실성을 함께 제시
* 변수 중요도 최상위 Region — **동해안 농도 최고** 인사이트로 해안 구조물 설계 기준 차등 적용 제안

### 6. 사면 안정성 다중분류 모델

`scikit-learn` `pandas` `numpy`

> 개인 프로젝트 · [slope-stability-multiclass-classification](https://github.com/daexung/slope-stability-multiclass-classification)

* 미탐 비용이 크다는 도메인 판단을 **자체 평가 지표(unstable recall 가중)** 로 수식화해 튜닝
* 최상위 위험 클래스 **미탐 0건** 달성
