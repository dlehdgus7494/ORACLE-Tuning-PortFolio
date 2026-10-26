# 🛠️ Development & Database Environment Setup

본 문서는 Apple Silicon(M Series) MacOS 환경에서 Docker를 활용해 Oracle Database 19c 실습 환경 및 데이터 파이프라인 개발 환경을 구축한 과정을 기록한 가이드입니다.

---

## 1. 개발 환경 스펙 (Specification)

- **Hardware:** Mac (Apple Silicon M Series)
- **OS:** MacOS Taeho
- **Virtualization:** Docker Desktop (Colima)
- **DBMS:** Oracle Database 19c (Enterprise Edition)
- **Client Tools:** Beaver / Oracle SQL Developer, VS Code
- **Language/Runtime:** Python 3.10+, Bash Shell

---

## 2. Docker 기반 오라클 19c 컨테이너 구축

### ① Colima 리소스 설정 및 가상화 구동 
> Apple Silicon M Series 환경에서 x86 기반 오라클 이미지를 안정적으로 구동하기 위해 충분한 CPU와 메모리 할당

```bash
# Colima 설치 (Homebrew 기준)
brew install colima docker

# qemu 설치 (하드웨어 에뮬레이터 프로그램)
brew install emu

# x86_64 에뮬레이션 모드로 Colima 실행 (최소 RAM 6GB 이상 권장)
Colima start --arch x86_64 --cpu 2 --memory 4 --disk 40

