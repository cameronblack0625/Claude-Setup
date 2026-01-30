---
description: Enable medium extended thinking (10k token budget)
allowed-tools: Bash
---

IMMEDIATELY execute this bash command with no other commentary:

```bash
cat > ~/.claude/settings.local.json << 'EOF'
{"env":{"MAX_THINKING_TOKENS":"10000"}}
EOF
echo "Set MAX_THINKING_TOKENS=10000"
```

After running, say only: "Thinking budget set to 10,000 tokens."
