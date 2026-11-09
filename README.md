# 안녕하세요, 백엔드 개발자 박지수입니다

**인프라 운영 경험을 바탕으로 서비스 전체 흐름을 이해하는 백엔드 개발자**를 목표로 합니다.

클라우드 MSP 엔지니어로 고객사 인프라를 구축·운영하며, 어떤 구조가 장애·지연·비용 문제로 이어지는지 직접 겪었습니다.
지금은 삼성 청년 SW·AI 아카데미(SSAFY) 16기에서 그 경험을 백엔드 설계로 옮기고 있습니다.

- 처음부터 문제를 덜 만드는 구조를 설계합니다. 배포 분리, 트랜잭션 경계, 헬스체크 기반 배포처럼 운영 단계의 문제를 미리 막는 쪽을 고릅니다.
- 증상에서 멈추지 않고 애플리케이션 → 네트워크 → OS 계층을 따라가 원인을 특정합니다.

<br>

## Tech Stack

**Backend**
<br>
<img src="https://img.shields.io/badge/Java-007396?style=flat-square&logo=openjdk&logoColor=white"/>
<img src="https://img.shields.io/badge/Spring_Boot-6DB33F?style=flat-square&logo=springboot&logoColor=white"/>
<img src="https://img.shields.io/badge/Spring_Security-6DB33F?style=flat-square&logo=springsecurity&logoColor=white"/>
<img src="https://img.shields.io/badge/JPA%20%2F%20QueryDSL-59666C?style=flat-square&logo=hibernate&logoColor=white"/>
<img src="https://img.shields.io/badge/JWT-000000?style=flat-square&logo=jsonwebtokens&logoColor=white"/>
<img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white"/>
<img src="https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white"/>

**Database**
<br>
<img src="https://img.shields.io/badge/MySQL-4479A1?style=flat-square&logo=mysql&logoColor=white"/>
<img src="https://img.shields.io/badge/Redis-DC382D?style=flat-square&logo=redis&logoColor=white"/>
<img src="https://img.shields.io/badge/AWS_RDS-527FFF?style=flat-square&logo=amazonrds&logoColor=white"/>

**Cloud · DevOps**
<br>
<img src="https://img.shields.io/badge/AWS-232F3E?style=flat-square&logo=amazonwebservices&logoColor=white"/>
<img src="https://img.shields.io/badge/GCP-4285F4?style=flat-square&logo=googlecloud&logoColor=white"/>
<img src="https://img.shields.io/badge/NAVER_Cloud-03C75A?style=flat-square&logo=naver&logoColor=white"/>
<img src="https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white"/>
<img src="https://img.shields.io/badge/GitHub_Actions-2088FF?style=flat-square&logo=githubactions&logoColor=white"/>
<img src="https://img.shields.io/badge/Linux%20%2F%20systemd-FCC624?style=flat-square&logo=linux&logoColor=black"/>

**Network · Security**
<br>
L2/L3/L4 · VLAN · Routing · ACL · Firewall · iptables · CCE/CVE 취약점 점검

<br>

## Experience

### 이노그리드 · 클라우드 인프라 구축 및 운영
`2024.10 – 2026.06` (인턴 2024.10 – 2025.02 / 사원 2025.02 – 2026.06)

| 프로젝트 | 내용 |
|---|---|
| **CSAP IaaS 인증 환경 구축**<br>2025.04 – 2025.09 · 13명 | IDC 2곳·장비 약 54대 규모에서 스위치 이중화, MAIN-DR 연결, HA·MGMT 망 분리 설계·구축 / DDoS 장비의 트래픽 경로상 배치 위치 제안 / CCE·CVE 취약점 점검·조치 |
| **고객사 홈페이지 AWS 이전·운영**<br>2025.12 – 2026.04 · 인프라 담당 | 구성도 설계부터 컷오버까지 담당 / ALB 노드가 Private Subnet에 배치되어 생긴 접속 지연 원인을 특정해 해소 / NAT Gateway 추가 없이 Bastion 경유 외부 통신으로 비용 제약 대응 |
| **인프라 점검·보고 자동화 툴**<br>2025.01 – 2026.03 · 단독 개발 | CloudWatch 지표 수집 → 엑셀 → 메일 발송 일일 점검 자동화 / 15개 기관 월간 보고서 PPT 자동 생성으로 **월 10시간 이상 → 5분** |

