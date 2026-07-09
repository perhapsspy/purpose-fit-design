# Purpose-Fit Design

[한국어](README.md) | [English](README.en.md)

## 요약

`purpose-fit-design`는 에이전트가 설계나 구현 계획을 시작하기 전에 방향이 사용자/도메인 목적, 명시 제약, 현재 증거, 검증 가능한 성공 조건에 맞는지 확인하게 해주는 스킬입니다.

기존 구현, 복사하기 쉬운 코드, fallback/default 로직을 설계 권위로 바로 받아들이지 않고 증거로 분류합니다. 목적에 맞지 않는 재사용과 임시 복사를 막되, 실제 source owner인 기존 컴포넌트나 계약은 그대로 따르게 합니다.

## 빠른 시작

**설치**

```bash
npx skills add perhapsspy/purpose-fit-design
```

혹은 `skills/purpose-fit-design` 폴더를 에이전트 스킬 디렉터리에 직접 복사합니다.

**바로 사용**

```text
Use $purpose-fit-design to check whether this implementation plan fits the user purpose before coding.

$purpose-fit-design 이 기존 fallback을 그대로 가져가도 되는 설계인지 먼저 봐줘.

$purpose-fit-design 이 컴포넌트를 새로 만들지, 기존 source-owned 컴포넌트를 써야 할지 판단해줘.
```

## 이런 때 사용

- 기존 구현이 있어서 그대로 재사용하고 싶지만 목적이 다른지 의심될 때
- rejected field, status, UI pattern, schema, timeout, policy, fallback이 다른 계층 이름으로 되돌아올 위험이 있을 때
- “일단 복사하고 나중에 정리”가 도메인 의미, 상태, 정책, 검증을 흐릴 수 있을 때
- route, UI, adapter, realtime, presentation 코드가 같은 의미를 fallback chain으로 계산하려 할 때
- 기존 컴포넌트나 계약을 무조건 거부하지 않고, 실제 source owner인 경우에는 보존해야 할 때

## 지원

[![Buy Me A Coffee](https://cdn.buymeacoffee.com/buttons/v2/default-yellow.png)](https://www.buymeacoffee.com/perhapsspy)

## 라이선스

[MIT](LICENSE)
