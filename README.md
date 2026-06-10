# AI 기획 스킬 모음 (Claude Code Skills)

Claude Code에서 `/명령어` 형태로 실행하는 기획자용 AI 스킬 모음입니다.  
기획자의 사고 단계(이해 → 작동원리 → 진단 → 설계 → 메시지)를 각각 구조화합니다.

---

## 기획 프레임워크 스킬 (5레이어)

| 레이어 | 스킬 | 핵심 질문 | 파일 |
|--------|------|---------|------|
| 01 이해 | `/concept-map` | 이게 뭐야? | [concept-map.md](./concept-map.md) |
| 02 작동원리 | `/mental-model` | 왜 이렇게 움직여? | [mental-model.md](./mental-model.md) |
| 03 진단 | `/business-diagnosis` | 어디가 문제야? | [business-diagnosis.md](./business-diagnosis.md) |
| 04 설계 | `/strategy-canvas` | 뭘 해야 해? | [strategy-canvas.md](./strategy-canvas.md) |
| 05 메시지 | `/brand-house` | 한 문장으로? | [brand-house.md](./brand-house.md) |

## 분석·리포트 스킬

| 스킬 | 설명 | 파일 |
|------|------|------|
| `/problem-canvas` | BMC × 맥킨지 7단계 문제 해결 | [problem-canvas.md](./problem-canvas.md) |

---

## 설치 방법

### 스킬 하나씩 설치

```bash
# 01 이해 — concept-map
mkdir -p ~/.claude/skills/concept-map && curl -o ~/.claude/skills/concept-map/SKILL.md https://raw.githubusercontent.com/juree85-netizen/my-prompts/main/concept-map.md

# 02 작동원리 — mental-model
mkdir -p ~/.claude/skills/mental-model && curl -o ~/.claude/skills/mental-model/SKILL.md https://raw.githubusercontent.com/juree85-netizen/my-prompts/main/mental-model.md

# 03 진단 — business-diagnosis
mkdir -p ~/.claude/skills/business-diagnosis && curl -o ~/.claude/skills/business-diagnosis/SKILL.md https://raw.githubusercontent.com/juree85-netizen/my-prompts/main/business-diagnosis.md

# 04 설계 — strategy-canvas
mkdir -p ~/.claude/skills/strategy-canvas && curl -o ~/.claude/skills/strategy-canvas/SKILL.md https://raw.githubusercontent.com/juree85-netizen/my-prompts/main/strategy-canvas.md

# 05 메시지 — brand-house
mkdir -p ~/.claude/skills/brand-house && curl -o ~/.claude/skills/brand-house/SKILL.md https://raw.githubusercontent.com/juree85-netizen/my-prompts/main/brand-house.md
```

### 전체 한 번에 설치

```bash
git clone https://github.com/juree85-netizen/my-prompts.git /tmp/my-prompts && \
for skill in concept-map mental-model business-diagnosis strategy-canvas brand-house problem-canvas; do
  mkdir -p ~/.claude/skills/$skill
  cp /tmp/my-prompts/$skill.md ~/.claude/skills/$skill/SKILL.md
done
```

---

## 사용 방법

Claude Code 터미널에서 슬래시 명령어로 호출합니다.

```
/concept-map Salesforce
/mental-model Coupa
/business-diagnosis 우리 팀 신규 고객 유입이 줄고 있어
/strategy-canvas Medallia는 이제 어떻게 해야 해?
/brand-house 이 서비스를 한 문장으로 정리해줘
```

슬래시 명령어 없이 자연어로도 트리거됩니다.  
예: "왜 성장했지", "어디가 문제야", "전략적 선택지 정리해줘", "한 문장으로 정리해줘"

---

## 상세 문서

각 스킬의 출력 구조와 사용 예시는 각 `.md` 파일 상단의 `description` 주석과 본문에서 확인할 수 있습니다.
