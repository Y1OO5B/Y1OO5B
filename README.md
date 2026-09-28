<div align="center">
  <h1>Yoon-Bin Cho</h1>
  <p><b>Data Analyst & Platform Engineer</b></p>
  <a href="https://pie-havarti-ecc.notion.site/yoon-bin-cho-cv"><img src="https://img.shields.io/badge/Notion-Portfolio-black?logo=notion" alt="Notion"></a>
  <a href="mailto:ybch1oo5@gmail.com"><img src="https://img.shields.io/badge/Email-ybch1oo5@gmail.com-blue?logo=gmail" alt="Email"></a>
  <a href="https://www.linkedin.com/in/y1oo5b/"><img src="https://img.shields.io/badge/LinkedIn-Profile-blue?logo=linkedin" alt="LinkedIn"></a>
</div>

<br/>

데이터의 한계를 통제하고, 지표의 근거를 설계하며, 분석 결과를 실제 운영되는 파이프라인으로 연결합니다. 
단편적인 전후 비교를 넘어 통계적 인과추론과 공간적 이질성을 분석한 경험과 다단계의 검증을 거치는 무인 배포 자동화(CI/CD)를 구축한 경험이 있습니다. 
인천대학교 산업경영공학(전공) 및 도시공학(부전공)을 2027년 2월 졸업할 예정입니다.

### 💡 My Approach to AI Pair Development
> 최근 수행한 **돈워리(Donworry)** 와 **IP-BOSS** 시스템 구현은 AI 페어 개발을 통해 진행했습니다.
저는 요구사항을 실행 가능한 지시로 분해하고, 산출물의 한계를 통제하며, 시스템의 방어선을 설계하는 역할을 맡았습니다.
> - **위험 검증:** 인프라 배포 시 제가 작성한 테스트가 정상 작동하는지 확인하기 위해 22개의 변형 코드(mutated variants)를 심었고, 22개 모두 잡아낸 후에야 병합을 승인했습니다.
> - **결함 규명:** 셸 스크립트의 `ERR` 트랩이 `exit`이나 실패한 `X || die`를 잡지 못해 롤백이 작동하지 않던 운영 환경의 맹점을 코드로 규명하고, 13개의 실패 경로를 컨테이너에서 직접 재현하여 수정했습니다.
> - **다각도 리뷰:** 항만 결재 시스템에서는 7개 관점의 15개 검증 에이전트를 통해 리뷰를 발주하고, 선석 중복 차단 누락 및 배포 빌드에서의 CORS 구성 누락 등 29건의 지적을 채택 및 수정했습니다.

---

### 🏆 External Credentials
- **학술 논문 (SSCI):** Transportation Research Part A (2026), **제2저자 (3인 중)**. *"Impacts of new public transportation stops on bike-sharing demand: A counterfactual analysis using SeoulBike data."*
- **경진대회:** 과학기술정보통신부 주관 2026 AI Rookie 경진대회 본선 진출 (돈워리 프로젝트).
- **실무 경험:** 인천항만공사 미래내일일경험 프로젝트형 인턴 (2026.06–08).
- **연구 경험:** INU Data Science for Intelligent Systems Lab 학부연구생 (2023.05–2025.06).

---

### 🚀 Flagship Projects

#### 1. 돈워리 (Donworry) 플랫폼 — 운영 배포 자동화 및 데이터 파이프라인
**10인 팀 프로젝트 (운영 배포 자동화 및 모델링 담당)** | `Bash` `Docker` `GitHub Actions` `GCP` `PostgreSQL` `XGBoost`
- **Scale:** 산업재해 사업장×주 259,331,227행 산출, 549,558개 중 518,806개 사업장 매칭 연동 (94.4%).
- **CI/CD 파이프라인 가동:** 2개 워크플로, 4개 잡, 28단계 검증을 PR 및 main push 경로 필터로 제어. PR 병합 후 서버 반영까지 10분 이내, 배포 실행 시간 85초. 15개 필드의 JSONL 운영 원장 기록.
- **안전장치 설계:** 코드 배포 범위에서 무인 자동화를 경계 짓고, DB·시스템 설정·배포 스크립트 변경, 과금 및 IAM 조작은 의도적으로 수동 관문을 거치도록 설계.
- **해석 통제:** XGBoost가 PR-AUC는 0.0017 더 높았으나, 카운트 예측 목적에 맞춰 Poisson deviance가 낮은 기준 모형을 운영 모형으로 채택. 사업장 낙인 효과를 방지하기 위해 검증되지 않은 사고 확률을 숨기고 상위 구간(Band)만 제공.

#### 2. IP-BOSS — 인천항 선석운영지원시스템
**인천항만공사 제안·시연용 프로토타입 (기획 팀 프로젝트, 시스템 단독 구현)** | `TypeScript` `Python` `SQL`
- **Scale:** 47개 선석 대상, 시간당 실행되는 5개의 공공데이터 오픈 API 크론 잡, 약 9,900줄의 코드 규모, 11개 DB 테이블 구성.
- **상태 전이 설계:** 종이와 이메일로 돌던 '항만공사법 시행규칙 별지 제6호서식'을 분석하여, 결재 라인 분리 및 동시 승인을 제어하는 8상태 조건부 전이 모델로 설계.
- **물리적 조건 반영:** 인천 내항의 9m 조차 조건을 반영하여 추정이 아닌 실측 만조 시각 기준 ±3시간을 갑문 통과창으로 계산. DWT(재화중량톤수) 데이터가 부재할 경우 추정값을 명확히 '추정'으로 분리 기록.

