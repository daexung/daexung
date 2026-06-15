# DAESEONG JU
## 🇰🇷 About Me
세종대학교 **건설환경공학** 전공 / **AI 연계 마이크로디그리** 이수
SKplanet **Data Engineering** 교육 수강 중 (2026.02 ~ 2026.08)
- 토목기사
- ADsP

## 🛠️ Stacks

<img src="https://img.shields.io/badge/python-3776AB?style=for-the-badge&logo=python&logoColor=white">
![Pandas](https://img.shields.io/badge/pandas-%23150458.svg?style=for-the-badge&logo=pandas&logoColor=white)
![NumPy](https://img.shields.io/badge/numpy-%23013243.svg?style=for-the-badge&logo=numpy&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-%23F7931E.svg?style=for-the-badge&logo=scikit-learn&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-%23d9ead3.svg?style=for-the-badge&logo=Matplotlib&logoColor=black)
![Ultralytics](https://img.shields.io/badge/ultralytics-%23111F68.svg?style=for-the-badge&logo=ultralytics&logoColor=white)
![PyTorch](https://img.shields.io/badge/PyTorch-%23EE4C2C.svg?style=for-the-badge&logo=PyTorch&logoColor=white)
![Claude](https://img.shields.io/badge/Claude-D97757?style=for-the-badge&logo=claude&logoColor=white)
![Apache Kafka](https://img.shields.io/badge/Apache%20Kafka-000?style=for-the-badge&logo=apachekafka)
![Apache Airflow](https://img.shields.io/badge/Apache%20Airflow-017CEE?style=for-the-badge&logo=Apache%20Airflow&logoColor=white)
![Docker](https://img.shields.io/badge/docker-%230db7ed.svg?style=for-the-badge&logo=docker&logoColor=white)
![AWS](https://img.shields.io/badge/AWS-%23FF9900.svg?style=for-the-badge&logo=amazon-aws&logoColor=white)
![Amazon S3](https://img.shields.io/badge/Amazon%20S3-FF9900?style=for-the-badge&logo=amazons3&logoColor=white)
![Postgres](https://img.shields.io/badge/postgres-%23316192.svg?style=for-the-badge&logo=postgresql&logoColor=white)
![MySQL](https://img.shields.io/badge/mysql-4479A1.svg?style=for-the-badge&logo=mysql&logoColor=white)
<img src="https://img.shields.io/badge/github-181717?style=for-the-badge&logo=github&logoColor=white">
![AutoCAD](https://img.shields.io/badge/autocad-%23E51050.svg?style=for-the-badge&logo=autocad&logoColor=white)

---

## 📋 Projects

#### 1. 포트홀 탐지 모델링
`YOLOv8` `PyTorch` `Conformal Prediction` `Claude`
- Claude Haiku·Sonnet을 활용한 3단계 Human-in-the-loop 방식으로 데이터 라벨 정제
- ICP·MCP 기반 Conformal Prediction으로 모델 불확실성 검증 (95% coverage)
- HNM(Hard Negative Mining)으로 포트홀 이미지 분류 시스템 구축
- Hyperband 방식을 참고한 베이지안 최적화 기반 하이퍼파라미터 튜닝 적용

#### 2. 도로안전 알리미 — 포트홀 탐지 end-to-end 파이프라인
`Kafka` `Airflow` `AWS` `YOLOv8` `Conformal Prediction` `React` `FastAPI`
- 버스 블랙박스 영상에서 포트홀을 실시간 감지하고 Kafka → S3/RDS → Airflow → 대시보드까지 연결한 end-to-end 파이프라인 구축
- YOLOv8-CLS + Conformal Prediction 적용, 단순 이진 분류 대신 4단계 불확실성 기반 분류(N/U_N/U_P/P) 구현
- 서울시 버스 API 미작동으로 Naver 지도 크롤링을 통해 영등포구 13개 노선 GPS 데이터 직접 수집
- Airflow DAG로 HNM(Hard Negative Mining) 후보 자동 추출 및 일일 리포트 생성
- 멀티프로세싱 기반 13개 노선 동시 페이크 로그 생성기 구현 → Kafka 연동 파이프라인 테스트

#### 3. 비래염분 농도 데이터 분석 및 회귀 모델링
`scikit-learn` `pandas` `numpy`
- 기상·환경 데이터를 활용한 비래염분 농도 EDA 및 Feature Selection
- 회귀 모델로 비래염분 농도 예측 모델 구축
- 동해·서해·남해 등 공간적 요인이 염분 농도에 미치는 영향 인사이트 도출

#### 4. 사면 안정성 다중분류 모델링
`scikit-learn` `pandas` `numpy`
- 사면 데이터 활용 다중분류 모델 개발
- 안전 고려 자체 제작 지표 기반 파라미터 튜닝
