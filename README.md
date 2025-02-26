# 취업봇다리

취업봇다리는 AI와 최신 채용 정보를 활용해 구직자에게 맞춤형 뉴스를 제공하고, 기업 정보와 채용 공고를 분석하여 취업 준비를 돕는 웹 애플리케이션입니다. 이 프로젝트는 프론트엔드(React, Vite)와 백엔드(Spring Boot, Spring Cloud 등)를 포함하며, Docker Compose와 GitHub Actions를 통해 Docker Hub에 배포된 컨테이너들을 자동으로 실행합니다.

---

## 주요 기능

- **회원 관리**  
  - 회원가입, 로그인, JWT 기반 인증
- **맞춤형 정보 제공**  
  - 최신 뉴스, 기업 정보, 채용 공고 제공
- **관심 기업 관리**  
  - 사용자가 관심 있는 기업 등록, 조회, 삭제
- **파일 업로드**  
  - 프로필 이미지 및 기타 파일 업로드 기능
- **보안 강화**  
  - Spring Security와 JWT 인증, AOP를 통한 로깅

---

## 기술 스택

- **프론트엔드:** React, Vite, Bootstrap, Axios
- **백엔드:** Spring Boot, Spring Cloud (Config, Eureka, Gateway), Spring Data JPA, Spring Security, AOP
- **데이터베이스:** MySQL
- **배포 및 인프라:** Docker, Docker Compose, GitHub Actions, Docker Hub

---

## 시스템 구성도

![image](https://github.com/user-attachments/assets/b34922d8-6aad-4ff4-8f40-3a6109dce9c0)

*구성도는 Config Server, Eureka Server, Gateway, 백엔드 서비스(취업봇다리, 취업봇다리-user), 프론트엔드 및 MySQL이 포함된 전체 아키텍처를 나타냅니다.*

---

## 실행 방법

모든 환경 변수는 백엔드 레포지토리의 GitHub Secrets를 통해 관리되므로, 별도의 환경 파일 수정 없이 아래 명령어 한 줄로 전체 서비스를 실행할 수 있습니다.

```bash
docker compose up -d
```

이 명령어를 실행하면 GitHub Actions가 Docker Hub에 배포된 최신 이미지를 사용하여 컨테이너들을 자동으로 실행합니다.

---

## 프로젝트 구조

```
Backend/                # 백엔드 소스 (Spring Boot, Spring Cloud 등)
Frontend/               # 프론트엔드 소스 (React, Vite 등)
```

---

## 추가 정보

- **컨테이너 상태 확인:**  
  ```bash
  docker compose ps
  ```
- **컨테이너 로그 확인:**  
  ```bash
  docker compose logs -f
  ```
- **컨테이너 중지:**  
  ```bash
  docker compose down
  ```

---

## 참고 사항

- **배포 자동화:**  
  GitHub Actions가 백엔드 및 프론트엔드 레포지토리의 변경 사항을 감지하여 Docker Hub에 이미지를 자동으로 빌드하고 배포합니다.
- **환경 변수 관리:**  
  모든 필수 환경 변수는 GitHub Secrets로 관리되며, docker-compose 실행 시 자동으로 주입됩니다.
- **접근 경로:**  
  클라이언트의 요청은 Gateway 서버를 통해 라우팅되며, Gateway 서버의 CORS 설정으로 프론트엔드(예: `http://localhost:5173`)에서의 요청을 허용합니다.

---

프로젝트 "취업봇다리"를 사용해 주셔서 감사합니다!

---
