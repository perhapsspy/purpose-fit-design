# Skill: Purpose-Fit Design (한국어 페어)

> 영문 기본 문서: `SKILL.md`

## 목적

설계나 구현 계획을 시작하기 전에 그 방향이 사용자/도메인 목적에 맞는지 확인한다. 기존 구현, 복사하기 쉬운 동작, fallback/default 로직은 기본 설계 권위가 아니라 평가해야 할 증거로 본다.

끝낼 때는 좁은 방향으로 진행하거나, 막는 사실 하나를 질문/조사하거나, 전문 workflow로 넘긴다.

명확한 전문 trigger가 이미 있으면 이 스킬 안에서 source ownership을 증명하거나 semantic owner를 배정하거나 코드 구조를 잡지 않는다.

## 적합성 확인

결정에 영향을 주는 내용만 답한다. 작은 작업에서는 짧은 한 문단으로 충분하다.

1. **목적과 성공 기준:** 사용자/도메인 결과와 가장 작은 관찰 가능한 성공 조건을 말한다.
2. **제약:** 명시적인 사용자 정정, rejected concept, "X를 추가하지 말라" 같은 규칙을 고정한다.
3. **증거:** 현재 구현이나 precedent를 `source owner`, `derived caller`, `legacy/compatibility`, `evidence candidate`, `unknown` 중 하나로 분류한다.
4. **적합성 위험:** reuse, fallback, schema, adapter, shortcut, "copy now, clean later" 중 목적에서 벗어나게 만들 수 있는 경로를 말한다.
5. **방향 또는 handoff:** 좁은 purpose-fit 방향을 말하거나 하나의 전문 workflow를 지정한다.
6. **검증:** 선택한 방향을 반증할 수 있는 가장 작은 확인을 말한다.

목적, 제약, 증거 상태, 성공 기준 중 설계에 영향을 주는 것이 unknown이면 하나를 조사하거나 집중 질문을 한다. 현재 구현 형태로 빈칸을 채우지 않는다.

명시적인 사용자 정정은 hard constraint로 다룬다. 사용자가 다시 검토하자고 하지 않는 한 rejected field, status, UI pattern, schema, timeout, policy, fallback을 다른 계층 이름으로 다시 들여오지 않는다.

lower-layer fallback은 command meaning, visible state, retry, audit, persistence, test, policy, 다른 caller에 영향을 줄 수 있으면 설계 결정으로 본다. rejected constraint를 되살리거나 의미에 영향을 주는 동작의 owner가 없으면 멈추고 semantic-boundary workflow로 넘긴다.

route, UI, adapter, realtime, presentation 코드에서 domain/status identity를 fallback chain으로 계산한다면 단순 scope-control 문제로 보지 않는다. 현재 owner가 명명되어 있지 않으면 편집 계획 전에 source-owner 또는 semantic-boundary discovery로 넘긴다.

transport watchdog이나 infrastructure guard는 transport/infra layer가 소유하고, liveness/resource protection에 한정되고, domain field/status/policy/default를 만들지 않고, accepted user-visible state를 바꾸지 않고, caller에게 business meaning이 될 수 없을 때 semantic-boundary work 없이 진행할 수 있다.

긴급함은 적합성 증거가 아니다. 사용자가 shortcut을 요청하면 지금 purpose, constraints, owner boundaries를 보존하는 가장 작은 slice를 제안한다. "copy now, clean later"를 설계 전략으로 제시하지 않는다. 임시 구현도 코드 시작 전에 명시적 adapter, wrapper, rollback boundary가 필요하다.

## 전문 workflow 라우팅

전문 workflow trigger가 이미 명확하면 이 스킬을 건너뛰고 그 workflow를 직접 사용한다. 그렇지 않으면 이 확인 뒤에:

- source of truth가 증명되지 않았으면 source-owner discovery를 사용한다.
- 하나의 의미가 계층 사이에서 drift될 수 있으면 semantic-boundary design을 사용한다.
- option, field, abstraction, follow-up이 넓어질 수 있으면 scope-justification을 사용한다.
- owner/design direction이 정해졌고 다음 문제가 code shape이면 structure-focused planning을 사용한다.
- user intent, presentation, async work, freshness가 섞일 수 있으면 interactive-state flow analysis를 사용한다.

## 위험 신호

- 현재 목적 적합성을 확인하지 않고 "이 컴포넌트가 이미 있으니 재사용"하는 경우.
- 사용자 목표나 owner evidence 없이 "보안/일관성상 schema/catalog/timeout이 필요"하다고 말하는 경우.
- rejected field, status, UI pattern, schema, timeout, policy, fallback을 lower-level implementation detail로 다시 들여오는 경우.
- 다른 도메인의 state, layout, policy, lifecycle을 소유한 surface를 "copy now, clean later"로 받아들이는 경우.
- UI, route, adapter, realtime 코드가 `x || y || z` fallback chain으로 domain meaning을 결정하는 경우.
- caller-boundary behavior를 보호하지 않고 helper 내부 테스트만 증명하는 경우.
- 설계 설명 대부분이 현재 구현이 괜찮은 이유를 설명하는 경우.
- 사용자가 design, ownership, purpose, fit을 다시 보자고 했는데 곧바로 edit로 이동하는 경우.

## 최종 확인

구현이나 최종 추천 전에 확인한다:

- 목적이 단지 "현재 구현을 작동하게 만들기"가 아니다.
- 선택한 방향이 사용자/도메인 목적과 관찰 가능한 성공 조건에 맞다.
- 명시적인 사용자 정정이나 rejected concept을 다시 들여오지 않았다.
- 긴급함이 constraints, owner boundaries, rollback boundary, verification을 덮지 않았다.
- 기존 코드는 convenience가 아니라 evidence status로 분류했다.
- semantic decision에는 하나의 owner가 있거나 unknown이 명명되어 있다.
- 절차 무게가 작업 크기에 맞다.
