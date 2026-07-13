# Purpose-Fit Design

[한국어](README.md) | [English](README.en.md)

## 요약

기존 코드를 그대로 재사용하기 전에 이번 작업의 실제 목적과 제약에 맞는지 확인합니다. 익숙하거나 복사하기 쉬운 구현 때문에 잘못된 방향으로 시작하는 일을 줄이고, 무엇이 성공인지 코딩 전에 분명하게 합니다.

## 빠른 시작

**설치**

```bash
npx skills add perhapsspy/purpose-fit-design
```

혹은 `skills/purpose-fit-design` 폴더를 에이전트 스킬 디렉터리에 직접 복사합니다.

**바로 사용**

```text
$purpose-fit-design 기존 검색 화면을 복사하기 전에 이번 요구와 맞는지 확인해줘.

$purpose-fit-design 이 fallback을 유지하면 사용자가 기대한 동작을 깨뜨리는지 봐줘.

$purpose-fit-design 새 컴포넌트가 필요한지 기존 것을 그대로 써도 되는지 판단해줘.
```

## 이런 때 사용

- 기존 구현이 있어서 그대로 재사용하고 싶지만 목적이 다른지 의심될 때
- 이미 제외한 필드, 상태나 정책이 다른 이름으로 다시 들어올 위험이 있을 때
- “일단 복사하고 나중에 정리”가 실제 요구와 성공 조건을 흐릴 수 있을 때
- 기존 구현의 일부를 재사용해도 목적과 제약이 그대로 유지되는지 확인해야 할 때
- 새로 만들지 기존 컴포넌트를 재사용할지 목적을 기준으로 판단해야 할 때

## 지원

[![Buy Me A Coffee](https://cdn.buymeacoffee.com/buttons/v2/default-yellow.png)](https://www.buymeacoffee.com/perhapsspy)

## 라이선스

[MIT](LICENSE)
