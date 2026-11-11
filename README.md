# 인적사항

- 이름: 이준필
- 연락처 : +82 010-5041-0009
- E-mail : [hanu9257@gmail.com](mailto:hanu9257@gmail.com)
- Linkedin : [https://www.linkedin.com/in/junepil-lee-648941245/](https://www.linkedin.com/in/junepil-lee-648941245/)
- Github: [https://github.com/junepil](https://github.com/junepil)
- 기술 블로그: [https://velog.io/@pil0009/posts](https://velog.io/@pil0009/posts)

# 경력

## 2023.01 - 2024.07 : 대한민국 공군 소프트웨어 개발병

- 급여 및 인사관리 체계 프론트앤드 시스템 개발
- 실사용자 회의를 통한 use case 도출, edge case 검증 등 system requirements 정의
- Vue3 를 이용한 컴포넌트, 커스텀 훅 및 레이아웃 구현
  - 근로자 신규 등록 시 Form에 저장해야 할 정보들이 50가지 정도가 되어 Pinia를 사용한 funnel 구조 구현을 통한 UX 개선
  - Combo box의 ~8k개의 부대 정보를 로딩시 클라이언트에서 1sec 이상 프리징 현상을 useInfinteQuery를 사용해 사용자의 스크롤에 따라 부대 정보를 추가로 불러오도록 개선
  - 기존 Pinia 기반으로 관리하던 Server State를 Tanstack Query를 사용해 리팩토링, state를 쉽게 관리하기 위해 TS의 namespace 기능을 사용해 일관적인 api 호출 방식 정의

## 2026.01 - 2026.02 Stormer : 그래프 기반 LLM 컨텍스트 관리 시스템

- 기존 채팅형 AI는 대화가 누적될수록 이전 맥락을 찾기 위해 긴 대화를 반복해서 탐색해야 하는 문제가 있어, React Flow와 Neo4j를 활용한 지식 그래프 구조 설계
- 사용자가 선택한 노드에 필요한 맥락만 전달하기 위해 Neo4j에서 루트 노드부터 대상 노드까지의 경로를 조회하고, 해당 경로상의 노드와 관계를 프롬프트 컨텍스트로 변환하는 LLM 질의 구조 구현
- Gemini, OpenAI, Claude를 교체해 사용할 수 있도록 LLM Provider를 추상화하고, 모델 응답을 JSON 형식의 지식 노드로 정규화
- 사용자, 프로젝트, 세션처럼 정합성이 필요한 데이터는 PostgreSQL와 GORM으로 관리하고, 지식 그래프의 그래프 탐색이 필요한 데이터는 Neo4j로 분리해 저장
- 프로젝트 소유권 검증을 API 공통 인증 계층에 적용하고 HttpOnly 세션 쿠키를 사용해 사용자별 그래프 데이터 접근을 제한

## 2026.03 - 2026.09 무신사 개인화팀 인턴

### CRM 파이프라인 멀티플랫폼 확장

- 단일 플랫폼을 전제로 작성된 CRM 백엔드에 29CM를 추가하면서 전체 플랫폼 확장 구조를 설계
-  요청 헤더 검증 전역 Filter와 플랫폼 컨텍스트 전달 구조를 구현해 플랫폼별 처리 경계를 분리
- 플랫폼별 기능 분화 대비를 위해 기능 가시성 매트릭스와 서비스 계층의 플랫폼별 정책 처리 설계 및 구현
- 멀티테넌트 환경의 테넌트별 ArgoCD 매니페스트와 발송 워커 모듈을 분리해 변경 범위와 실패 영향 범위 축소

### ClickHouse Cloud 마이그레이션 및 장애 대응

- 배치성 잡들로 작동하는 테이블들에 대한 마이그레이션 영향 범위 및 절차 산정
- 기존 테이블명을 기본값으로 유지하고 환경변수로 전환할 수 있도록 백엔드 레포지토리 계층을 리팩터링해 코드 병합만으로는 동작이 변하지 않고 설정 변경으로 전환 및 롤백 가능하도록 설계 및 구현
- ClickHouse Cloud의 extra credentials 등록을 위해 값이 없을 때 기존 쿼리와 동일하게 렌더링되는 쿼리 유틸리티 구현
- ClickHouse Cloud allowed list 갱신 이후 대량 발송 잡이 실패함에 따라 개발 환경에서 연결 단절을 재현하고 로그 대조로 가설 검증 후, 벤더 동작과 애플리케이션의 재시도 부재를 각각 발단과 취약성으로 분리해 RCA 작성 및 읽기 경로 재시도 추가

### 디스플레이 광고 시스템

- 광고 실시간 서빙 파이프라인 설계 
- OpenSearch 검색엔진 기반 색인기와 인메모리 bitmap 기반 색인기 PoC &amp; 파이프라인 아키텍쳐 설계
- OpenSearch index mapping &amp; 클러스터 아키텍쳐 설계
- 광고별 pacing 관리를 위한 kafka 이벤트 컨슈밍 컴포넌트 설계 및 구현
- indexer &amp; meter 컴포넌트에 대한 observability 확보용 grafana dashboard 구현

### 개발 인프라 및 시스템 기획

- ktlint를 통한 모노레포 포멧팅 표준 도입
- 모노레포 환경에서 Gradle 의존성 그래프 기반 변경 모듈 감지를 통한 CI 파이프라인 개선 설계

-  AWS Batch revision 자동 갱신을 이용하도록 CD 파이프라인 기획 및 설계

- 재사용 가능하도록 기존 GHA의 workflows와 action 모듈화 및 step 분리를 통한 가시성 개선

# 프로젝트

## 건국대학교 시설 예약 자동화 크롬 익스텐션

- wxt + vite를 이용한 멀티 브라우저 익스텐션 개발
- react, tailwind, tailwind-merge, cva, motion 라이브러리를 사용한 UI 구현

## 산불 조기 예측 시스템

- 2025 구글 솔루션 챌린지 참여를 위한 프로젝트 기획
- Github Action, ECR, EC2를 이용한 백엔드 컨테이너 배포 파이프라인 구축

## 건국대학교 연구실 안전교육 우회 스크립트

- 크롬 개발자도구를 이용한 패킷 정적 분석 및 URL 분석
- Github jsdelivr CDN을 이용한 스크립트 배포

# 기술 스택

- **Language**: JS &amp; TS, Golang, Kotlin, Python
- **Framework &amp; Library**: React, Vue3, Bum, Spring, Gradle, OpenSearch, Redis, ClickHouse, Kafka, Airflow
- **Infrasturcture**: Git, Github, ArgoCD, Docker, Terraform, Ansible, AWS, Grafana

# 학력

## 2021.03 - 현재 : 건국대학교 컴퓨터공학부

- OS와 System programing 등 깊은 내용까지 이해할 수 있는 low level 지식에 관심이 많습니다.

## 2025.07 - 2025.11 : UWA 교환학생

## OpenMp와 MPI를 사용한 행렬 곱셈 라이브러리 구현

- Cache의 False sharing을 방지하기 위해 word size 단위의 메모리 레이아웃 사용
- 각 코어 별 연산 시 필요한 데이터의 복사 및 수집 최적화
- zero-padding을 동적으로 구현하기 위한 ghost rows 복사 전략 구현

## The Deplomacy 보드게임 에이전트 제작

- MCTS, Minimax, A* 등 검색 알고리즘에 대한 학습
- Informed Search 기반의 보드게임 전략 수립