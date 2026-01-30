---
description: Enable basic extended thinking (4k token budget)
allowed-tools: Bash
---

IMMEDIATELY execute this bash command with no other commentary:

```bash
cat > ~/.claude/settings.local.json << 'EOF'
{"env":{"MAX_THINKING_TOKENS":"4000"}}
EOF
echo "Set MAX_THINKING_TOKENS=4000"
```

After running, say only: "Thinking budget set to 4,000 tokens."
