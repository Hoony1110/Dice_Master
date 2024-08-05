# 주사위 게임 프로젝트

해당 프로젝트는 사용자가 주사위의 합을 맞추는 게임을 통해 보상을 얻는 Java 기반의 콘솔 애플리케이션입니다.
사용자 및 관리자 기능을 지원하며, 데이터베이스와의 연동을 통해 로그인, 회원가입, 게임 기록 관리 등을 구현하였습니다.

## 기능

### 사용자
- **로그인 및 회원가입**: 사용자가 로그인 및 회원가입을 할 수 있습니다.
- **회원 수정**: 사용자 정보(비밀번호, 이메일 등)를 수정할 수 있습니다.
- **로그아웃**: 사용자 세션을 종료합니다.
- **회원 탈퇴**: 사용자가 계정을 삭제할 수 있습니다.

### 관리자
- **로그인 및 회원가입**: 관리자가 로그인 및 회원가입을 할 수 있습니다.
- **회원 관리**: 사용자의 정보 및 보상 상태를 관리할 수 있습니다.

### 게임(사용자)
- **주사위 게임**: 3개의 주사위의 합을 맞추는 게임을 진행할 수 있습니다. 게임은 보상 체계가 있으며,
                   게임 결과에 따라 리워드를 획득하거나 차감합니다.
- **사용자 정보**: 사용자 자신의 정보 확인이 가능합니다.
- **게임 랭킹**: 게임을 진행한 전체 사용자 중 자신의 순위를 확인할 수 있습니다.

## 데이터베이스

### member 테이블
- `User_name`: 사용자 이름
- `User_id`: 사용자 ID (로그인 ID)
- `User_pw`: 사용자 비밀번호
- `User_email`: 사용자 이메일
- `Role`: 사용자 역할 (사용자, 관리자)
- `Reward`: 사용자 보유 코인

### gamehistory 테이블
- `User_id`: 사용자 ID
- `User_name`: 사용자 이름
- `Reward`: 게임 종료 시 획득 코인
- `Time_start`: 게임 시작 시간
- `Time_over`: 게임 종료 시간

## 게임 규칙
- **게임 시작**: 100 Reward 차감
- **1회차 성공**: 200 Reward 획득
- **2회차 성공**: 150 Reward 획득
- **3회차 성공**: 100 Reward 획득
- **게임 실패**: 보상 없음

## 프로젝트 실행 방법

1. **환경 설정**
   - Java Development Kit (JDK) 17 이상 설치
   - JDBC (Java Database Connectivity) 설치 및 설정

2. **데이터베이스 설정**
   - `member` 및 `gamehistory` 테이블을 생성합니다.
   - 데이터베이스 연결 설정을 `dao` 파일에 구성합니다.

3. **프로젝트 빌드 및 실행**
   - 프로젝트를 클론한 후, IDE에서 프로젝트를 열고 빌드합니다.
   - `indexMain.java` 파일을 실행하여 애플리케이션을 시작합니다.

4. **사용자 로그인**
   - 기본적으로 사용자 ID와 비밀번호를 사용하여 로그인합니다.

## 기술 스택

- **Java**: 애플리케이션의 주요 프로그래밍 언어
- **JDBC (Java Database Connectivity)**: Java와 MySQL 간의 연결을 위한 라이브러리
- **Git**: 소스 코드 버전 관리 시스템
