# DAESEONG JU

## 🇰🇷 About Me
세종대학교 **건설환경공학** 전공/ **AI 연계 마이크로디그리** 이수 

SKplanet **dataengineering** 교육 (2/26-)


## 🛠️Stacks
<img src="https://img.shields.io/badge/python-3776AB?style=for-the-badge&logo=python&logoColor=white"><br>
![Matplotlib](https://img.shields.io/badge/Matplotlib-%23d9ead3.svg?style=for-the-badge&logo=Matplotlib&logoColor=black) ![Pandas](https://img.shields.io/badge/pandas-%23150458.svg?style=for-the-badge&logo=pandas&logoColor=white) ![NumPy](https://img.shields.io/badge/numpy-%23013243.svg?style=for-the-badge&logo=numpy&logoColor=white) ![scikit-learn](https://img.shields.io/badge/scikit--learn-%23F7931E.svg?style=for-the-badge&logo=scikit-learn&logoColor=white) ![Ultralytics](https://img.shields.io/badge/ultralytics-%23111F68.svg?style=for-the-badge&logo=ultralytics&logoColor=white) ![MySQL](https://img.shields.io/badge/mysql-4479A1.svg?style=for-the-badge&logo=mysql&logoColor=white)
<br>
<img src="https://img.shields.io/badge/github-181717?style=for-the-badge&logo=github&logoColor=white"> ![Claude](https://img.shields.io/badge/Claude-D97757?style=for-the-badge&logo=claude&logoColor=white) ![Amazon S3](https://img.shields.io/badge/Amazon%20S3-FF9900?style=for-the-badge&logo=amazons3&logoColor=white)
 ![AutoCAD](https://img.shields.io/badge/autocad-%23E51050.svg?style=for-the-badge&logo=autocad&logoColor=white)
<br>

## 📋Projects

#### 1. 포트홀 탐지 모델 및 매핑 시스템(Pothole Detection and Mapping System)
`Ultralytics` `YOLOv8` `PyTorch` `Claude`

- Claude Haiku와 Sonnet을 활용한 3단계 Human-in-the-loop 방식으로 데이터 라벨을 정제
- ICP와 MCP 기반 Conformal Prediction으로 모델의 불확실성을 검증(95% coverage)
- HNM(Hard Negative Mining)을 통해 포트홀 이미지를 분류하는 시스템을 구축.

- Hyperband 방식을 참고한 베이지안 최적화 기반 하이퍼파라미터 튜닝을 적용하여 모델 성능 개선.

- 로컬 서버 환경에서 OpenStreetMap을 활용하여 탐지된 포트홀을 지도에 시각화하는 매핑 시스템 구현.
#### 2. 포트홀 모델 실제 구현 및 로그 수집 파이프라인과 AWS기반 실제 서비스 배포 (Pothole Detection and Mapping System)
https://github.com/daexung/road-defect-pipeline 

- 'Kafka' , 'Airflow', 'AWS'

- 버스 블랙박스 영상에서 포트홀을 실시간 감지하고 Kafka →  Airflow → S3/RDS  → 대시보드까지 연결한 end-to-end 파이프라인 구축
- YOLOv8-CLS + Conformal Prediction 적용, 단순 이진 분류 대신 4단계 불확실성 기반 분류(N/U_N/U_P/P) 구현
- 서울시 버스 API 미작동으로 Naver 지도 크롤링을 통해 영등포구 13개 노선 GPS 데이터 직접 수집
- Airflow DAG로 HNM(Hard Negative Mining) 후보 자동 추출 및 일일 리포트 생성
- 멀티프로세싱 기반 13개 노선 동시 페이크 로그 생성기 구현 → Kafka 연동 파이프라인 테스트

#### 3. 비래염분 농도 데이터 분석 및 회귀 모델링 (Airborne Chloride Analysis and Regression Modeling)
`scikit-learn` `pandas` `numpy`
- 기상 및 환경 데이터를 활용한 비래염분 농도 데이터 분석
- EDA 및 Feature Selection을 통해 주요 영향 변수 도출
- 회귀 모델을 활용해 비래염분 농도 예측 모델 구축
- 동해,서해,남해 등 공간적 요인이 염분 농도에 미치는 영향 인사이트 도출

#### 4. 사면 안정성 다중분류 모델링
```scikit-learn``` ```pandas``` ```numpy```<br>

- 사면 데이터 활용 다중분류 모델 개발
- 안전 고려 자체 제작 지표 기반 파라미터 튜닝
<!--
**daexung/daexung** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.

Here are some ideas to get you started:

- 🔭 I’m currently working on ...
- 🌱 I’m currently learning ...
- 👯 I’m looking to collaborate on ...
- 🤔 I’m looking for help with ...
- 💬 Ask me about ...
- 📫 How to reach me: ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...
-->