#### 3. 신규 대중교통 도입에 따른 공유자전거 수요 변화 분석
**학부연구생 논문 프로젝트 (제2저자, 기여도 35%)** | `Python` `BSTS` `GWR` `QGIS`
- **Scale:** 2,843개 서울 공공자전거 대여소 중 데이터 요건을 충족하고 반경 100m 이내인 90개를 처치군으로, 나머지 2,640개를 대조군으로 분리. 대여와 반납을 분리하여 총 180개의 베이지안 구조적 시계열(BSTS) 모델 추정.
- **분석 결과:** 90개소 중 반납 수요는 46개소에서 유의미한 변화가 발생했으며 그중 61%가 증가. 대여 수요는 39개소에서 유의미한 변화 발생 (51% 증가, 49% 감소).
- **해석 통제:** 공간적 독립성을 가정하지 않고 Moran's I (-0.0473, p=0.2875) 검정을 직접 수행해 독립성을 확인. 상관계수 0.85 이상의 대조군 대여소만을 공변량으로 선정.

#### 4. Safe Watch — 산업재해 조기경보 스크리닝 패널 분석
**4인 팀 프로젝트 (기여도 70%)** | `Python` `XGBoost` `SHAP`
- **Scale:** 17개 시도 × 19개 산업 × 308주 = 99,484행의 패널 데이터 구성.
- **지표 및 평가 설계:** 단일 임계값이 아닌 시도별 Q70, Q90 기준선을 직접 설계. 민원 데이터의 Granger 선행성 검정을 수행하고, 회귀 성능(WMAPE 25.93%)과 경보 분류 성능(고위험 정밀도 90.09%)을 분리하여 평가.
- **해석 통제:** 예상과 달리 민원 데이터의 SHAP 기여도가 3.33%에 그친 사실을 숨기지 않고 보조적 행정 신호로 재정의하여 보고. 주간 단위 패널에서 월간 사업장 수 데이터를 단순 역산(Backfill)하여 시점 누수(Temporal Leakage)가 발생하지 않도록 통제.

#### 5. 다문화가구원 시공간 변화와 대중교통 접근성의 공간적 불일치
**개인 GIS 분석 (기여도 100%)** | `QGIS` `Python`
- **Scale:** 인천광역시 10개 군/구, 연수구 15개 행정동 공간 조인 및 버퍼 분석.
- **지표 설계:** 버스 및 도시철도 접근성 인덱스(TAI)와 수요 점수를 비교하는 Mismatch Index를 수식화하여 4개의 우선 검토 행정동 도출.
- **해석 통제:** 정류장 84개를 보유한 송도3동이 면적 대비 접근성 비율은 41.78%로 가장 낮은 점을 지적하여 '시설 존재'와 '실제 접근'을 구별. 수요 점수와 접근성 지표 간 상관계수가 -0.03으로 나타난 선형적 대응 부재 결과를 그대로 보고.

---

### 📊 Major Projects

| Project | Definition & Core Metric | Interpretive Restraint & Limits |
| :--- | :--- | :--- |
| **[LDI] 입법수요지수 산출** <br/>*(2인 팀, 60%)* | 약 26만 건의 뉴스/SNS 텍스트를 분석하여 297개 토픽 중 44개를 입법예고와 연계(14.8%). 상관분석 및 집단 비교를 통해 Buzz, Focus, Depth 등 5개 축의 LDI 가중치 산식 설계. | 화제성 볼륨이 아닌 의미와 시간 기준으로 매칭. 시드를 고정하여 토픽 응집도(C_v) 0.8 이상 유지. |
| **인천맛!잇다 BI** <br/>*(2인 팀, 50%)* | 13개 공공데이터를 융합해 4,878개 장소 마스터 도출. 음식점 수 단일 지표를 규모, 테마, 밀집, 관광, 교통의 다차원 합산 점수로 설계. | Tableau 구현 경험은 직접 하지 않았으며, 입력 데이터 구조 설계 및 진단문 로직을 전담. |
| **AirportDB 연계 분석** <br/>*(개인, 100%)* | 2개의 SQL VIEW로 기간과 지역 조건을 고정해 재현성을 확보하고, 3NF를 검토한 2개의 복합키 확장 지표 테이블 설계. | 분석 샘플 데이터베이스의 구조적 한계를 인정하고, 실제 항공 시장 전체로 과대 해석하지 않음. 최소 예약 30건 미만의 희소 샘플 배제. |

---

<div align="center">
  <img src="https://github-readme-stats.vercel.app/api?username=Y1OO5B&show_icons=true&theme=transparent" alt="Y1OO5B's GitHub stats" height="150" />
  <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=Y1OO5B&layout=compact&theme=transparent" alt="Top Languages" height="150" />
</div>

