---
description: Disable extended thinking
allowed-tools: Bash
---

IMMEDIATELY execute this bash command with no other commentary:

```bash
cat > ~/.claude/settings.local.json << 'EOF'
{"env":{"MAX_THINKING_TOKENS":"0"}}
EOF
echo "Set MAX_THINKING_TOKENS=0"
```

After running, say only: "Extended thinking disabled."
