# Claude Skills

Skills and commands for scientific Python development.

## Installation

```bash
git clone https://github.com/yallup/claude-skills.git
```

Then in Claude Code:
```
/plugin marketplace add ./claude-skills
/plugin install claude-skills@yallup
```

### Enable Auto-Activation

```bash
python3 -c "
import json; from pathlib import Path
p = Path.home() / '.claude' / 'settings.json'
s = json.loads(p.read_text()) if p.exists() else {}
s.setdefault('permissions', {}).setdefault('allow', []).append('Skill(*)') if 'Skill(*)' not in s.get('permissions', {}).get('allow', []) else None
p.write_text(json.dumps(s, indent=2))
"
```

## Skills

| Skill | Description |
|-------|-------------|
| `reviewing-code` | Senior engineer task execution |
| `using-jax` | JAX patterns: JIT, vmap, RNG |
| `running-python` | Runs Python with uv |
| `plotting` | Publication-quality plots with tueplots |

Skills auto-activate based on context.

## Commands

| Command | Description |
|---------|-------------|
| `/code-review` | Invoke reviewing-code with Python skill reminders |

## Updating

```bash
cd claude-skills && git pull
```

## License

MIT
