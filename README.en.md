# Purpose-Fit Design

[한국어](README.md) | [English](README.en.md)

## Summary

Before reusing existing code, `purpose-fit-design` checks whether it fits the actual purpose and constraints of this work. It reduces false starts caused by familiar or easy-to-copy implementations and makes success clear before coding begins.

## Quick Start

**Install**

```bash
npx skills add perhapsspy/purpose-fit-design
```

Or copy `skills/purpose-fit-design` directly into an agent skill directory.

**Use**

```text
Use $purpose-fit-design to check whether copying this search screen fits the current request.

Use $purpose-fit-design to check whether keeping this fallback would break the behavior users expect.

Use $purpose-fit-design to decide whether this needs a new component or can safely reuse the existing one.
```

## Use When

- Existing implementation is convenient to reuse, but may not fit the current purpose.
- A rejected field, status, or policy may return under another name.
- "Copy now, clean later" could blur the real requirement or success condition.
- Multiple layers are about to calculate the same rule independently.
- You need to decide whether to create something new or reuse an existing component based on purpose.

## Support

[![Buy Me A Coffee](https://cdn.buymeacoffee.com/buttons/v2/default-yellow.png)](https://www.buymeacoffee.com/perhapsspy)

## License

[MIT](LICENSE)
