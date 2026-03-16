# TDD 스킬 (Claude Code Custom Skill)

TDD(테스트 주도 개발) 워크플로우를 단계별로 수행하는 Claude Code 커스텀 스킬입니다.

## 파일 구조

```
tddskill/
├── tdd.md              # Claude Code 스킬 정의 파일 (커맨드 프롬프트)
└── tdd-workflow-ko.md  # TDD 워크플로우 상세 가이드 (한국어)
```

## 설치 방법

`tdd.md` 파일을 Claude Code 커스텀 커맨드 디렉토리에 복사합니다:

```bash
# 프로젝트 전용 (현재 프로젝트에서만 사용)
cp tdd.md .claude/commands/tdd.md

# 전역 설치 (모든 프로젝트에서 사용)
cp tdd.md ~/.claude/commands/tdd.md
```

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
