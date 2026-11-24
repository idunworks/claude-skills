# idunworks Claude skills

Skills for [Claude Code](https://claude.com/claude-code), drawn from features built on [idunworks.com](https://idunworks.com). One skill per major feature, not per session. Each one is written up on the blog too.

| Skill | What it does | Runs |
|---|---|---|
| [session-to-blog](plugins/session-to-blog/skills/session-to-blog/SKILL.md) | Turns a finished piece of work into a redacted, first-person blog post draft | Only when you type `/session-to-blog` |
| [not-the-product](plugins/not-the-product/skills/not-the-product/SKILL.md) | Checks a community or social app feature so its members are never the product, and drafts plain promise text with a test behind each promise | By itself when you design or review community features (feeds, notifications, groups, digests, AI access), or when you ask for it |
| [not-generic](plugins/not-generic/skills/not-generic/SKILL.md) | Reviews a finished text or web page for generic, unsupported, repetitive or unconsidered work, and names a concrete change and an honest open question for each finding. It doesn't try to tell AI from human; it asks what only this project could have made | Only when you type `/not-generic` |

## Install

```
/plugin marketplace add idunworks/claude-skills
/plugin install session-to-blog@idunworks-skills
/plugin install not-the-product@idunworks-skills
/plugin install not-generic@idunworks-skills
```

## Turn it off, or detach it

Every skill here is built so you can switch it off without touching your project.

| You want to… | Do this | Undo |
|---|---|---|
| Stop session-to-blog for one project | Write "Blog drafts: off" in the project's `docs/blog/README.md` (or `CLAUDE.md`). The skill checks this first and stops. | Remove the line |
| Stop not-the-product for one project | Write `not-the-product: off` in the project's `CLAUDE.md`. The skill checks this first and stops. | Remove the line |
| Stop not-generic for one project | Write `not-generic: off` in the project's `CLAUDE.md`. The skill checks this first and stops. | Remove the line |
| Stop it everywhere, keep it installed | `claude plugin disable <skill>@idunworks-skills` | `claude plugin enable …` |
| Remove it | `claude plugin uninstall <skill>@idunworks-skills` | Install again |
| Drop this whole catalog | `/plugin marketplace remove idunworks-skills` | Add it again |

Nothing in your project depends on the skill: it reads your rules file but never writes to it unless you ask. Uninstalling leaves your drafts and rules exactly as they were.

## Safety rules every skill here follows

- **Never triggers itself** unless its page says so. You call it.
- **Never publishes, posts or deploys.** It prepares; you press the button.
- **Your project's rules win** over the skill's defaults.
- **Holds no credentials, hosts or project-specific names.**

## License

[MIT](LICENSE)
