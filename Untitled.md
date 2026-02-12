OpenClaw has recently added CLI backend integration that allows it to use Claude Code CLI (and similar command-line tools like Codex CLI) as fallback runtimes or standalone models. This integration was documented in early February 2026 and provides a text-only safety net when API providers are unavailable.[1]

## How CLI Integration Works

OpenClaw can now invoke local AI CLIs directly as an alternative to API-based models. The system builds the same OpenClaw system prompt with workspace context, executes the CLI with a session ID for conversation continuity, parses the output (JSON or plain text), and persists session IDs so follow-up messages maintain context.[1]

## Built-in Claude Code CLI Support

Claude Code CLI ships with zero-configuration defaults in OpenClaw. You can use it immediately without any setup:[2][1]

```
openclaw agent --message "hi" --model claude-cli/opus-4.6
```

The built-in configuration includes flags for JSON output format, session management via `--session-id`, system prompt injection through `--append-system-prompt`, and conversation resumption using `--resume`.[1]

## Fallback Configuration

CLI backends can serve as automatic fallbacks when primary API models fail due to rate limits, authentication issues, or timeouts. You configure this in your agent settings by adding CLI models to the fallbacks array:[1]

```json
"model": {
  "primary": "anthropic/claude-opus-4-6",
  "fallbacks": ["claude-cli/opus-4.6", "claude-cli/opus-4.5"]
}
```

If the primary Anthropic API becomes unavailable, OpenClaw automatically switches to the local Claude Code CLI while maintaining conversation flow.[1]

## Session Management

The integration supports persistent sessions so multi-turn conversations work correctly. OpenClaw tracks session IDs per backend and can operate in three modes: `always` (creates new UUID if none exists), `existing` (only uses stored session IDs), or `none` (stateless). Claude Code CLI uses "always" mode by default, ensuring every conversation gets tracked.[1]

## Limitations

CLI backends run in a simplified mode compared to full API integration. OpenClaw's native tools (filesystem, browser, shell) are disabled when using CLI backends, though the underlying CLI may still execute its own agent capabilities. There's no streaming support—output is collected and returned after the CLI completes. For Codex CLI specifically, session resumption falls back to plain text output instead of structured JSON.[1]

## Codex CLI Support

Beyond Claude Code, OpenClaw also includes built-in support for Codex CLI with similar zero-config usage. Codex uses JSONL streaming output and includes sandbox controls for read-only file access, making it suitable for code execution scenarios.[2][1]

Kilder
[1] The Rise of OpenClaw https://www.security.com/expert-perspectives/rise-openclaw
[2] CLI Backends - OpenClaw https://docs.openclaw.ai/gateway/cli-backends
[3] Integration with OpenClaw https://openrouter.ai/docs/guides/guides/openclaw-integration
[4] OpenClaw — Personal AI Assistant https://openclaw.ai
[5] Full OpenClaw Setup Tutorial: Step-by-Step Walkthrough ... https://www.youtube.com/watch?v=fcZMmP5dsl4
[6] I built a way to setup openclaw with claude code in under a ... https://www.reddit.com/r/ClaudeCode/comments/1qtq7zv/i_built_a_way_to_setup_openclaw_with_claude_code/
[7] Claude + OpenClaw: Complete Setup Guide for Production (2026) https://clawctl.com/blog/claude-openclaw-setup-guide
[8] How to turn your Claude into a agent for OpenClaw? https://www.reddit.com/r/claudexplorers/comments/1qt4y8a/how_to_turn_your_claude_into_a_agent_for_openclaw/
[9] What is OpenClaw? Your Open-Source AI Assistant for 2026 https://www.digitalocean.com/resources/articles/what-is-openclaw
[10] How to turn your Claude into a agent for OpenClaw? https://www.reddit.com/r/claudexplorers/comments/1qt4y8a/how_to_turn_your_claude_into_a_agent_for_openclaw/o30qpca/
[11] OpenClaw Desktop - The AI That Actually Does Things ... https://openclawdesktop.com
