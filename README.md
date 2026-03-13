# prompt-library 📚

Curated Claude prompt templates for Web3 developers. Copy, paste, adapt.

All prompts tested with Claude claude-opus-4-5 and claude-sonnet-4-5.

## Categories

| File | Prompts | Use Case |
|---|---|---|
| [security-audit.md](prompts/security-audit.md) | 6 | Security review, vulnerability hunting |
| [gas-optimization.md](prompts/gas-optimization.md) | 5 | Reduce gas costs |
| [test-generation.md](prompts/test-generation.md) | 5 | Foundry test suites, fuzz, fork |
| [architecture.md](prompts/architecture.md) | 5 | Design review, upgrade strategy |
| [docs-natspec.md](prompts/docs-natspec.md) | 4 | NatSpec, README, plain English |
| [code-review.md](prompts/code-review.md) | 5 | Best practices, refactoring |

**30 prompts total.**

## How to Use

1. Open the relevant category file
2. Find the prompt that fits your task
3. Copy the prompt block
4. Replace `[PLACEHOLDERS]` with your content
5. Paste into Claude

## Tips

- Use claude-opus for security audits (more thorough)
- Use claude-haiku for quick reviews (faster, cheaper)
- Chain prompts: audit first, then optimize, then generate tests
- Add your contract ABI when asking about interactions

## Contributing

PRs welcome. Each prompt should include: name, when-to-use, the prompt template with `[PLACEHOLDERS]`, and tips.

## License

MIT
