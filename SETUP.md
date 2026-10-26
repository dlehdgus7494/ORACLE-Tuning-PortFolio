# 🛠️ Development & Database Environment Setup

본 문서는 Apple Silicon(M Series) MacOS 환경에서 Docker를 활용해 Oracle Database 19c 실습 환경 및 데이터 파이프라인 개발 환경을 구축한 과정을 기록한 가이드입니다.

---

## 1. 개발 환경 스펙 (Specification)

- **Hardware:** Mac (Apple Silicon M Series)
- **OS:** MacOS Taeho
- **Virtualization:** Docker Desktop
- **DBMS:** Oracle Free 23c/21c
- **Client Tools:** Beaver / Oracle SQL Developer, VS Code
- **Language/Runtime:** Python 3.10+, Bash Shell

```bash
# Docker: 애플리케이션을 컨테이너로 실행하고 관리
          Oracle 같은 데이터베이스를 컨테이너에서 실행
          이미지 다운로드, 컨테이너 생성, 실행, 삭제 등 


```

---

## 2. Docker 기반 오라클 19c 컨테이너 구축
```bash
# Oracle Free 23c/21c 설치
docker run -d --name oracle19c -p 1521:1521 -p 5500:5500 -e ORACLE_PWD=YourPassword123! gvenzl/oracle-free
