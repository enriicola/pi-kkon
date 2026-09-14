while :; do cat PROMPT.md | claude; done

## if external

```bash
PATH = "~/.config/pi/safe-bin:" + PATH
MAX_LOOPS = 5
LOOP = 0

git checkout -b ralph-working-branch

# Loop
while true; do
    LOOP++
    
    if [ LOOP > MAX_LOOPS ]; then
        git reset --hard HEAD
        git clean -fd
        exit 1
    fi

    run_tests()
    if [ tests_passed ]; then
        git add .
        git commit -m "checkpoint"
        exit 0
    fi

    # Update state and prompt
    echo "Test failed: $TEST_LOG" > agent_state.md
    
    cat agent_state.md | pi --model openrouter/auto
done
```

##  blacklisting commands
...such as 
- rm -f
- or rm in general
- git push
- to be added ...

before executing it...install 1 of these extensions:
1. https://pi.dev/packages/@gotgenes/pi-permission-system
2. https://github.com/aliou/pi-guardrails
3. https://github.com/MasuRii/pi-permission-system
4. https://pi.dev/packages/@pi-lab/permissions
  
## other good extensions to install

- https://pi.dev/packages/pi-hermes-memory
- pi-web-access
- pi-file-widget