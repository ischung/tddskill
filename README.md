# TDD 스킬 (Claude Code Custom Skill)

TDD(테스트 주도 개발) 워크플로우를 단계별로 수행하는 Claude Code 커스텀 스킬입니다.

## 파일 구조

```
tddskill/
├── tdd.md              # Claude Code 스킬 정의 파일 (커맨드 프롬프트)
└── tdd-workflow-ko.md  # TDD 워크플로우 상세 가이드 (한국어)
```

## 설치 방법

> **사전 요구사항:** [Claude Code](https://claude.ai/code)가 설치되어 있어야 합니다.

### 방법 1: curl로 바로 설치 (권장)

**전역 설치** — 모든 프로젝트에서 `/tdd` 사용 가능:

```bash
mkdir -p ~/.claude/commands
curl -o ~/.claude/commands/tdd.md \
  https://raw.githubusercontent.com/ischung/tddskill/main/tdd.md
```

**프로젝트 전용 설치** — 현재 프로젝트에서만 사용:

```bash
mkdir -p .claude/commands
curl -o .claude/commands/tdd.md \
  https://raw.githubusercontent.com/ischung/tddskill/main/tdd.md
```

### 방법 2: 저장소 클론 후 복사

```bash
git clone https://github.com/ischung/tddskill.git
cd tddskill

# 전역 설치
mkdir -p ~/.claude/commands
cp tdd.md ~/.claude/commands/tdd.md

# 또는 프로젝트 전용 설치
mkdir -p .claude/commands
cp tdd.md .claude/commands/tdd.md
```

### 설치 확인

Claude Code를 열고 다음 명령어를 입력합니다:

```
/tdd
```

자동완성 목록에 `tdd`가 나타나면 설치 완료입니다.

## 사용 방법

```
/tdd [구현할 기능 설명]
```

**예시:**
```
/tdd 두 수를 더하는 계산기 함수
/tdd 사용자 로그인 유효성 검사
/tdd 장바구니에 상품 추가 기능
```

## TDD 사이클

```
🔴 RED     → 실패하는 테스트 먼저 작성
🟢 GREEN   → 최소한의 코드로 테스트 통과
🔵 REFACTOR → 동작 유지하며 코드 개선
🔁 반복
```

## 주요 기능

- **STEP 0:** 요구사항 분석 및 TODO 테스트 목록 자동 생성
- **STEP 1 (RED):** AAA 패턴(Arrange-Act-Assert)으로 실패 테스트 작성
- **STEP 2 (GREEN):** 최소 구현으로 테스트 통과
- **STEP 3 (REFACTOR):** 코드 스멜 제거 및 개선
- **STEP 4:** 다음 사이클 자동 진행

## 참고 문서

- [TDD 워크플로우 상세 가이드](tdd-workflow-ko.md)
