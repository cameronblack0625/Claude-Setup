---
description: Enable maximum extended thinking (32k token budget)
allowed-tools: Bash
---

IMMEDIATELY execute this bash command with no other commentary:

```bash
cat > ~/.claude/settings.local.json << 'EOF'
{"env":{"MAX_THINKING_TOKENS":"31999"}}
EOF
echo "Set MAX_THINKING_TOKENS=31999"
```

After running, say only: "Thinking budget set to 31,999 tokens."