<br>

## Projects

| 프로젝트 | 역할 · 기술 | 핵심 성과 |
|---|---|---|
| **Seed**<br>AI 기반 초등학생 금융교육 시뮬레이션<br>2026.08 · 4명 (팀장) | DB 설계 · 인프라 · AI 신용평가<br>`Spring Boot` `FastAPI` `MySQL` `GCP` | 잔액 변경과 거래내역 기록을 한 트랜잭션으로 묶어 부분 반영 방지<br>Spring Boot(API 22개)·FastAPI(AI API 6개) 배포 분리로 **AI 재학습 시 백엔드 재시작 불필요**<br>배포 잡 종료 시 AI 서버가 함께 꺼지던 원인 특정 → systemd 기동 + 헬스체크 통과 시에만 배포 성공 처리<br>신용점수 MLP 모델 **검증 MAE 13.8점** (300~1000점 범위) |
| **SSAFY AI 챌린지**<br>텍스트 이미지 기반 VQA 모델<br>2026.09 · 4명 · 🏆 **지역 최우수상** | 검증 전략 · 전처리 · 추론 전략<br>`Qwen3-VL` `PyTorch` `PEFT(LoRA)` | 문장 파싱 방식을 A~D 토큰 logit 기반 분류로 바꿔 **파싱 실패 0%**<br>내부 검증셋 670문항으로 효과가 확인된 전략만 채택<br>정확도 **88.5% → 97.1%** |
| **PaintFinder**<br>물감 검색 및 작품별 사용 물감 관리<br>3명 | 기획 · 크롤러 · FE · BE · DB · 배포<br>`Spring Boot` `JPA/QueryDSL` `React` `AWS` | 제조사별 물감 데이터를 수집·정제해 공통 DB 스키마로 통합<br>Elastic Beanstalk·Amplify로 push만으로 FE·BE 자동 배포<br>502 장애: ALB 헬스체크의 301 리다이렉트와 배포 중 컨테이너 종료를 차례로 특정해 해결<br>CORS preflight 차단을 Spring Security 필터 체인에서 처리하도록 수정 |

<br>

## Certifications

| 자격증 | 발급 | 취득일 |
|---|---|---|
| Samsung Cloud Engineer - Associate | SAMSUNG SDS | 2025.09 |
| AWS Certified Solutions Architect - Associate | AWS | 2025.01 |
| NAVER Cloud Platform Certified Professional | NAVER Cloud | 2024.12 |
| OPIc 영어 IH | ACTFL | 2026.09 |

<br>

## Education

- **삼성 청년 SW·AI 아카데미(SSAFY) 16기** · 2026.07 – 현재
- **서울청년취업사관학교(SeSAC) 금천 4기** · 클라우드 기업 취업연계 과정 · 2024.08 – 2024.12 (640시간)
- **서울청년취업사관학교(SeSAC) 성동 1기** · SK쉴더스 채용연계 클라우드 기반 모빌리티 융합보안 과정 · 2023.10 – 2024.03 (720시간)
- **동국대학교 컴퓨터공학과** 졸업

<br>

## Learning

백엔드 CS를 주제별로 정리하고 스터디에서 발표하고 있습니다. 스레드·프로세스, JVM·GC, Spring, JDBC·JPA, 트랜잭션, Java 동시성을 다뤘습니다.

<br>

## Contact

<a href="mailto:jisoo449@naver.com"><img src="https://img.shields.io/badge/Email-jisoo449@naver.com-03C75A?style=flat-square&logo=naver&logoColor=white"/></a>
<a href="https://velog.io/@jisoo449/posts"><img src="https://img.shields.io/badge/Velog-jisoo449-20C997?style=flat-square&logo=velog&logoColor=white"/></a>
<a href="https://www.linkedin.com/in/jisoo-park-65ba0b266/"><img src="https://img.shields.io/badge/LinkedIn-박지수-0A66C2?style=flat-square&logo=linkedin&logoColor=white"/></a>
