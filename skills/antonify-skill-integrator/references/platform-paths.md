# Platform Skill Paths

Use these paths when adapting Antonify into agent skill systems.

## Claude Code

- Project: `.claude/skills`
- Personal: `~/.claude/skills`
- Typical invocation: `/skill-name`

## Codex

- Repo: `.agents/skills`
- Personal: `~/.agents/skills`
- Typical invocation: `$skill-name`
- Use a Codex plugin when distributing a polished skill bundle beyond one repo or user.

## OpenClaw

- Workspace: `skills/`
- Global: `~/.openclaw/skills`
- Useful checks:
  - `openclaw skills list`
  - `openclaw skills info skill-name`
  - `openclaw skills check`

## Hermes Agent

- Local: `~/.hermes/skills`
- Additional directories: `skills.external_dirs` in `~/.hermes/config.yaml`
- Typical invocation: `/skill-name`
- Session preload: `hermes chat -s skill-name`
