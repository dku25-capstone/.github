# 📊 캡스톤디자인. ChatGraph

## 목차
| 순번 | 목차 |
|:--:|:--:|
| 1 | [개요](#개요) |
| 2 | [기간](#기간) |
| 3 | [팀원](#팀원) |
| 4 | [기술 스택](#기술-스택) |
| 5 | [주요 기능](#주요-기능) |
| 6 | [시스템 아키텍처](#시스템-아키텍처) |
| 7 | [설치 및 실행 방법](#설치-및-실행-방법) |
| 8 | [프로젝트 구조](#프로젝트-구조) |
| 9 | [향후 계획](#향후-계획) |

---

## 개요
> ChatGPT 질의응답 내용을 트리/그래프 형태로 시각화하여 대화 흐름을 한눈에 파악할 수 있는 웹 서비스

---

## 기간
> 2025.03 ~ 현재

---

## 팀원
| 이름 | 역할 | Github |
|------|------|--------|
| 이영민 | FE | <a href="https://github.com/E0min"><img src="https://avatars.githubusercontent.com/u/59902527?v=4" width="64"></a> |
| 이상현 | FE | <a href="https://github.com/SangHyun01"><img src="https://avatars.githubusercontent.com/u/143057125?v=4" width="64"></a> |
| 이재경 | BE | <a href="https://github.com/jkli51"><img src="https://avatars.githubusercontent.com/u/104336147?v=4" width="64"></a> |
| 장준서 | BE | <a href="https://github.com/jun562"><img src="https://avatars.githubusercontent.com/u/37623843?v=4" width="64"></a> |

---

## 기술 스택
**Frontend**
- Next.js, TypeScript, Tailwind CSS, D3.js

**Backend**
- Spring Boot, Java, JPA
- Neo4j (질문-답변 트리 저장)
- MariaDB (회원/토픽 관리)

**Infra**
- AWS EC2, Docker, Nginx
- GitHub Actions (CI/CD)

---

## 주요 기능
- ChatGPT API를 통한 질문·답변 처리
- 대화 내용을 계층형 트리 데이터로 변환
- D3.js 기반 질문-답변 그래프 시각화
- 브레드크럼 탐색 및 노드 클릭 이동
- 질문 추가, 수정, 삭제
- 토픽별 대화 기록 관리

---

## 시스템 아키텍처
```mermaid
flowchart LR
  User -->|Web| Frontend[Next.js + D3.js]
  Frontend -->|REST API| Backend[Spring Boot]
  Backend -->|Graph Query| Neo4j[(Neo4j DB)]
  Backend -->|Relational Query| MariaDB[(MariaDB)]
  Backend -->|OpenAI API| ChatGPT[OpenAI GPT API]
