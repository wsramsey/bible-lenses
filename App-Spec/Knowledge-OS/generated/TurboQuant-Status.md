# TurboQuant Status

## Result
TurboQuant is installed and importable in an isolated Python virtual environment.

## Location
- venv: `/Users/wyattramsey/.openclaw/workspace/.venvs/turboquant`
- wrapper: `/Users/wyattramsey/.openclaw/workspace/bin/turboquant`

## Verification
- Python import succeeded
- server CLI responds to `--help`

## Current invocation
```bash
/Users/wyattramsey/.openclaw/workspace/bin/turboquant --help
```

## Notes
This package provides a server entrypoint (`python -m turboquant.server`) rather than a default package CLI.

## Next likely use
Evaluate whether TurboQuant meaningfully helps local inference on the Mac Mini versus standard Ollama quantized models before making it part of the default stack.
