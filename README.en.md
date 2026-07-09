# Purpose-Fit Design

[한국어](README.md) | [English](README.en.md)

## Summary

`purpose-fit-design` helps an agent check whether a design or implementation-planning direction fits the user/domain purpose, explicit constraints, current evidence, and verifiable success conditions before coding starts.

It treats existing implementation, copy-friendly code, and fallback/default logic as evidence to classify rather than as default design authority. It blocks misleading reuse and temporary copy pressure, while still preserving existing components or contracts when they are the real source owner.

## Quick Start

**Install**

```bash
npx skills add perhapsspy/purpose-fit-design
```

Or copy `skills/purpose-fit-design` directly into an agent skill directory.

**Use**

```text
Use $purpose-fit-design to check whether this implementation plan fits the user purpose before coding.

Use $purpose-fit-design to decide whether copying this fallback preserves the domain purpose.

Use $purpose-fit-design to judge whether a new local component is justified or the source-owned component should be composed.
```

## Use When

- Existing implementation is convenient to reuse, but may not fit the current purpose.
- A rejected field, status, UI pattern, schema, timeout, policy, or fallback may return under another layer name.
- "Copy now, clean later" could blur domain meaning, state, policy, or verification.
- Route, UI, adapter, realtime, or presentation code may compute the same meaning through a fallback chain.
- You need to avoid both misleading reuse and over-rejecting a valid source-owned component or contract.

## Support

[![Buy Me A Coffee](https://cdn.buymeacoffee.com/buttons/v2/default-yellow.png)](https://www.buymeacoffee.com/perhapsspy)

## License

[MIT](LICENSE)
