# 스킬 방향

## 목적

- 설계와 구현 계획이 기존 구현 편의가 아니라 사용자/도메인 목적, 명시 제약, 현재 증거, 검증 가능한 성공 조건을 따르게 한다.

## 유지할 것

- 기존 구현은 기본 권위가 아니라 분류해야 할 증거로 둔다.
- rejected concept이 다른 계층 이름으로 되돌아오는 경우를 강하게 막는다.
- misleading reuse와 copy-now-clean-later 압력을 막되, 실제 source owner인 기존 컴포넌트나 계약은 보존한다.
- 작은 작업에서는 한 문단 판단으로 충분하게 유지한다.
- 설계 방향이 정해진 뒤에는 구조화, 구현, 검증 흐름으로 자연스럽게 넘긴다.

## 피할 것

- 스킬을 전면 프로세스 프레임워크로 키우는 방향.
- 모든 재사용을 의심하거나 모든 기존 구현을 거부하는 방향.
- owner discovery, semantic boundary design, implementation planning을 이 스킬 안에서 전부 수행하는 방향.
- 예시와 실험 기록을 런타임 `SKILL.md`에 계속 추가하는 방향.

## 수정 기준

- 실제 작업에서 miss, over-trigger, late handoff가 반복될 때만 shipped skill을 수정한다.
- 검증되지 않은 안정성 주장이나 production-proven 표현은 넣지 않는다.
- 한국어 문서는 영문 base skill의 의미를 보존하되 자연스럽고 직접적으로 쓴다.
- 저장소 운영 문서는 스킬 사용 계약을 대신하지 않는다.
