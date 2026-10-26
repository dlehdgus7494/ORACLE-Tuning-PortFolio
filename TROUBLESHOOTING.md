# 🛠️ Development & Database TroubleShooting

본 문서는 Apple Silicon(M Series) MacOS 환경에서 Docker를 활용해 Oracle Database 19c 실습 환경 및 데이터 파이프라인 개발 환경을 구축한 과정을 기록한 가이드입니다.

---

## 1. 개발 환경 설정

- **초기 목표:** 기업 실무 표준인 **Oracle Database 19c Enterprise Edition** 환경 구축
- **이슈 발생:**
  1. Apple Silicon(ARM64) 환경에서 기존 19c x86 기반 이미지 실행 시 번역 레이어(QEMU) 오버헤드로 인한 아키텍처 비호환 및 성능 저하 문제 발생
  2. Oracle Container Registry의 19c x86 이미지가 Apple Silicon Docker Desktop 환경에서 AR64 에물레이션 관련 Access Denied 및 바이너리 비호환 오류 유발
- **해결 및 대안 선택:**
  1. 성능 튜닝 및 AWR/ASH 분석 프로젝트 달성을 위해 ARM64 Native 아키텍처를 공식 지원하는 오라클 데이터베이스 이미지(gvenzl/oracle-free)로 환경 전환
  2. SQL 실행 계획, AWR/ASH 성능 분석, 인덱스 튜닝, 대용량 데이터 파이프라인 구축 등 주요 엔진 동작 및 성능 관련 기능은 Oracle 19c와 동일한 Core 커널 구조를 공유하므로
     포트폴리오 검증 목적에 완벽히 부합함을 확인 후 채택
```bash
# Oracle Free 23c/21c 설치
docker run -d --name oracle19c -p 1521:1521 -p 5500:5500 -e ORACLE_PWD=YourPassword123! gvenzl/oracle-free
```
---

```

---

## 2. Docker 기반 오라클 19c 컨테이너 구축
```bash
# Oracle Free 23c/21c 설치
docker run -d --name oracle19c -p 1521:1521 -p 5500:5500 -e ORACLE_PWD=YourPassword123! gvenzl/oracle-free
