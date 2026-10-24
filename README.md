# idunworks Claude skills

Skills for [Claude Code](https://claude.com/claude-code), drawn from features built on [idunworks.com](https://idunworks.com). One skill per major feature, not per session. Each one is written up on the blog too.

| Skill | What it does | Runs |
|---|---|---|
| [session-to-blog](plugins/session-to-blog/skills/session-to-blog/SKILL.md) | Turns a finished piece of work into a redacted, first-person blog post draft | Only when you type `/session-to-blog` |

## Install

```
/plugin marketplace add idunworks/claude-skills
/plugin install session-to-blog@idunworks-skills
```

## Turn it off, or detach it

Every skill here is built so you can switch it off without touching your project.

| You want to… | Do this | Undo |
|---|---|---|
| Stop it for one project | Write "Blog drafts: off" in the project's `docs/blog/README.md` (or `CLAUDE.md`). The skill checks this first and stops. | Remove the line |
| Stop it everywhere, keep it installed | `claude plugin disable session-to-blog@idunworks-skills` | `claude plugin enable …` |
| Remove it | `claude plugin uninstall session-to-blog@idunworks-skills` | Install again |
| Drop this whole catalog | `/plugin marketplace remove idunworks-skills` | Add it again |

Nothing in your project depends on the skill: it reads your rules file but never writes to it unless you ask. Uninstalling leaves your drafts and rules exactly as they were.

## Safety rules every skill here follows

- **Never triggers itself** unless its page says so. You call it.
- **Never publishes, posts or deploys.** It prepares; you press the button.
- **Your project's rules win** over the skill's defaults.
- **Holds no credentials, hosts or project-specific names.**

## License

<!-- Owner to choose: MIT is the usual pick for skills. -->
