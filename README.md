# Purpose-Fit Design

[한국어](README.md) | [English](README.en.md)

## 요약

기존 구조나 첫 해법이 방향을 너무 일찍 닫기 전에 이번 작업의 목적, 제약과 증거에서 설계 공간을 다시 엽니다. 익숙하거나 복사하기 쉬운 구현을 기본형으로 삼지 않고, 잠정 방향이나 가장 작은 확인을 코딩 전에 찾습니다.

## 빠른 시작

**설치**

```bash
npx skills add perhapsspy/purpose-fit-design
```

혹은 `skills/purpose-fit-design` 폴더를 에이전트 스킬 디렉터리에 직접 복사합니다.

**바로 사용**

```text
$purpose-fit-design 기존 검색 화면을 복사하기 전에 이번 목적에서 방향을 다시 열어줘.

$purpose-fit-design 이 fallback을 유지하면 사용자가 기대한 동작을 깨뜨리는지 봐줘.

$purpose-fit-design 새 컴포넌트가 필요한지 기존 것을 그대로 써도 되는지 판단해줘.
```

## 이런 때 사용

- 기존 구조나 첫 해법이 초기 방향을 미리 결정할 위험이 있을 때
- 중요한 선택에서 신뢰할 만한 대조안이나 가장 작은 확인이 필요할 때
- 이미 제외한 필드, 상태나 정책이 다른 이름으로 다시 들어올 위험이 있을 때
- “일단 복사하고 나중에 정리”가 실제 요구와 성공 조건을 흐릴 수 있을 때
- 기존 구현의 일부를 재사용해도 목적과 제약이 그대로 유지되는지 확인해야 할 때
- 새로 만들지 기존 컴포넌트를 재사용할지 목적을 기준으로 판단해야 할 때

## 지원

[![Buy Me A Coffee](https://cdn.buymeacoffee.com/buttons/v2/default-yellow.png)](https://www.buymeacoffee.com/perhapsspy)

## 라이선스

[MIT](LICENSE)
