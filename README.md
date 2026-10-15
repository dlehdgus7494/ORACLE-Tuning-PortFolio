## ORACLE-Tuning-Portfolio
# 🗄️Oracle 19c Performance Tuning & Analysis Portfolio

>> **Oracle Database 성능 분석 및 대용량 데이터 튜닝 실습 및 스크립트 저장소입니다.**
>> 본 저장소는 오라클 아키텍처에 대한 이해를 바탕으로 비효율적 쿼리 분석, 인덱스 재설계,
   대기 이벤트(Wait Event) 분석 및 자동화 스크립트 작성 과정을 담고 있습니다.

---

## 📌 개요 ( Overview )

* **진행 기간:** 2026.10.15 ~ 2026.10
* **목표:**
  * 500만 건 이상 대용량 더미 데이터 기반 쿼리 성능 최적화 (응답 시간 90% 이상 단축)
  * AWR / ASH 리포트 분석을 통한 DB 병목 구간 원인 규명
  * Shell Script를 활용한 DB 주요 상태 모니터링 자동화
* **Notion PortFolio** [https://app.notion.com/p/439f0b4603cc83a199b101f79a9889d6?v=b15f0b4603cc83ce954408ec6518116a&source=copy_link]

---

## 💻 실습 및 분석 환경 ( Environment )

* **OS:** MacOS (Apple Silicon M Series)
* **Virtualization / Container:** Docker Desktop & Colima
* **DBMS:** Oracle Database 19c Enterprise / Express Edition
* **Client Tool:** Oracle SQL Developer, Beaver, VS Code
* **Language / Shell:** Oracle SQL, PL/SQL, Bash Shell

---

## 📁 저장소 구조 ( Directory Structure )

```text
.
├── README.md                     # 프로젝트 안내 및 요약 문서
├── 01_dummy_data/
│   └── create_dummy_data.sql     # 500만 건 대용량 더미 데이터 생성 스크립트
├── 02_index_tuning/
│   ├── 01_before_tuning.sql      # 튜닝 전 쿼리 및 실행계획
│   ├── 02_create_index.sql       # 인덱스 설계 및 생성 DDL
│   └── 03_after_tuning.sql       # 튜닝 후 쿼리 및 실행계획
├── 03_awr_ash_analysis/
│   └── wait_event_analysis.md    # 대기 이벤트 분석 보고서
└── 04_monitoring_script/
    └── db_health_check.sh        # DB 상태 모니터링 셸 스크립트
```


